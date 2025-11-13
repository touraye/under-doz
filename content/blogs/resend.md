This is a great idea. Documenting your stack makes future projects much faster and helps others learn.

Here is the complete workflow formatted as a clean, step-by-step blog post.

***

# Building a Production-Ready Contact Form with Next.js, Shadcn UI, Zod, and Resend

Building forms is a classic web development task that is often more complex than it appears. You need a beautiful UI, immediate client-side validation for good UX, secure server-side validation, and a reliable way to deliver the data.

In this guide, we will build a robust, type-safe contact form using the modern Next.js stack:

*   **Next.js 14 (App Router):** The framework.
*   **Shadcn UI & Tailwind CSS:** For beautiful, accessible, copy-paste components.
*   **Zod & React Hook Form:** For industry-standard validation and form state management.
*   **Resend & React Email:** To design emails using React and send them reliably.

Let's dive in.

---

## Step 1: Install Dependencies

Assumptions: You have a Next.js project set up with Tailwind CSS, and you have initialized Shadcn UI (`npx shadcn-ui@latest init`).

First, install the necessary Shadcn components:

```bash
npx shadcn-ui@latest add button form input select textarea sonner
```

Next, install the libraries for validation, form handling, and email sending.
*Note: We must install `@react-email/render` to allow Resend to compile React components into HTML server-side.*

```bash
npm install zod @hookform/resolvers react-hook-form resend @react-email/components @react-email/render
```

---

## Step 2: Define the Validation Schema (Zod)

We define our schema in one place. This serves as the "source of truth" for both client-side validation and server-side API route validation.

Create a file at `lib/validators/contact-form.ts`:

```typescript
import { z } from "zod";

// Define the list of inquiries for reuse
export const inquiries = [
  "General Information",
  "Volunteer Opportunities",
  "Donation Inquiry",
  "Partnership",
  "Media Inquiry",
  "Program Information",
  "Other",
] as const;

// Define the schema
export const contactFormSchema = z.object({
  fullName: z.string().min(2, {
    message: "Full name must be at least 2 characters.",
  }),
  email: z.string().email({
    message: "Please enter a valid email address.",
  }),
  phoneNumber: z.string().min(10, {
    message: "Please enter a valid phone number.",
  }),
  // Using z.enum ensures the value is strictly one of the options
  typeOfInquiry: z.enum(inquiries, {
    errorMap: () => ({ message: "Please select a valid inquiry type." }),
  }),
  description: z.string().min(10, {
    message: "Message must be at least 10 characters.",
  }).max(1000, {
    message: "Message cannot exceed 1000 characters."
  }),
});

// Infer the type from the schema for full type-safety
export type TContactFormSchema = z.infer<typeof contactFormSchema>;
```

---

## Step 3: Design the Email Template

Instead of sending raw text or messy HTML strings, we'll use **React Email** to design a clean template using React components.

Create a file at `components/emails/ContactFormEmail.tsx`:

```tsx
import * as React from "react";
import {
  Html, Body, Head, Heading, Container,
  Text, Section, Hr, Preview,
} from "@react-email/components";
import { TContactFormSchema } from "@/lib/validators/contact-form";

interface ContactFormEmailProps {
  formData: TContactFormSchema;
}

export const ContactFormEmail: React.FC<ContactFormEmailProps> = ({
  formData,
}) => (
  <Html>
    <Head />
    <Preview>New Inquiry from {formData.fullName}</Preview>
    <Body style={main}>
      <Container style={container}>
        <Heading style={heading}>New Contact Submission</Heading>
        <Section style={section}>
          <Text style={text}><strong>Name:</strong> {formData.fullName}</Text>
          <Text style={text}><strong>Email:</strong> {formData.email}</Text>
          <Text style={text}><strong>Phone:</strong> {formData.phoneNumber}</Text>
          <Text style={text}><strong>Inquiry Type:</strong> {formData.typeOfInquiry}</Text>
          <Hr style={hr} />
          <Text style={text}><strong>Message:</strong></Text>
          {/* Preserves line breaks from the textarea */}
          <Text style={message}>{formData.description}</Text>
        </Section>
      </Container>
    </Body>
  </Html>
);

export default ContactFormEmail;

// Basic inline styles for email compatibility
const main = { backgroundColor: "#f6f9fc", fontFamily: "sans-serif" };
const container = { backgroundColor: "#ffffff", border: "1px solid #eee", borderRadius: "5px", margin: "40px auto", padding: "20px 40px", maxWidth: "600px" };
const heading = { fontSize: "24px", fontWeight: "bold", color: "#333" };
const section = { padding: "20px 0" };
const text = { fontSize: "16px", color: "#333", margin: "10px 0" };
const message = { fontSize: "16px", color: "#555", whiteSpace: "pre-wrap" as const, backgroundColor: "#f9f9f9", padding: "15px", borderRadius: "4px" };
const hr = { borderColor: "#e6ebf1", margin: "20px 0" };
```

---

## Step 4: Setup API Keys

1.  Go to [Resend.com](https://resend.com), sign up, and generate an API Key.
2.  Create or edit your `.env.local` file in the root of your project.

```env
# .env.local
RESEND_API_KEY=re_123456789yourkeyhere
```

---

## Step 5: Create the Backend API Route

We need a secure environment to use our API key and send the email.

Create a file at `app/api/contact/route.ts`:

```typescript
import { NextResponse } from "next/server";
import { Resend } from "resend";
import { contactFormSchema } from "@/lib/validators/contact-form";
import ContactFormEmail from "@/components/emails/ContactFormEmail";

const resend = new Resend(process.env.RESEND_API_KEY);
// The email you want to receive notifications at
const destinationEmail = "fabbfoundation.gm@gmail.com"; 

export async function POST(request: Request) {
  try {
    const body = await request.json();

    // 1. Server-side validation using the same Zod schema
    const result = contactFormSchema.safeParse(body);

    if (!result.success) {
      return NextResponse.json(
        { error: "Validation failed", details: result.error.flatten() },
        { status: 400 }
      );
    }

    const formData = result.data;

    // 2. Send email using Resend and React Email
    const { data, error } = await resend.emails.send({
      // specific 'from' address required for testing, change for production
      from: "Contact Form <onboarding@resend.dev>", 
      to: [destinationEmail],
      reply_to: formData.email,
      subject: `New Inquiry: ${formData.typeOfInquiry}`,
      // Resend will compile this React component to HTML
      react: ContactFormEmail({ formData }), 
    });

    if (error) {
      return NextResponse.json({ error: error.message }, { status: 500 });
    }

    return NextResponse.json({ success: true, data }, { status: 200 });

  } catch (error) {
    return NextResponse.json(
      { error: "Internal Server Error" },
      { status: 500 }
    );
  }
}
```

---

## Step 6: Build the Frontend Form

Finally, let's build the UI. We wire up React Hook Form with the Zod resolver, handle loading states, and display Toast notifications via Sonner.

Create (or update) `components/ContactForm.tsx`:

```tsx
"use client";

import { useState } from "react";
import { useForm } from "react-hook-form";
import { zodResolver } from "@hookform/resolvers/zod";
import { Loader2 } from "lucide-react";
import { toast } from "sonner"; // Import toast

// UI Components
import { Button } from "@/components/ui/button";
import { Input } from "@/components/ui/input";
import { Textarea } from "@/components/ui/textarea";
import {
  Form, FormControl, FormField, FormItem, FormLabel, FormMessage,
} from "@/components/ui/form";
import {
  Select, SelectContent, SelectItem, SelectTrigger, SelectValue,
} from "@/components/ui/select";

// Schema
import {
  contactFormSchema,
  TContactFormSchema,
  inquiries,
} from "@/lib/validators/contact-form";

const ContactForm = () => {
  const [isSubmitting, setIsSubmitting] = useState(false);

  // 1. Initialize form with Zod resolver
  const form = useForm<TContactFormSchema>({
    resolver: zodResolver(contactFormSchema),
    defaultValues: {
      fullName: "",
      email: "",
      phoneNumber: "",
      description: "",
      // typeOfInquiry remains undefined until selected
    },
  });

  // 2. Handle submission
  async function onSubmit(values: TContactFormSchema) {
    setIsSubmitting(true);
    try {
      const response = await fetch("/api/contact", {
        method: "POST",
        body: JSON.stringify(values),
        headers: { "Content-Type": "application/json" },
      });

      const data = await response.json();

      if (!response.ok) {
        throw new Error(data.error || "Something went wrong");
      }

      toast.success("Message sent successfully!");
      form.reset(); // Clear the form
    } catch (error) {
      toast.error("Failed to send message. Please try again.");
      console.error(error);
    } finally {
      setIsSubmitting(false);
    }
  }

  return (
    <Form {...form}>
      <form onSubmit={form.handleSubmit(onSubmit)} className="grid gap-6">
        <div className="grid grid-cols-1 sm:grid-cols-2 gap-4">
          <FormField
            control={form.control}
            name="fullName"
            render={({ field }) => (
              <FormItem>
                <FormLabel>Full Name</FormLabel>
                <FormControl>
                  <Input placeholder="John Doe" {...field} className="bg-white" />
                </FormControl>
                <FormMessage />
              </FormItem>
            )}
          />
          <FormField
            control={form.control}
            name="email"
            render={({ field }) => (
              <FormItem>
                <FormLabel>Email</FormLabel>
                <FormControl>
                  <Input placeholder="john@example.com" {...field} className="bg-white" />
                </FormControl>
                <FormMessage />
              </FormItem>
            )}
          />
        </div>

        <div className="grid grid-cols-1 sm:grid-cols-2 gap-4">
          <FormField
            control={form.control}
            name="phoneNumber"
            render={({ field }) => (
              <FormItem>
                <FormLabel>Phone Number</FormLabel>
                <FormControl>
                  <Input placeholder="+1 (555) 000-0000" {...field} className="bg-white" />
                </FormControl>
                <FormMessage />
              </FormItem>
            )}
          />
          <FormField
            control={form.control}
            name="typeOfInquiry"
            render={({ field }) => (
              <FormItem>
                <FormLabel>Type of Inquiry</FormLabel>
                <Select onValueChange={field.onChange} defaultValue={field.value}>
                  <FormControl>
                    <SelectTrigger className="bg-white">
                      <SelectValue placeholder="Select an option" />
                    </SelectTrigger>
                  </FormControl>
                  <SelectContent className="bg-white">
                    {inquiries.map((item) => (
                      <SelectItem key={item} value={item}>
                        {item}
                      </SelectItem>
                    ))}
                  </SelectContent>
                </Select>
                <FormMessage />
              </FormItem>
            )}
          />
        </div>

        <FormField
          control={form.control}
          name="description"
          render={({ field }) => (
            <FormItem>
              <FormLabel>Message</FormLabel>
              <FormControl>
                <Textarea
                  placeholder="How can we help you?"
                  className="resize-none bg-white"
                  rows={5}
                  {...field}
                />
              </FormControl>
              <FormMessage />
            </FormItem>
          )}
        />

        <Button type="submit" disabled={isSubmitting} className="w-full sm:w-auto">
          {isSubmitting && <Loader2 className="mr-2 h-4 w-4 animate-spin" />}
          {isSubmitting ? "Sending..." : "Send Message"}
        </Button>
      </form>
    </Form>
  );
};

export default ContactForm;
```

Don't forget to add the `<Toaster />` to your root layout (`app/layout.tsx`) so the notifications appear:

```tsx
import { Toaster } from "@/components/ui/sonner"

export default function RootLayout({ children }) {
  return (
    <html lang="en">
      <body>
        <main>{children}</main>
        <Toaster richColors />
      </body>
    </html>
  )
}
```

## Important Note on Resend Production

While testing, you must use `onboarding@resend.dev` as the "From" address, and you can only send emails to the email address you used to sign up for Resend.

To go to production and send emails to any address using a custom domain (e.g., `noreply@yourfoundation.org`), you must **verify your domain** in the Resend dashboard. Once verified, update the `from` field in `app/api/contact/route.ts`.