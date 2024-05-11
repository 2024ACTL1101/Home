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

## Compound Interest

"Money makes money. And the money that money makes, makes money." - Benjamin Franklin

"The most powerful force in the universe is compound interest." - Albert Einstein (possibly apocryphal, see [Snopes](https://www.snopes.com/fact-check/compound-interest/))

### Definitions

- **Nominal Interest Rate** - Interest rates are normally **QUOTED** as per annum percentage nominal rates.
- **Effective Interest Rate per Period** - Let $j^{(m)}$ denote the per annum nominal interest rate with $m$ periods. The effective interest rate per period is calculated as:
  $r = \frac{j^{(m)}}{m}$

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

## Time Value of Money in Fixed Income and Equity

Understanding the time value of money is essential in evaluating the present value (PV) of fixed-income and equity instruments based on expected future cash flows. The principle that cash inflows are valued more highly the sooner they are received is fundamental in financial analysis.

### Time Value of Money Principles

The relationship between a current or present value (PV) and future value (FV) of a cash flow, given a discount rate \(r\) per period and \(t\) compounding periods, is defined as:

- **Future Value:**
$$
FV_t = PV \times (1 + r)^t
$$

- **Present Value:**
$$
PV = \frac{FV_t}{(1 + r)^t}
$$

When compounding continuously:
- **Future Value with Continuous Compounding:**
  \[ FV_t = PV \times e^{rt} \]

- **Present Value with Continuous Compounding:**
  \[ PV_t = FV \times e^{-rt} \]

## Fixed-Income Instruments

Fixed-income instruments include debt securities like bonds or loans. These instruments can exhibit different cash flow patterns:

### Discount Instruments

For a discount instrument, an investor pays a price (PV) today and receives the full principal amount (FV) at maturity without receiving periodic interest payments. This type is often called a zero-coupon bond.

**Example:**
- **Investment:** Purchase of a discount bond with a principal of INR 100, due in 20 years.
- **Market Discount Rate:** 6.70%
- **Calculation:**
  \[ PV = \frac{INR 100}{(1 + 0.067)^{20}} = INR 27.33 \]

### Periodic Interest Instruments

These involve paying a price (PV) for a bond or loan and receiving periodic interest payments (PMT) across the life of the instrument, with the final interest payment and the principal paid at maturity.

### Level Payment Instruments

Instruments like mortgages where an investor pays an initial price (PV) and receives uniform cash flows (PMT) at predetermined intervals through maturity which represent both interest and principal repayment.

## Equity Instruments

Equity investments such as stocks involve ownership shares in a company and entitle investors to receive discretionary cash flows in the form of dividends.

### Valuation Models

#### Constant Dividends

If dividends are constant:
\[ PV = \frac{D}{r} \]

#### Growing Dividends

If dividends grow at a constant rate \(g\):
\[ PV = \frac{D \times (1 + g)}{r - g} \]

**Example:**
- **Scenario:** A stock pays a starting dividend of GBP 1.50 expected to grow at 6% per year indefinitely.
- **Required Rate of Return:** 15%
- **Calculation:**
  \[ PV = \frac{GBP 1.50 \times (1 + 0.06)}{0.15 - 0.06} = GBP 17.67 \]

### Application in Practical Scenarios

These principles allow investors and financial analysts to evaluate and compare the value of different investment opportunities, taking into account the timing of cash flows and the associated risks due to time and uncertainty.

