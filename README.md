# Assignment1: Mean-CoVaR Model to Optimize Portfolio

When used in risk measurement, CVaR not only takes into account the frequency of exceeding VaR value, but also the average loss exceeding VaR value. The measurement of tail loss is sufficient. 

In addition, when the density function of portfolio losses is a continuous function, the CVaR model is a consistent risk measurement model with subadditivity, and the risk diversification effect of portfolio is considered. In particular, when the modern portfolio theory based on mean-variance is applied in asset allocation, CVaR is used to replace variance as the risk measurement index and the planning goal is to minimize CVaR, which can optimize allocation and reduce investment risks. In other words, the mean-CVaR model minimizes the CVaR by adjusting the configuration when the expected return is certain. Or, when CVaR is constant, adjust the configuration to maximize the revenue. 

However, CVaR is not perfect. Since CVaR is the calculation of the mean value of tail losses exceeding VaR, the accuracy of tail loss distribution estimation will directly affect the calculation accuracy of CVaR. However, tail events often mean extreme market conditions, such as financial crisis events, when the correlation between asset prices often deviates from the normal market conditions, which makes it difficult for traditional methods to accurately estimate the distribution of extreme losses, and may affect the reliability of the calculation results of CVaR. In addition, the historical data of extreme market situation is needed when Backtest of CVaR is carried out. However, extreme market situation is an event with small probability and less data, which may also affect the reliability of the test. 

Although CVaR also has disadvantages, it is an indisputable fact that compared with VaR, CVaR has both advantages of VaR and can overcome the disadvantages of VaR. CVaR has become a more superior risk management tool.

