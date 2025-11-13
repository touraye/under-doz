#  Community Investment Pool

A group of individuals decides to **pool their money together** over a period of **one year** with the intention of **investing in a lucrative business**. At the end of the year, each member will receive a **share of the investment profits** based on their total contribution.

Each participant contributes a **monthly amount within the range of GMD5,000 to GMD15,000**. The program will:

1. **Take user inputs**:
   - Name of each participant.
   - Their **total contribution** at the end of the year (calculated as their monthly contribution × 12).
2. **Compute and display**:
   - The **total pooled amount** from all participants.
   - Each participant’s **percentage share** of the total contribution.
   - (Optional) A projection of **potential profit shares** based on predefined business returns.

------

### **Possible Variables**

- **participants** = A list to store details of each participant.
- **name** = Name of the participant.
- **monthly_contribution** = The amount contributed per month (between **GMD5,000 and GMD15,000**).
- **total_contribution** = Monthly contribution × 12 (total amount contributed in one year).
- **total_pooled_amount** = The sum of all participants' total contributions.
- **percentage_share** = (individual contribution / total pooled amount) × 100.
- **profit** (optional) = The potential business earnings if an investment return rate is applied.

------

### **Additional Enhancements**

- Implement **data validation** to ensure contributions stay within the allowed range.
- Allow **multiple users** to enter their details.
- Format the **output report** to clearly show each participant's contribution, their percentage in the pool, and the total pooled funds.
- (Optional) Simulate **investment growth** by applying a return rate (e.g., **20% annual return**) to project each member’s potential earnings.

## Task:

Develop a Java program to solve such a problem. The program should be free from error, users should seamlessly interact with the program. The program should be clear and concise, and all currencies should be formatted with a GMD money sign.