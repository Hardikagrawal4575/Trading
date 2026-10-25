# Handoff: Eyes FootPrint indicator — study the YouTuber's live strategy

You are continuing work started in a cloud session that could not reach YouTube or the
user's browser. This session runs on the user's own computer with the Claude in Chrome
extension connected, so use Chrome for the YouTube work below.

## Setup

- Repo: `hardikagrawal4575/trading`, branch `claude/elegant-ptolemy-6sk6ls`.
  Fetch it first: `git fetch origin claude/elegant-ptolemy-6sk6ls && git checkout claude/elegant-ptolemy-6sk6ls`
- Indicator source (unmodified, the user's backup — never edit this file):
  `indicators/eyes_footprint_original.pine`.
  Any future changes go in a separate new file.

## The user

- Trades **forex gold (XAUUSD)**.
- TradingView plan: **Free**.
- Follows the strategy of YouTuber **https://www.youtube.com/@eyesbaadshah369**, who
  provided this indicator. Content is likely in Hindi.
- Wants the flow driven by them: ask before deciding things; don't assume.

## Your task now

1. In Chrome, open the channel's **Live** tab (https://www.youtube.com/@eyesbaadshah369/streams)
   and go through the **latest** live streams about this indicator.
2. For each live: get the transcript (description → "Show transcript", or auto-captions),
   and **read his screen** — what's on the chart when he talks (which quartile line,
   bubble colour/size, volume/delta labels, timeframe, symbol, candle behaviour).
   Match what he says to what the chart shows at that moment.
3. Take **entry rules, stop-loss and targets only from what he says/shows in the lives**.
   Don't fill gaps with generic order-flow theory; mark anything unclear as unclear,
   with the video and timestamp.
4. Write a full strategy write-up: every setup with conditions, entries, SL, targets,
   timeframe, session/time-of-day, filters, what he avoids, worked examples with
   video links + timestamps, and any settings he uses for the indicator.
5. **Do not modify the script.** The user wants to understand the whole structure first;
   they'll say later what to develop.

## What's already established about the script (from code review)

- **Not true footprint data.** It uses `request.security_lower_tf` on 1-minute candles.
  "Delta" = each 1m candle's whole volume counted as buy if green, sell if red.
  "POC" = hlc3 of the highest-volume 1m candle, not a true price-level POC.
- **Five levels** from the last 50 bars (Lookback): 100% "Sellers Defense" = highest high,
  75%, 50% "Structural Pivot", 25%, 0% "Buyers Defense" = lowest low. The "Defense" names
  are labels only, not order-flow derived.
- **Bubbles appear only on bars whose range crosses one of the five lines.** Big activity
  between lines gets no bubble.
- **Bubble colour:** green if delta > 0, else red (delta = 0 shows red).
- **Bubble size:** |delta| percentile vs last 50 bars, but non-touch bars count as 0 delta,
  so touch bars rank high easily; inner (delta) size is capped at volume tier − 1, so size
  mostly follows volume. Outer "Volume Mass" bubble is off by default.
- **Repaints on the live bar:** levels include the current bar's high/low, so any bar
  making a new 50-bar high/low "touches" 100%/0%; last-bar bubbles can change until close.
- Needs a chart timeframe above 1m (default LTF = 1m). Only ~the last 25 bubbles get
  labels (TradingView's ~50 label limit).
- **Gold-specific:** XAUUSD on TradingView has only broker **tick volume** (count of price
  changes), not real traded volume, so volume/delta are approximations. COMEX `GC1!` has
  real volume but it's delayed on Free.
- **Free plan:** no `request.footprint()` (Premium+ only); fewer bars of 1m history, so on
  older bars the script may fall back to whole-candle colour = delta.

When you compare his explanations to the code, point out where what he claims the
indicator shows differs from what the code actually computes.
