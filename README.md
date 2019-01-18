# esback

The esback package contains function that can be used to backtest
[expected shortfall](https://en.wikipedia.org/wiki/Expected_shortfall) forecasts.

## Installation

### CRAN (stable release)

esback is not on [CRAN](https://cran.r-project.org/) yet.

### GitHub (development)

The latest version of the package is under development at [GitHub](https://github.com/BayerSe/esback). 
You can install the development version using these commands:

    install.packages("devtools")
    devtools::install_github("BayerSe/esback")
    
## Implemented Backtests

These backtests are currently implemented:

* Expected Shortfall Regression Backtest ([Bayer & Dimitriadis, 2018])
* Exceedance Residuals Backtest ([McNeil & Frey, 2000])
* Cummulative Violation Backtests ([Du & Escanciano, 2016] and [Costanzino & Curran, 2015])
* Conditional Calibration Backtest ([Nolde & Ziegel, 2017])

## Examples

    # Load the esback package
    library(esback)
   
    # Load the data
    data(risk_forecasts)
    
    # Plot the returns and expected shortfall forecasts
    plot(risk_forecasts$r, xlab = "Observation Number", ylab = "Return and ES forecasts")
    lines(risk_forecasts$e, col = "red", lwd = 2)
  
    # Backtest the forecast using the ESR test
    esr_backtest(r = risk_forecasts$r, e = risk_forecasts$e, alpha = 0.025, version = 1)

[McNeil & Frey (2000)]: https://doi.org/10.1016/S0927-5398(00)00012-8
[McNeil & Frey, 2000]: https://doi.org/10.1016/S0927-5398(00)00012-8
[Costanzino & Curran (2015)]: https://doi.org/10.21314/JRMV.2015.131
[Costanzino & Curran, 2015]: https://doi.org/10.21314/JRMV.2015.131
[Du & Escanciano (2016)]: https://doi.org/10.1287/mnsc.2015.2342
[Du & Escanciano, 2016]: https://doi.org/10.1287/mnsc.2015.2342
[Nolde & Ziegel (2017)]: https://projecteuclid.org/euclid.aoas/1514430265
[Nolde & Ziegel, 2017]: https://projecteuclid.org/euclid.aoas/1514430265
[Bayer & Dimitriadis (2018)]: https://arxiv.org/abs/1801.04112
[Bayer & Dimitriadis, 2018]: https://arxiv.org/abs/1801.04112
