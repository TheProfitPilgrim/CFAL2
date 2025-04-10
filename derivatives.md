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

### One period Binomial Model

![img](https://raw.githubusercontent.com/TheProfitPilgrim/CFAL2/main/cfa_media/2.png)

The binomial model has only 2 options - the price going up or down 

Upfactor : $u = \frac{S^+}{S}$

Downfactor : $d = \frac{S^-}{S}$

Now for a two period call option, t = 0 is start. Say it moves up at t = 1(so $c_+$). Now value of the call option at expiry at t = 2 can be either : 

$$c^{++} = Max (0, u^2S - X) $$ 
$$c^{+-} = Max (0, udS - X) $$

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

* Thus you need to buy 0.5 shares of the underlying and borrow 40 in cash to replicate the call option's value
* If you consider cost of borrowing as risk free rate, then you should borrow PV of that amount 
* So for a call option : 
* Buy $h = \frac{c^+ - c^-}{S^+ - S^-}$ units of the underlying and borrow PV $(-hS^- + c^-)$

![img](https://raw.githubusercontent.com/TheProfitPilgrim/CFAL2/main/cfa_media/1.png)

Answer A 

* For a put positions to be replicated, the same Hedge formula holds good. Just replace c with p. 
* But there is a difference : $p^+$ will be lesser than $p^-$ thus, the hedge ratio will be negative indicating that you should short the underlying and lend money

Thus in the **expectations approach**, the value of call and put is : 

$$ c = PV(\pi c^+ + (1-\pi)c^-) = E(c_1) $$

$$ p = PV(\pi p^+ + (1-\pi)p^-) = E(p_1) $$

where the risk neural probability $\pi$ 

$$\pi = \frac{(1+r) - d}{u-d}$$

r : interest rate / risk free rate

* This expected value is different in the sense that the probabilities are not determined by the investors based on their view. It is objectively determined. 

    Suppose a call option is trading at $20 and its value is $18, the arbitrage to do here is : 
    1. Short the call option
    2. Replicate a long call position so : 
        * Buy underlying shares
        * Borrow funds


### Two period Binomial Model: Call Options

* For a two period binomial option, there are 4 possibilities. ++, +-, -+ and --. The +- and -+ yield the same results thus 3 possibilities. 

* Draw the tree with possibilities and find it step by step from t=2 --> t=1 and then t=0. Based on the option values of t=2 we find t=1 and then using t=1 we find t=0

* 2 important concepts : 
    1. Self-financing : the replicating will not require any additional funds from the arbitrageur during the entire lifetime
    2. Dynamic Replication : at every step, the replication mimics the expiration value of the option

* The main differnce b/w European and American options is checking for exercising at every step. Follow the same steps as EU options but if the exercise call/put price is higher than the calculated one, use that as the value for further steps 

### Role of Dividends

* Dividends encourage early exercise for American calls 
* If dividend is large enough, american call > european call
* If no dividends, early exercise is never optimal for calls
* For puts, early exercise might be optimal even without dividends

### Interest Rate options using Binomial Model 

1. Solve just like the stock case. Instead of strike price, you have exercise rate in % terms.
2. Use the zero coupon bond rates as the equivalent of risk free rate in the stock option case - instead of doing $\frac{\pi*c^+ + (1-\pi)*c^-}{(1+r)}$, do ${\pi*c^+ + (1-\pi)*c^-}*Zero-coupon \ bond \ rate$

### BSM Option Valuation Model

* Follows no arbitrage approach but applied with continuous time
* Uses GBM - geometric brownian motion as its stochastic process because:
    * The value never reaches 0 or goes below it (like stocks and many fin instruments)
    * Does not make any sudden jumps

#### Assumptions of BSM 

* Continuously compounded return is normall distributed
* Price move continuously, does not jump from one value to another
* Underlying is liquid - can be easily bought and sold
* Continuous trading is available
* Complete short selling is allowed
* No market frictions
* No arbitrage opportunities
* Options are European style : early exercise not allowed 
* Continuously compounded risk-free rate is known and constant & borrowing and lending at risk-free rate is allowed
* Volatility of the return on the underlying is known and constant 
* If underlying pays a yield, it is expressed as continuous known and constant yield at annualised rate

### BSM Model : Components 

The BSM model for stocks : 

![img](https://raw.githubusercontent.com/TheProfitPilgrim/CFAL2/main/cfa_media/3.png)

Due to symmetry of normal distribution,***N(-x) = 1 - N(x)***

The BSM can also be thought of as 2 components : the stock and bond component

For call options, $SN(d_1)$ is the stock component and $e^{-rT}XN(d_2)$ is the bond component 

For put options, $SN(-d_1)$ is the stock component and $e^{-rT}XN(-d_2)$ is the bond component

The BSM model can be interpreted as a dynamically managed portfolio of stocks and zero-coupon bonds.

Replication strategy cost = $n_SS + n_BB$

* Number of shares to buy $n_S = N(d_1) > 0$ for calls and $n_S = -N(-d_1) < 0$ for puts. 
* The price of a zero coupon bond is $B = e^{-rT}X$. 
* Number of bonds to buy : $n_B = -N(d_2)$
* If n is +ve, we are buying the underlying. If n is -ve, we are shorting

![img](https://raw.githubusercontent.com/TheProfitPilgrim/CFAL2/main/cfa_media/4.png)

#### Option Expiry Probabilities (BSM Model)

| Option Type | Expiry Condition     | Probability Expression |
|-------------|----------------------|-------------------------|
| Call        | In the Money (ITM)   | \( N($d_2$) \)            |
| Call        | Out of the Money     | \( N($-d_2$) \)           |
| Put         | In the Money (ITM)   | \( N($-d_2$) \)           |
| Put         | Out of the Money     | \( N($d_2$) \)            |

### BSM Model : Carry Benefits and Applications 

![img](https://raw.githubusercontent.com/TheProfitPilgrim/CFAL2/main/cfa_media/5.png)

* Carry benefits *decrease* the value of call options and *increase* the value of put options
* If the stock does not pay any dividends but you use this model, ie, $\gamma = 0$, then the value will change because d1 and d2 have been adjusted for dividends

* For foreign exchange options, $\gamma = r^f$ is the continuously compounded foreign risk free rate
* Carry benefit is the interest rate in the foreign country because the foreign currency could be invested in the foreign country's risk free rate
* Both the underlying and exercise price must by quoted in the same currency
* Volatility in the model is the volitility of the log return of the spot rate
* There is a notional amount and cost of option = value * notional amount

* The two components for call options are : The foreign exchange compoenent (similar to stock component) $Se^{-r^fT}N(d_1)$ and the bond component is $Xe^{-rT}N(d_2)$
* For Put options it is the same as call but with $-d_1$ and $-d_2$ for the respective components
* If option is at-the-money, then underlying = spot = exercise price

### Black Option Valuation Model and EU options on Futures

* BSM model when underlying is costless to carry like equity indices, forwards / futures contract
* 


