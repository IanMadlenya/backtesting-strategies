---
title: What is backtesting?
subtitle: A brief look at backtesting and why it is important.
output:
  html_document:
    toc: false
    toc_float: false
---

Backtesting trading strategies can be an exciting (and profitable) method of exploring the stock market. It is a method of mining market data to find patterns and conditions that may precede another event from occuring (a market rally or a market collapse). 

__IT ISN'T WHAT YOU THINK IT IS__

Backtesting trading strategies is not easy. It begins with an idea (usually obtained from data mining but can be something as simple as curiousity). The idea is converted to a script or program. The results are analyzed. The idea is discarded (non-profitable), slightly modified, or moved into a testing phase. 

If you do a search on Twitter such as "$AAPL" you will see thousands of people posting their ideas on what they think AAPL is going to do:

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Short <a href="https://twitter.com/search?q=%24AAPL&amp;src=ctag">$AAPL</a> here. Thank me later.</p>&mdash; Arduous Investor (@PapaSmurf100000) <a href="https://twitter.com/PapaSmurf100000/status/828979857241624577">February 7, 2017</a></blockquote>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">A lot can happen from now till year&#39;s end But <a href="https://twitter.com/search?q=%24aapl&amp;src=ctag">$aapl</a> chart implies 165 by december</p>&mdash; Chart_Guy (@Chart_Guy) <a href="https://twitter.com/Chart_Guy/status/828977586978058241">February 7, 2017</a></blockquote>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">adding <a href="https://twitter.com/search?q=%24AAPL&amp;src=ctag">$AAPL</a> to 1% scalp list. looks good</p>&mdash; NorthPost Partners (@NPPtrades) <a href="https://twitter.com/NPPtrades/status/828976104350240769">February 7, 2017</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

I'm not trying to call anyone out here or suggest they're wrong. But in just a few minutes I found three sides of a trade: bearish, neutral, and bullish. But what makes @PapaSmurf100000 correct? Or, are they wrong and @NPPtrades is correct? Is @Chart_Guy onto something?

On any given day there are billions of signals given that triggers buys and sells. That's what moves the market. A trader in NYC sees a doji candlestick after a 1% drop and goes long. A trader in Chicago sees that doji, anticipates a slight midday correction and then adds to their short. An amateur in Junction City, Kansas just sees their account go red, panics, and liquidates the position.

Trading the stock market is an emotionally intensive exercise. When I first started trading in 2008 (yup!) I couldn't tell you how many times I would get down in the dumps for making a losing trade only to feel rejuvenated when I made a profitable trade. 

Backtesting gives us a way to remove those emotions and instill confidence. Additionally, it helps us define rules for a specific strategy:

    1. Wait for a doji candle
    
    2. Buy on the next bar that exceeds the high of the doji candle. 
    
    3. Sell on the close of the third bar.

Is this strategy profitable? I honestly don't know. But it's an idea. We can test it. If it passes all tests, we can move it to a paper trading environment under real life conditions. If those tests pass, we can move it to a live account.

In short, we developed an algorithm. We can let the computers do the work and monitor daily, weekly and monthly reports to make sure there are no inconsistencies.

__PITFALLS OF BACKTESTING__

A couple of years ago I had written a strategy based on NR7: 

    * The last bar (Bar -1) is the smallest trading range of the preceeding six bars
    
    * Buy if the current bar exceeds the high of Bar -1 **OR** short if current bar exceeds the low of Bar -1. 
    
    * Close in $n$ days.

When I ran the equity analysis I was stunned; it showed a significant profit margin with very little drawdown (relatively speaking). I was very anxious to move it to a paper trading account. But I knew I had to be careful. 

When you find a strategy that seems successful your priorities **must** change. You have to put on your scientist hat. You no longer are trying to find a strategy that is profitable in the market: it becomes your job to *prove it doesn't work*. 

There are several reasons for this. First, and generally, most likely, you have an error in your script. In my case, I thought I had written the strategy to close in $n$ days. Instead, I kept buying. Second, your timeframe may be inadequate. When testing you need to have several years of data to test the strategy against. And this time frame must include not only when the ticker is rallying but selling off as well (any long strategy can be made profitable in a bull market). 

What you are trying to avoid is __confirmation bias__. In short, this is finding the proof to believe what you want to believe and ignoring the proof that invalidates your strategy. This is why we put our scientific hats on. In the science community, when a potential new discovery is made the scientist seeks anonymous peer review to validate that discovery. The data, tests and results are examined thoroughly by knowledgeable scientists; picked apart with a fine-tooth comb, seeking a desire to find the smallest error that invalidates the results (or, at least, require additional testing). 

As most of us will never want to share potentially profitable strategies with an anonymous community, it is up to you to do this work on your own. 
