Value - Momentum
=====
This is a modified and updated algorithm based on Quantopian user Johhny Wu's trading algorithm. Quantopian has deprecated get_fundamentals method, so the code is modified to make use of the faster pipeline functionality. The original discussion can be found in [Quantopian](https://www.quantopian.com/posts/ev-slash-ebitda-value-then-momentum?r=1&b=5a1bacbf17595f419d6e2bca#reply).

How it works
* Stocks are ranked based on EV/EBITDA ratio (Crudely, high means overvalued and low means undervalued, similar to PE ratio)
* Choose _n_ stocks with the lowest EV/EBITDA ratio
* Choose the _m_ (_< n_) stocks with highest momentum 
* Rebalance monthly, equal weighted

![Backtest result](https://raw.githubusercontent.com/j24ohuw/Trading-Algos/master/EvEbitda%20Momentum/2003-02-03%20to%202015-05-21.PNG)
-----
Most of the algorithm's out-performance comes from previous decade. It underperforms against the benchmark (SPX) in the current decade due to the progressively worsening performance of the value factor. This phenomenon is well described [#### here](https://www.msci.com/www/blog-posts/the-value-factor-marks-a-decade/0313945437). Sorting by EV/EBITDA in descending order and applying momentum seems to achieve a small edge between Jan 2014 to Nov 2017.
