# Weather Guessing Game 

**Development Guide**

Objective:

To create a console-based Java program that guesses the weather condition based on a user's outfit.

------

### Step 1: **Define the Purpose**

The program should:

- Ask the user for a set of outfit items they are wearing.
- Based on the combination of these items, guess the likely weather (e.g., **hot**, **cold**, **windy**, **rainy**, or **sunny**).

------

### Step 2: **Plan the Data**

Declare variables for each outfit item. Each will store either:

- `1` (Yes – the item is worn)
- `0` (No – the item is not worn)

Example outfit items:

```java
int sunGlass, hat, jumper, rainCoat, rainBoot, jacket, scarf, tShirt;
```

------

### Step 3: **Collect Input**

Use the `Scanner` class to ask the user whether they're wearing each item. Prompt for input with simple yes/no questions.

```java
Scanner in = new Scanner(System.in);
System.out.print("Are you wearing a Hat? ");
hat = in.nextInt();
```

Repeat for all items.

------

### Step 4: **Define Conditions**

Use `if` statements to check for outfit combinations that match specific weather conditions.

**Example Conditions:**

- **Hot**: Sun Glass + Hat + T-shirt
- **Cold**: Jumper + Jacket + Scarf
- **Windy**: Jumper + Jacket (but not Rain Coat or Sun Glass)
- **Rainy**: Rain Coat + Rain Boots

```java
if (sunGlass == 1 && hat == 1 && tShirt == 1) {
    System.out.println("☀️ It's likely a hot and sunny day.");
}
```

Emojis to enhance the look and feel for program
sunny day ☀️, cold ❄️, windy day 🍃, rainy day 🌧️, warn not too sunny 🌤️, no clue 🤷‍♂️ 

Handle no clues scenario: user input 1 (yes) or 0 (no) for all.

------

### Step 5: **Close Scanner**

Good practice to close the `Scanner` after use:

```java
in.close();
```

------

### Output

```
Are you wearing Sun Glasses? 1
Are you wearing a Hat? 1
Are you wearing a T-Shirt? 1
Are you wearing a Jumper? 0
Are you wearing a Rain Coat? 0
Are you wearing Rain Boots? 0
Are you wearing a Jacket? 0
Are you wearing a Scarf? 0

☀️ It's likely a hot and sunny day!
```



Happy coding!