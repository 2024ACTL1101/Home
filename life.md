## Life Insurance Products

There are many types of Life Insurance products (see Sherris Section 8.3), with the most common being:

- **Whole of Life**: Pays a benefit at death, regardless of when death occurs.
- **Term Insurance**: Pays a benefit at death, but only if death occurs in a certain period.
- **Endowment**: Pays a benefit at death if death occurs in a certain period, but also pays the benefit if the life is alive at the end of the period.


## Term Insurance - Claim Payments

- $T(x)$ is the future lifetime (a continuous random variable) for a life $(x)$.
- $X$ is the age-at-death (also a continuous random variable).
  
$$
T(x) = X - x
$$
- Will require probability of this random variable taking values $0,1,\cdots,n-1$.
  - $x+k$ age last birthday, with integer $x+k$.

## Term Insurance - Benefit Payment

Assume the insured life is aged $x$ at purchase, the death benefit is of amount $S$, and it is paid at the end of the year of death, but only if death occurs within $n$ years of purchase.
Assume an annual (effective) rate of interest $i$.
- If death occurs in the first year of the policy, when the life is aged $x$, then the present value of the death benefit would be:

$$
\frac{S}{(1+i)} = Sv
$$
  
- If death occurs when the life is aged $x+1$ then the present value of the benefit would be:
  
$$
\frac{S}{(1+i)^2} = Sv^2
$$

In general, if death occurs when the life is aged $x+k$ last birthday where $k=0,1,2,\ldots n-1$ then the **present value of the benefit payment** at the end of the year of death would be:

$$
\text{PV[Payment]} = 
\begin{cases}
Sv^{k+1} & \text{for } k=0,1,2,\ldots, n-1 \\
0 & \text{for } k \geq n
\end{cases}
$$

## Term Insurance - EPV of Claim Payments

What are the associated probabilities with the values of the present value of the payment?

Let $K(x)$ be the discretized future lifetime random variable for age $x$ (i.e., $K(x) = \lfloor T(x) \rfloor$). Then:

$$
\text{PV}[Payment] = 
\begin{cases}
Sv^{k+1} 	& \text{with probability Pr} [K(x) = k] \\
            & \text{for } k = 1,2,3,\ldots,n-1 \\
0 & \text{with probability Pr} [K(x) \geq n] = ~_{n} p_x
\end{cases}
$$

What is $\Pr[K(x) = k]$?

$$
\Pr[K=k] = \Pr[k \leq T(x) < k+1] = _{k}p_{x}q_{x+k}
$$

## Expected Present Value of Benefit Payment

The **Expected Present Value** of the benefit payment for this term insurance is then:

$$
\sum_{k=0}^{n-1} S v^{k+1}(_{k}p_{x}q_{x+k}) = S \cdot \sum_{k=0}^{n-1} v^{k+1}(_{k}p_{x}q_{x+k}) = S \cdot A_{x:\overline{n}\rvert}^{1}
$$

Where $A_{x:\overline{n}\rvert}^{1}$ is standard actuarial notation (for the expected PV of a term life insurance paying a benefit of 1, and covering the next $n$ years of a life aged $x$).

### Example 8.5

Determine the expected present value of the claim payments for a 5-year term insurance on a life aged 20 with a sum insured of $100,000 using the following mortality probabilities and a 6% p.a. effective interest rate.

#### Mortality Probabilities

| Age  | $q_{\text{age}}$      |
|------|----------------------|
| 20   | 0.00192              |
| 21   | 0.00181              |
| 22   | 0.00160              |
| 23   | 0.00138              |
| 24   | 0.00118              |

#### Solution

To calculate the EPV of $1 payable on death within $n$ years:

$$
A_{20:\overline{5}|}^{1} = \sum_{k=0}^{4}v^{k+1}\left( _{k}p_{20}q_{20+k}\right)
$$

where:
- $v^{k+1} = \left( \frac{1}{1.06}\right)^{k+1}$
- $_{k}p_{20} \) is assumed as follows, with \( _{0}p_{20}=1$:

#### Detailed Calculations

| Age(x+k) | $q_{x+k}$    | $k$  | $v^{k+1}$ | $_{k}p_{x}$ | $_{k}p_{x} \cdot q_{x+k}$ |
|----------|--------------|------|-----------|-------------|----------------------------|
| 20       | 0.00192      | 0    | 0.94340   | 1.00000     | 0.00192                    |
| 21       | 0.00181      | 1    | 0.89000   | 0.99808     | 0.00181                    |
| 22       | 0.00160      | 2    | 0.83962   | 0.99627     | 0.00159                    |
| 23       | 0.00138      | 3    | 0.79209   | 0.99468     | 0.00137                    |
| 24       | 0.00118      | 4    | 0.74726   | 0.99331     | 0.00117                    |


**Total $A_{20:\overline{5}|}^{1}$: $0.00672$**

The EPV of the claim payments for a sum insured of $100,000 is then:

$$
100,000 \cdot A_{20:\overline{5}|}^{1} = 672.06
$$

### Life Annuities

- A **life annuity** is a stream of regular payments, paid as long as a life is alive.
- Consider a life aged $x$. Call $P_k$ the payment they receive at time $k$, for $k=0,1,2,\ldots$
- The Expected Present Value of a life annuity due (paid in advance) of $1 per period to this life aged $x$ is:

$$
\ddot{a}_{x} = \mathbb{E} \left[ \text{PV}(P_0) + \text{PV}(P_1) + \ldots + \text{PV}(P_{\omega-x-1}) \right]
= \sum_{k=0}^{\omega -x-1}v^k \cdot _{k}p_{x}
$$

Furthermore:

$$
\ddot{a}_{x} = 1 + \sum_{k=1}^{\omega -x-1}v^k \cdot _{k}p_{x}
= 1 + \sum_{k=1}^{\omega -x-1}v \cdot v^{k-1} \cdot p_x \cdot _{k-1}p_{x+1}
= 1+v \cdot p_{x} \left[ \sum_{k=0}^{\omega -x-2}v^k \cdot _{k}p_{x+1}\right]
= 1+v \cdot p_{x} \cdot \ddot{a}_{x+1}
$$

- Note that $\ddot{a}_{x} = 1 + a_x.$ Do you see why?

If the payments are restricted to $n$ payments maximum:

$$
\ddot{a}_{x:\overline{n}|} = \sum_{k=0}^{n-1} v^k \cdot _{k}p_{x} = 1 + a_{x:\overline{n-1}|}
$$




# Life Insurance Application - Case Study

### Background

**LifeSecure Insurance** has tasked you, an actuarial analyst, with developing a new term life insurance product aimed at the diverse U.S. market. This product will cover individuals from ages 0 to 120 for a 5-year term. With changing demographics, healthcare improvements, and fluctuating economic scenarios, it is crucial to set a competitive yet profitable premium and assess the product's financial viability over its term.

### Objectives

- **Premium Calculation**: Determine the premium necessary to cover the expected costs of claims, considering initial and renewal expenses.
- **Policy Liability Evaluation**: Assess the expected value of the policy's liability at the end of each year of the term using a recursive formula.

### Data Sources and Assumptions

- **Mortality Rates**: Extracted from the **Human Mortality Database** for U.S. individuals aged 0 to 120.
- **Interest Rate**: Assumed to be 5% per annum.
- **Initial Expenses**: 0.5% of the sum insured at policy inception.
- **Renewal Expenses**: $100 per annum per policy.

### Methodology

1. **Mortality Data Analysis**: Investigate U.S. mortality rates to understand age-specific risk factors.
2. **Financial Modeling**:
   - Use actuarial methods to calculate the necessary premium that covers the present value of future claims and expenses.
   - Implement recursive calculations to determine policy liability over the term.

## Implementation Steps [To-Do]

### Extract and Analyze Mortality Data
Begin by extracting age-specific mortality rates for the U.S. from the Human Mortality Database. Analyze these to understand mortality trends relevant to the age groups of interest, which will form the basis for pricing and risk assessment.

### Programming and Calculation

- **Develop a R or Python Script**: Automate the calculations of premiums and liabilities using Python. This script will integrate the mortality data, financial assumptions, and actuarial formulas to compute the necessary values.
- **Validate Calculations**: Ensure the accuracy of the script by comparing its outputs against industry standards and through peer reviews.

### Documentation

- **Process Documentation**: Clearly document each step of the analysis in your markdown file, ensuring that all calculations are reproducible and transparent.
- **Visualizations**: Include charts or graphs to visualize mortality trends and changes in the pricing structure across different age groups. This will help in illustrating the data-driven insights obtained from the analysis.

## Discussion Questions [To-Do]

1. **How would you approach setting a premium structure that balances both competitiveness in the market and profitability for the insurer?** Consider the role of actuarial fairness and market viability in your answer.
2. **What factors should be considered to ensure that premiums are set at a fair rate while still appealing to potential customers?** Discuss how demographic data, mortality rates, and market trends might influence your strategy.
3. **Discuss how external factors like economic downturns or pandemics might affect the profitability and marketability of life insurance products.** What strategies might an insurance company employ to mitigate these risks?
4. **Can you think of a recent event that significantly impacted the insurance industry?** How did insurance providers respond to this event in terms of product pricing or policy terms?


