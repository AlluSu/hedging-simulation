# Hedging simulation
This project performs delta hedging, delta-vega hedging, delta-vega-gamma hedging and other financial risk management strategies on real option data. The data used is Apple's stock option data, which was obtained from Refinitiv using the university's license with the Python script found under *data/data-fetching-scripts* directory. Apple stock options was chosen due to Apple's stock being very liquid.  

This assignment was done as part of the Financial Engineering 1 class as a group project.  

## Hedging and option greeks  

Hedging can be classified into two categories: static and dynamic. Static hedges do not need to be rebalanced when for example, volatility or underlying changes, as in dynamic hedging rebalancing is needed. A static hedge would be for example, a futures contract for a currency rate.  

### Delta and Delta hedging  

Delta-hedging is a dynamic hedging strategy, which is used to protect against a downturn in the price of the underlying asset, e.g. a stock price. In this situation, one needs to hedge, i.e., sell short Delta ∆ units of the underlying asset. So the initial situation is that we have a portfolio, which consists of one long position in a call option and one short position in ∆ amount of the underlying asset. The ∆ should be chosen so that the value of the portfolio is not sensitive to small changes in the price of the underlying asset. To make a delta-neutral portfolio, we want the delta of the portfolio to be 0, and then solve the linear equation to get the amount of assets needed to sell or buy to balance the portfolio. Delta is determined as the first partial derivative of Black-Scholes price with respect to the underlying stock, and is one of the most fundamental greeks that exists in trading. So in other words, Delta is the difference in the call option price with respect to the difference in the stock price. For call options, the Delta is always between 0 and 1, and for put options between 0 and -1.  

In addition to Delta, there are multiple other greeks, which can be utilized in trading. Gamma and Vega are also good indicators, which the trader can monitor in the market, and try to either hedge their position or try to make money based on these.  

### Gamma  
Gamma is the derivative of Delta, i.e., also the second derivative of the Black-Scholes option price with respect to the underlying asset's price. Gamma of the underlying is always 0, while the Delta of the underlying is always 1. Gamma expresses how much hedging will cost in a small time interval, and if the Gamma of the portfolio is positive, we make money by delta hedging and vice versa. When we have a portfolio, which is both Delta and Gamma hedged, it results in a portfolio which is even less sensitive to small price changes of the underlying. Also when the portfolio is both Delta and Gamma hedged, there occurs less need for rebalancing, which saves trading costs.  

### Vega  
As Delta and Gamma are Greeks with respect to the spot price, Vega is a Greek with respect to volatility. A positive Vega portfolio rises in value when the volatility increases, and falls in value when the volatility decreases. To attain a positive Vega, you should buy a call, and to attain a negative Vega, you should sell a call. A trader could take a long Vega position if they believe that volatility will increase in the future, and short Vega if they believe volatility will decrease. The Vega of the underlying is always 0, as like Gamma also.  

## Future work  
This repository is still work-in-progress, and could be improved in many ways:  

- Add more option strategies in addition to Straddle and Strangle
- Apply other hedging strategies than delta hedging to Straddle and Strangle
- Make the codebase more cleaner and robust by splitting the code into smaller functions
- Present the results more clearly (outputs and plots)
- Make the code less copy-paste, and more generally applicable to different datasets and situations  

