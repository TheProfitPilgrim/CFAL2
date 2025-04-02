# Derivatives

## Valuation of Contigent Claims

### Introduction 

* Main goal is to understand how the values of options are determined 
* Like other instruments, a valuation model is used with inputs and an ouput. This also follows the no arbitrage principle.
* Thus the approximate price of an option is one that makes it impossible for any party to earn an arbitrage profit at the expense of the other
* This price is the value of the option 

2 models : 

    1. Binomial model : based on discrete time
    2. BSM model : based on continuous time 

* From the perspective of abitrageur : Do not use own money, Do not take price risk 
* Built on the law of one price - if 2 investments have same CF, then both should have same current price 

A few assumptions are made : 

    1. Instruments are identifiable and investible
    2. There are no market frictions : transaction costs, taxes
    3. Short selling is allowed with full use of proceeds
    4. Underlying instrument follows a known stat distribution
    5. Borrowing and lending at a risk free rate is available 

### Binomial Option Valuation Model

* Used to value path-dependent options. BSM is used for path-independent options. 
An option is path dependent if the value depends not only on the underlying at expiration but also on how it got there. Path dependent : American options (can be exercised prior to expiration), Independent : European options

Naming : 

1. $S_t$ : Underlying's price at time t. $S_T$ for time T
2. t or T (time) is represented as fraction of year : $\frac{90}{365}$, $\frac{60}{365}$
3. $c_t$ : European style call price at time t with expiration on time = T; $C_t$ : American style
4. At initiation date, subscripts are ignored ==> $c = c_0$

A 90-day EU call option : c = 2.50 and T = $\frac{90}{365} = 0.246575$ has exercise value of : 

$c_T$ = Max(0, $S_T - X$)

$p_T$ = Max(0, $X - S_T$)

#### Hedge Ratio and Forming an equivalent portfolio

Lets a stock is at 100. We buy a call option at strike 100.

Now the stock has 2 options : Go to 120 or go to 80. 

If it goes to 120, the call option value will be 120 - 100 = 20. If it goes to 80, the call option will expire worthless so 0. 

Now, if we need to create a position using the underlying stock and cash that replicates this call option pay off, we need to buy the underlying and borrow money. 

How much of the underlying should you buy? You should buy h (hedge ratio) amount of shares where h is : 

$$h = \frac{20-0}{120-80} = 0.5$$

How much should you borrow? 

The value $ V = hS + B$

If the stock is UP : 
$$20 = 0.5*120 + B $$

which implies B = -40, i.e, you should borrow 40.

If the stock is DOWN : 
$$ 0 = 0.5*80 + B $$

which implies B = -40 again.

Thus you need to buy 0.5 shares of the underlying and borrow 40 in cash to replicate the call option's value

### One period Binomial Model








