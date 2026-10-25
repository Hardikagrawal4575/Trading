# Notes: live of 25 Oct 2026 (SshdZH9tj3Q), the live where Eyes FootPrint appears

- Video: https://www.youtube.com/watch?v=SshdZH9tj3Q
- Length: 3:01:28. Sunday, so forex is closed and he trades **BTC/ETH on 1m**, on a TradingView **paper** account (SELL/BUY buttons on screen).
- **Source.** YouTube had no captions, so I transcribed the audio locally with Whisper "small", then re-ran the indicator moments
  more carefully. Both passes are **very garbled**, so the speech notes below are only the parts that came through clearly.
  The screen checks are reliable (1080p frames).

## Proof that this is your indicator

| Time | On screen |
|---|---|
| 25:05 | Legend: **"Eyes FootPrint 50 0 Large"** (Lookback 50, Bubble Size Offset 0, Label Size **Large**), with "Eyes Smart Structure Engine" and a third script ("…Royal Zones…") above it. |
| 2:48:06 | He opens the **Eyes FootPrint settings dialog**. Inputs match `eyes_footprint_original.pine`: 75% Upper Quartile (green), 50% Structural Pivot (grey), 25% Lower Quartile (red), 0% Buyers Defense (green). Enable Bubbles **on**; Outer – Volume Mass **off**; Inner – Delta Pressure **on** (▲ green / ▼ red); Bubble Size Offset **0**; Show Volume and Delta Labels **on**; Label Size **Normal**. Legend now reads "Eyes FootPrint 50 0 Normal". |

**His settings vs the file's defaults:** everything is default except Label Size. He uses Normal or Large; the file's default is Small.

## What the bubbles look like in use

| Time | Chart | What's on screen |
|---|---|---|
| 36:24 | BTC 1m | Sharp drop with **big red bubbles** (numbers inside) on the falling candles. Then a **big green bubble at the low**, on the green 0% line. A long position is drawn from that low, and he sketches the bounce. |
| 39:42 | BTC 1m | Same trade, later: price has rallied through the long's target area. The big red bubbles from the drop and the green bubble at the low are still visible. |
| 1:27:47 | ETH 1m | **Red bubbles at the swing high** and a **large red bubble at the low**. A short position is drawn after the top, with his pen sketch of price going down. |
| 2:10:40 | BTC 1m | Rally with a **run of green bubbles** on the candles making new highs; he **circles the top bubble**. |
| 2:11:04 | BTC 1m | Many bubbles: **large red bubbles along the drop from the top**, green bubbles at the lows; an FRVP is also drawn on the move. |
| 2:47:08 | BTC 1m | Eyes FootPrint **lines visible**: red dotted 100% at the top, green 75%, grey 50%, red 25%, green dotted 0%, all stepping with price. Green bubbles on the rally, red bubbles on the fall. |

## What he says (only the parts the transcription caught clearly)

- **2:11:00–2:11:06:** the **red bubble at the top** is where you could have sold; the **green bubble below** is where you could have taken the buy profit.
- **2:10:35–2:10:41 (rough):** when price fills/comes back and you see a **selling bubble**, it means **buyers are trapped**.
- **2:47:04–2:47:12 (rough):** green bubble / red bubble; there is a "method" to read them, which he says he'll teach later.
- **2:48:17 (rough):** explains that the numbers in the bubble are worth reading, but the detail is garbled. **Unclear.**
- **25:02, 29:51, 36:16 (rough):** with it you can see in advance how much buying and selling is happening in a candle.
- **39:35–39:47 (rough):** a viewer calls it a "bubble indicator". He says he'll give this indicator to everyone **free**, but you have to learn how to use it.
- **44:03 (rough):** it's free, not paid.
- **2:16:37–2:16:55, 2:21:30–2:25:56 (rough):**
  - He'll teach how to use it.
  - He'll share it (and apparently the **source code**) on **Telegram** once a like target is reached.
  - Don't resell it or publish it under your own name.
  - The indicator has bubbles, sizes and labels.
  - Check how to apply it before using it.
- **2:41:30 (rough):** settings are simple; he'll start teaching how to use it **from tomorrow**.

## How he appears to use it (from screen + the clear lines)

1. **Reversal at the range extremes.** A **red bubble at/near the top** (100% "Sellers Defense", or a new high) is his sell cue.
   A **green bubble at/near the bottom** (0% "Buyers Defense") is his buy cue (2:11:00; screens at 36:24, 1:27:47).
2. **Trapped-side read.** A **bubble of the opposite colour** after a move means that side is trapped (e.g. a selling bubble
   after a rally = buyers trapped). Rough audio (2:10:35); **needs confirmation**.
3. **Big bubbles matter more** than small dots (his circled/traded examples are the large ones), but he gives no explicit size rule. **Unclear.**
4. **Still combined with his usual tools:** FRVP on the move (2:11:04), drawn zones and position boxes, and the paid
   Eyes Smart Structure Engine on the same chart.
5. **No SL/TP rules tied to the bubbles** were captured. His examples use the position tool (SL beyond the bubble's
   high/low, target toward the other side of the range). **Unclear; not stated.**

## How this compares with the code

- **Bubbles at extremes are partly mechanical.** On 1m, every new 50-bar high or low "touches" the 100% or 0% line, so a bubble
  appears there on almost every push. A rally makes a run of bubbles, as at 2:10:40. They are **not** independent order-flow
  events, and on the live bar they can change until it closes.
- **Colour = 1m candle colour × volume.** On a 1m chart the lower timeframe equals the chart timeframe, so each bar's "delta"
  is essentially that bar's own volume, + if green, − if red. A red bubble at a top means a red (down-closing) candle touched
  the line; a green bubble at the low means a green candle touched it. That is close to "rejection candle at the extreme",
  not real buyer/seller pressure.
  - Note: the script's tooltip says to set the LTF *below* the chart timeframe. On a 1m chart it can't be; see HANDOFF.
- **The numbers inside** are the bar's volume (top) and that ± "delta" (bottom). On BTC "INDEX" the volume is the index feed's
  volume; on XAUUSD it would be broker tick volume.
- **Bookmap vs Eyes FootPrint.** His Bookmap bubbles (other lives) are real order flow on crypto. Eyes FootPrint's bubbles
  imitate the look, not the data.

## Open items

- He says the proper "how to read the bubbles" lesson starts **tomorrow (26 Oct)**. That live, once captioned, should give
  the actual rules.
