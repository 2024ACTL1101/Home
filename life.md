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


```math
\Pr[K=k] = \Pr[k \leq T(x) < k+1] = _{k}p_{x}q_{x+k}
```



## Expected Present Value of Benefit Payment

The **Expected Present Value** of the benefit payment for this term insurance is then:

```math
\sum_{k=0}^{n-1} S v^{k+1} \cdot _{k}p_{x}q_{x+k} = S \cdot \sum_{k=0}^{n-1} v^{k+1} \cdot _{k}p_{x}q_{x+k} = S \cdot A_{x:\overline{n}|}^{1}
```

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

To calculate the EPV of 1 payable on death within $n$ years:

```math
A_{20:\overline{5}|}^{1} = \sum_{k=0}^{4}v^{k+1}\left( _{k}p_{20}q_{20+k}\right)
```

where:
- $v^{k+1} = \left( \frac{1}{1.06}\right)^{k+1}$
- $\_{k}p_{20}$ is assumed as follows, with $\_{0}p_{20}=1$

#### Detailed Calculations

| Age(x+k) | $q_{x+k}$    | $k$  | $v^{k+1}$ | $\_{k}p_{x}$| $\_{k}p_{x} q_{x+k}$       |
|----------|--------------|------|-----------|-------------|----------------------------|
| 20       | 0.00192      | 0    | 0.94340   | 1.00000     | 0.00192                    |
| 21       | 0.00181      | 1    | 0.89000   | 0.99808     | 0.00181                    |
| 22       | 0.00160      | 2    | 0.83962   | 0.99627     | 0.00159                    |
| 23       | 0.00138      | 3    | 0.79209   | 0.99468     | 0.00137                    |
| 24       | 0.00118      | 4    | 0.74726   | 0.99331     | 0.00117                    |


The EPV of the claim payments for a sum insured of 100,000 is then:

```math
100,000 \cdot A_{20:\overline{5}|}^{1} = 672.06
```

### Life Annuities

- A **life annuity** is a stream of regular payments, paid as long as a life is alive.
- Consider a life aged $x$. Call $P_k$ the payment they receive at time $k$, for $k=0,1,2,\ldots$
- The Expected Present Value of a life annuity due (paid in advance) of 1 per period to this life aged $x$ is:

```math
\ddot{a}_{x} = \mathbb{E} [ \text{PV}(P_0) + \text{PV}(P_1) + \ldots + \text{PV}(P_{\omega-x-1})] = \sum_{k=0}^{\omega-x-1}v^k \cdot _{k}p_{x}
```


Furthermore:

```math
\ddot{a}_{x} = 1 + \sum_{k=1}^{\omega -x-1} v^k \cdot _{k}p_{x} = 1 + \sum_{k=1}^{\omega -x-1} v \cdot v^{k-1} \cdot p_{x} \cdot _{k-1}p_{x+1} = 1 + v \cdot p_{x} \left[ \sum_{k=0}^{\omega -x-2} v^k \cdot _{k}p_{x+1} \right] = 1 + v \cdot p_{x} \cdot \ddot{a}_{x+1}
```

- Note that $\ddot{a}_{x} = 1 + a_x.$ Do you see why?

If the payments are restricted to $n$ payments maximum:

```math
\ddot{a}_{x:\overline{n}|} = \sum_{k=0}^{n-1} v^k \cdot _{k}p_{x} = 1 + a_{x:\overline{n-1}|}
```






