# Financial Mathematics

## Introduction and Motivation

### Motivation

From the [Actuaries Institute](https://www.actuaries.asn.au/becoming-an-actuary/):

> "Actuaries evaluate risk and opportunity - applying mathematical, statistical, economic and financial analyses to a wide range of business problems."

A key concept here is **financial**; most of an actuary's work relates in some way or another to money, such as insurance claims, superannuation benefits, investment returns, etc. Understanding the **time value of money** is crucial: $1,000 today does not hold the same value as $1,000 in 20 years...

### Overview

Financial mathematics are typically not an end in itself but a **fundamental tool** that actuaries need. This week covers the valuation of **known** future cash-flows. Another difficulty in actuarial studies is that cash flows related to losses are by nature **uncertain**. In-depth coverage is provided in the course ACTL2111: Financial Mathematics.

Historically, actuaries developed the application of the mathematics of finance to insurance problems as early as the 1700s.

### Some Applications

1. **Personal and Housing Loans**
   - Personal loan - usually with level repayments, "flat" fixed interest rates (3 to 5 years)
   - Housing loan - level repayments of loan principal and interest (20 to 30 years), variable interest rates in Australia, flexible repayments

2. **Fixed and Floating Interest Securities (Bonds)**
   - Repayments of interest (coupons) and face value on maturity
   - Includes government bonds, corporate bonds

### Terminology

- **Principal** (not principle) - Amount of the loan or investment
- **Maturity** - Repayable at a future specified date (the maturity date of the loan)
- **Repayments** - Repayments of capital and interest, typically level repayments as in an annuity or interest-only as in a government bond

## Compound Interest

"Money makes money. And the money that money makes, makes money." - Benjamin Franklin

"The most powerful force in the universe is compound interest." - Albert Einstein (possibly apocryphal, see [Snopes](https://www.snopes.com/fact-check/compound-interest/))

### Definitions

- **Nominal Interest Rate** - Interest rates are normally **QUOTED** as per annum percentage nominal rates.
- **Effective Interest Rate per Period** - Let $j^{(m)}$ denote the per annum nominal interest rate with $m$ periods. The effective interest rate per period is calculated as:
  $$r = \frac{j^{(m)}}{m}$$

### Continuous Compounding

- The `continuously compounded interest rate` is the nominal interest rate obtained when the compounding frequency is increased to infinity.
- Known as the **force of interest**, with the mathematical constant $e$ discovered by Jacob Bernoulli in 1683.
- For an annual effective rate of 10% p.a., the continuously compounded interest rate is approximately 9.530%, calculated as:
  $$\delta = \ln[1 + j] = \ln[1.1] = 0.09531.$$

## Annuities and Actuarial Notation

### Time Certain Annuity

A **time certain annuity** is a stream of level payments, happening at regular intervals. Assuming a constant interest rate, the symbol $a_{\lcroof{n}}$ represents the Present Value (PV) of $n$ payments of 1, payable in arrears (at the end of each period).

### Annuity Due - Payments in Advance

For annuity due, where payments are made in advance, the Present Value is represented by $\ddot{a}_{\lcroof{n}}$, and calculated as:
$$\ddot{a}_{\lcroof{n}} = (1 + i) \cdot a_{\lcroof{n}}$$
