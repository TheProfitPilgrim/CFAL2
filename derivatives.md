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
    2. t or T (time) is represented as fraction of year : 90/365, 60/365
    3. $c_t$ : European style call price at time t with expiration on time = T; $C_t$ : American style
    4. At initiation date, subscripts are ignored ==> $c = c_0$






