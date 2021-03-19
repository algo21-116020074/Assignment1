# Assignment1: Mean-CoVaR Model to Optimize Portfolio

**Abstract**  
  
When used in risk measurement, CVaR not only takes into account the frequency of exceeding VaR value, but also the average loss exceeding VaR value. The measurement of tail loss is sufficient. A portfolio optimization model based on tail risk is constructed using CVAR and co-skewness matrix, and the portfolio optimization model is empirically tested using the underlying assets in the paper, which preliminarily verifies the effectiveness of the portfolio optimization model.  
   

**Background** 
  
According to Modern Portfolio Theory(MPT), investors should diversify the investment to realise the minimum risk and maximum return. Traditionally, we often use Markowitz’s effective frontier theory, which is the `Mean-Variance`, to achieve such investment goals. Mean-Variance model laid the cornerstone of modern portfolio theory, but with the change in the definition of risk, the problem of portfolio construction has been continuously revised. _Research by Bertocchi showed that the investment portfolio constructed through the classic mean-variance framework may lack optimality and fail to correctly identify the impact of the `non-normal`distribution of asset returns on risk._(Bertocchi M, 2005) The return on financial assets often exhibits the characteristics of non-normal distribution with `sharp kurtosis`, `thick tails` and `negative skewness`. Therefore, the use of variance to measure the risk of assets is not completely accurate.   
Subsequent `VaR`(Value at Risk) theory was put forward, which can effectively measure the tail risk of financial assets. Under a given probability level, the maximum loss that the portfolio may have in a certain period of time.  
However, VaR does not satisfy convexity and subadditivity, and is not a consistent risk measurement indicator. That is, when VaR is used as a risk measurement indicator, the risk of the portfolio is not necessarily less than the maximum value of the asset risks, which does not conform to risk diversification. Market principles and economic significance of globalization. Therefore, Rockafeller and Uryasev proposed the conditional value at risk
(`CVAR`), refers to the average loss value of the investment portfolio under the condition that the loss of the investment portfolio exceeds a given VaR value. CVAR can more accurately characterize the tail risk of the investment portfolio, and satisfies `subadditivity`, `positive homogeneity`, `monotonicity` and `translation invariance`, and is a `consistent risk measurement indicator`.   
  
  
**Verification Process**  
  
The top 6 weighted stocks in the SSE 50 Index are used as the underlying assets, namely: Ping An of China (600318), China Merchants Bank (600036), Kweichow Moutai (600519), Industrial Bank (601166), Minsheng Bank (600016) and Bank of Communications (601328). I chose a period of time closer to today, which is between 2015-01-01 and 2020-12-31. The specific code and process are in the `Mean-CoVaR.ipython`.   
The estimation method used is `Monte Carlo simulation` to optimize the Mean-Variance and Mean-CVaR models respectively. Substitute the results of the optimal portfolio weight allocation in the Mean-Variance model to the CoVaR formula, push back the CoVaR value of its portfolio, and convert the Mean-Variance efficiency frontier from the original rate of return-standard deviation coordinate space into the rate of return-CoVaR values, therefore, we can compare these two models in the same coordinate space.   
  
**Conclusions**  
  
The research conclusions of this article are a powerful supplement to China's investment portfolio theory, and at the same time have certain practical reference value for investors: although volatility is a common indicator to measure investment risk, it is not the most effective indicator because when assets fluctuate upwards, it can often bring higher investment returns to investors. Therefore, when constructing investment portfolios, the downside risks of assets should be considered, especially to increase the management of tail risks. For example, the CVAR minimization model used in this article can be used in The portfolio optimization process reduces the tail risk of the portfolio, so that the risk-adjusted return of the portfolio.  
  
However, CVaR is not perfect. Since CVaR is the calculation of the mean value of tail losses exceeding VaR, the accuracy of tail loss distribution estimation will directly affect the calculation accuracy of CVaR. However, tail events often mean extreme market conditions, such as financial crisis events, when the correlation between asset prices often deviates from the normal market conditions, which makes it difficult for traditional methods to accurately estimate the distribution of extreme losses, and may affect the reliability of the calculation results of CVaR. In addition, the historical data of extreme market situation is needed when Backtest of CVaR is carried out. However, extreme market situation is an event with small probability and less data, which may also affect the reliability of the test.   
  
Although CVaR also has disadvantages, it is an indisputable fact that compared with VaR, CVaR has both advantages of VaR and can overcome the disadvantages of VaR. CVaR has become a more superior risk management tool.

**Reference**  
  
Bertocchi M, Giacometti R, Ortobelli S, et al. _The Impact of Different Distributional Hypotheses on Returns in Asset Allocation[J]._ Finance Letters, 2005, 3(1): p17-p27.  
