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

## One period Binomial Model

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




