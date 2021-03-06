# Sliding Features
Modular sliding window with various signal processing functions and technical indicators including Normalization. Can be used for building low latency real-time trading systems. Values in window are updated at each time step. A View defines the function which processes the incoming values and provides and output value. Views can easily be added by implementing the View Trait which requires two functions:
- update(&mut self, val: f64)
- last(&self) -> f64

The Views can be parameterized as desired when created with new() function.
Add Views to SlidingWindow by calling register_view().
SlidingWindows last() function returns a vector of all the latest observations of all views that are currently registered. This vector can serve as input to a neural network or decision tree for creating trading agents.


### Views
A View defines the function which processes value updates. They currently include:
- Echo
- Normalizer
- Center of Gravity
- Cyber Cycle
- Laguerre RSI
- Laguerre Filter
- ReFlex
- TrendFlex
- ROC
- RSI
- ALMA (Arnaux Legoux Moving Average)

### How to use
See examples folder.
Run the examples using
```
cargo run --example simple
cargo run --example multiple
cargo run --example multiple_normalized
```

### Images
Underlying data synthetically generated by [MathisWellmann/rust_timeseries_generator](https://www.github.com/MathisWellmann/rust_timeseries_generator)
Note that each run is differently seeded by default.

![laguerre_filter](img/laguerre_filter.png)
![center_of_gravity](img/center_of_gravity.png)
![center_of_gravity_normalized](img/center_of_gravity_normalized.png)
![cyber_cycle](img/cyber_cycle.png)
![laguerre_rsi](img/laguerre_rsi.png)
![re_flex](img/re_flex.png)
![trend_flex](img/trend_flex.png)
![roc](img/roc.png)
![rsi](img/rsi.png)
![alma](img/alma.png)

### TODOs:
- SMA
- EMA
- FRAMA
- MAMA
- FAMA
- Stochastic
- Super Smoother
- Zero Lag
- gaussian filter
