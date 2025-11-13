# Investment Pool

Ahmed is an early investor who initially invested **$109** in the stock market. His investment agent informed him that his capital would yield a **50% return on investment (ROI) every week**.

If Ahmed decides to **hold onto his investment for six months** (approximately **24 weeks**), his initial capital will undergo **compound growth**. The goal is to:

1. **Calculate the total compounded value of Ahmed’s investment after 24 weeks** based on the weekly 50% return.
2. **Determine the total margin of return on investment** over this six-month period.
3. **Compute the final amount Ahmed will have** at the end of the investment period, including both the initial principal and the accumulated returns.

### Possible Variables:

- **initial_investment** = `109` (Ahmed’s starting capital)
- **weekly_roi** = `50%` (investment return per week)
- **weeks_held** = `24` (number of weeks in six months)
- **final_amount** = `?` (total compounded value after 24 weeks)
- **profit_margin** = `?` (total earnings excluding the initial investment)

The program should use **compound interest principles**, where each week's return is reinvested, contributing to exponential growth. The formula to compute the final investment amount is:

A=P(1+r)tA = P (1 + r)^t

Where:

- **A** = Final investment amount
- **P** = Initial investment (`$109`)
- **r** = Weekly return rate (`50%` or `0.50`)
- **t** = Number of weeks (`24`)

Finally, the **profit margin** is calculated as:

Profit Margin=A−P\text{Profit Margin} = A - P

This approach ensures Ahmed understands how much his investment will grow over time.



