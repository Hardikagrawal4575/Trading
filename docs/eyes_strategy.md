# Eyes Baadshah: strategy write-up from his live streams

Study of the five most recent lives on https://www.youtube.com/@eyesbaadshah369/streams, done to understand
the strategy around the **Eyes FootPrint** indicator (`indicators/eyes_footprint_original.pine`, unmodified).

| Live | Link | Length | Notes file |
|---|---|---|---|
| 20 Oct 2026 (titled "19 Oct") | https://www.youtube.com/watch?v=6VTHI15UG4w | 2:06 | `transcripts/notes_2026-10-20_6VTHI15UG4w.md` + full transcript |
| 21 Oct 2026 (titled "19 Oct") | https://www.youtube.com/watch?v=b0NAPRNyoxA | 2:02 | `transcripts/notes_2026-10-21_b0NAPRNyoxA.md` |
| 22 Oct 2026 | https://www.youtube.com/watch?v=vZ2AWxKhLw0 | 2:33 | `transcripts/notes_2026-10-22_vZ2AWxKhLw0.md` |
| 23 Oct 2026 | https://www.youtube.com/watch?v=A3-hEpzHkmk | 2:34 | `transcripts/notes_2026-10-23_A3-hEpzHkmk.md` |
| 24 Oct 2026 (Saturday) | https://www.youtube.com/watch?v=mfVj251fsQc | 3:52 | `transcripts/notes_2026-10-24_mfVj251fsQc.md` + full transcript |

The 25 Oct live was skipped because it had no captions yet.

**How this was made.** I read the YouTube Hindi auto-captions for each live, then checked his screen at the key moments
(1080p frames, list in §9). Rules below come **only from what he says or shows**. Anything he doesn't explain is marked **Unclear**.
Times are `h:mm:ss` into the video.

**Caveats.**
- Auto-captions garble terms. For example "एफबीजी" = FVG, "फैक्टल" = "fractal" (his word for multi-timeframe trend), "सीबी" = imbalance flip.
- The 24 Oct trades were on a **TradingView paper account** (he says so).
- Win-rate and P&L claims (8/10 wins, "never a losing day", account tripled) are his own and unverified.
- Long promotional parts (Telegram, brokers, copy-trading bot, his paid indicator, a cash card) are left out.

---

## 1. Main finding: Eyes FootPrint does not appear in these lives

- **He never names "Eyes FootPrint"** in any of the five transcripts.
- **None of the 14 frames I checked show it.** No five quartile lines, no delta bubbles. His charts are TradingView
  (Gold TVC, EURUSD FXCM, BTC INDEX) with hand-drawn zones and the tools below.
- His **red / black / green zones** come from TradingView's free **Fixed Range Volume Profile (FRVP)**: Value Area High,
  POC and Value Area Low. He says so repeatedly (21 Oct 43:14, 1:29:41; 23 Oct 19:17, 1:07:15; 20 Oct 45:39) and it's
  confirmed on screen (23 Oct 24:05, 1:08:15).
- The **"bubbles" / "footprint data"** he talks about are **Bookmap**, a separate order-flow app he uses on crypto
  (21 Oct 44:11; 23 Oct 30:05; 24 Oct 1:15:05; 20 Oct 1:23:33).
- The indicator he shows on charts is a **different, paid script: "Eyes Smart Structure Engine"** (legend on screen
  "Eyes Smart Structure Engine 4 20 1.5", 22 Oct 1:57:06). It draws a trend ribbon, coloured candles and zones, and gives
  top/bottom buy-sell signals.
- **Both "50% zone" mentions are hand-drawn.** One is the middle of a box he drew (EURUSD, 21 Oct 1:48:43); the other is
  a box/leg midpoint (BTC, 23 Oct 14:08). He also uses a 0 / 0.5 / 1 "fib box" to mark the 50% of a leg (24 Oct 1:43:31).

So the method in these lives is **ICT/SMC + FRVP zones + Bookmap order flow**. Eyes FootPrint looks like his attempt to put
"zones + bubbles" into one free TradingView script (see §8 for how it differs).

---

## 2. Tools and settings he uses

### 2.1 Fixed Range Volume Profile (TradingView, free)
**Settings, read off his screen on 23 Oct at 1:08:15–1:08:23.** He gives the same spoken settings on 20 Oct (57:37) and 21 Oct (45:27).

| Tab | Setting | Value |
|---|---|---|
| Inputs | Rows Layout | Number of rows |
| Inputs | Row Size | **50** |
| Inputs | Volume | **Up/Down** (not Delta, 20 Oct 57:53) |
| Inputs | Value Area Volume | **70** |
| Inputs | Extend Right | **On** |
| Style | Volume profile / Values | On / On |
| Style | Width (% of box) | 30, Placement **Left** |
| Style | Up / Down volume | teal / pink |
| Style | Value area up / down | teal / red |
| Style | **VAH line** | On, **red** |
| Style | **VAL line** | On, **green** |
| Style | **POC line** | On, **black** |
| Style | (two other line options) | Off (20 Oct 1:26:12) |

**How he draws it** (21 Oct 43:14; 23 Oct 22:21; 24 Oct 1:47:45; 20 Oct 56:58, 1:20:33):
- Wait for a **big impulsive move**, typically right after a consolidation.
- Apply FRVP across that move, **from its low to its high**. It's the "last major swing".
- Best practice: draw it on a **higher TF**, then trade on a lower TF. His pairings are 15m→5m, 5m→1m, 1H→15m
  (20 Oct 1:19:42; 23 Oct 1:37:11).

**What the three lines mean to him:**
- **Red (VAH):** sell only *above* it.
- **Green (VAL):** buy only *below* it, not just at it (20 Oct 58:08, 1:04:21).
- **Black (POC):** the target. He calls the POC a "magnet" that pulls price back (21 Oct 43:39; 20 Oct 1:06:42).
- **Never trade in the middle**, between the lines (21 Oct 44:02).

### 2.2 Bookmap (order flow / "heatmap", crypto only for free)
- He uses it at a zone to confirm the entry: was there a real liquidity sweep, absorption, or trapped buyers/sellers?
  It shows large resting or market orders (e.g. 30 or 44 lots sold at a wick).
  (21 Oct 44:11–45:00; 24 Oct 32:34–34:20, 2:17:42; 20 Oct 1:21:12–1:25:05, 1:35:22–1:42:15)
- It's free for crypto; gold/forex data needs a paid plan (24 Oct 40:18; 20 Oct 1:39:20).
- He says footprint / Bookmap is **for confirmation only**; the trade itself comes from the "fractal" and the zones
  (24 Oct 2:40:31).

### 2.3 "Malaysian fib" (TradingView Fib Retracement, custom levels)
- Levels on screen (23 Oct 1:10:08), ticked: **0, 1.47, 2.6, 1.55, 2.56, 2.64, 1, −0.23, −0.2, −0.29**. A second 0 and −6.25 are unticked.
- **Use:** find a liquidity-sweep zone, draw from that low to the high, and sell when price reverses from the fib zone.
  He claims 1:20–1:30 targets (23 Oct 1:08:57–1:12:47). **Unclear** which level is the entry and why these numbers.

### 2.4 "Fib box" (0 / 0.5 / 1)
- Marks the 50% of a leg. Sell in the **premium** (above 50%), buy in the **discount** (below 50%)
  (24 Oct 1:41:54–1:43:31, screen 1:43:31).

### 2.5 Paid "Eyes Smart Structure Engine"
- Has a signal setting: **1.5 on 1m, 1 on 5m** (24 Oct 3:16:49). Fewer signals in sideways markets (22 Oct 53:16).
- He says buyers get extra rules to filter its signals.
- Used for the 24 Oct recovery trade (3:30:15). It's a different script from Eyes FootPrint.

---

## 3. Bias: the "fractal" (multi-timeframe trend)

He trades **only in the direction of the higher-timeframe bias** (21 Oct 33:40–34:04, 50:25–50:48; 20 Oct 8:13–8:48).

1. **Starting timeframe** (21 Oct 57:38): weekly for scalping/intraday, monthly for swing, 6-month for long-term.
2. **Go down the timeframes**: W → D → 4H → 1H → 15m → 5m (sometimes 1m). On each, ask whether price took the
   previous candle's high or low. His rule (he calls it CRT): if a candle's **low** is swept, price "must" go for that
   candle's **high**, and vice versa (21 Oct 58:02–58:25; 24 Oct 6:07–6:54).
3. **Daily close above the previous day → buyers bullish**, and vice versa (21 Oct 58:39).
4. **All TFs aligned = fractal.** Bullish fractal → **buy only, below the green zone**. Bearish → **sell only, above the red zone**.
   He says even big counter-moves should not be traded (21 Oct 1:00:23–1:01:06).
5. **His exception:** he himself sometimes takes counter-trend pullbacks, but tells followers not to
   (20 Oct 1:09:10–1:10:21; 24 Oct 1:09:36–1:10:22).

---

## 4. Liquidity concepts he relies on

- **BSL / SSL:** every swing high is buy-side liquidity, every swing low is sell-side liquidity. After BSL is taken, price
  "has to" go for SSL (20 Oct 1:13:07–1:15:19; 23 Oct 2:15; 24 Oct 2:24:58).
- **Equal highs/lows:** a level tapped three or more times is liquidity. Retail buys/sells it, so he trades the opposite way,
  and puts targets at those taps (22 Oct 11:19–12:56; 20 Oct 14:03).
- **Stop-hunt rule:** before a big fall, price first makes a big move up to take stops, and vice versa
  (21 Oct 0:59; 22 Oct 29:46; 24 Oct 24:26).
- **SMT divergence (crypto):** if BTC sweeps a level and ETH doesn't (or the reverse), trade the one that didn't sweep
  (22 Oct 1:05:02; 24 Oct 44:30).
- **Order block / FVG as POI:** POIs are higher-TF (4H) order blocks, FVGs and liquidity pools (24 Oct 16:12).

---

## 5. Setups

### Setup A: FRVP red-zone short (his main gold setup in these lives)
| | Rule | Source |
|---|---|---|
| Bias | Bearish fractal (gold was "sell only" all week) | 21 Oct 12:19; 20 Oct 4:03 |
| Zone | Price goes **above the red line (VAH)** of an FRVP drawn on the last impulse, ideally into a 4H/1H order block or minor BSL | 21 Oct 43:31; 20 Oct 1:10:53, 1:31:24 |
| Trigger (one of) | **Liquidity grab above, then a red candle closes** (1m/5m) → enter at that candle's low | 23 Oct 23:55, 1:30:46, 1:37:59 |
| | **Close back below** the level (CISD/MSS), then **FVG forms → sell the FVG on the pullback** | 21 Oct 4:36, 16:07; 20 Oct 1:53:53 |
| | **Rejection** from the FVG/zone | 21 Oct 17:37 |
| | Bookmap shows **sellers stepping in / absorption** (crypto) | 21 Oct 44:26 |
| SL | Just above the high of the setup/entry candle. He accepts a "slightly bigger" SL for double confirmation (gold ≈ $4 in his 21 Oct trade) | 21 Oct 19:07–19:15; 23 Oct 8:40 |
| TP | TP1 = **POC (black line)**; TP2 = green line / next zone; then sell-side lows. Expected ≈1:3 | 21 Oct 20:43, 44:54; 23 Oct 24:09 |
| Skip if | No FVG formed after the close (20 Oct 52:41); price is still **below** the red zone (20 Oct 1:49:40); price is in the middle of the range | |

**Variant (24 Oct 1:22:59–1:29:14, BTC, paper):** price closes back **below** the red zone, then **retests** it from below. Sell the retest;
SL above; TP at the zone below.

### Setup B: FRVP green-zone long (mirror)
- **Bias:** bullish fractal (examples on EURUSD and BTC).
- **Zone:** price **below the green line (VAL)**, plus a POI / order block.
- **Trigger:** structure shift / sweep, or Bookmap showing **sellers trapped**.
- **SL:** below the low. **TP:** POC, then red line, then trail.
- Sources: 21 Oct 53:47–54:12; 20 Oct 1:04:21; 24 Oct 1:07:50.

### Setup C: Liquidity sweep → structure shift → FVG pullback (the general model he teaches)
1. Mark the HTF POI and the liquidity (BSL/SSL).
2. Wait for price to **sweep** it.
3. Drop to 5m/1m and wait for a **structure shift with a candle close**. A wick doesn't count (24 Oct 20:16–20:41).
4. Wait for an **FVG** to form (three-candle gap; 20 Oct 1:58:16).
5. Enter on the **pullback into the FVG**, or **on the break of the low** after the FVG is tapped (20 Oct 1:59:29, 1:00:04).
6. SL above the swing high; TPs at successive SSLs.

Sources: 20 Oct 7:09; 21 Oct 10:00–10:58; 22 Oct 17:58–19:38.

**Definitions he gives:**
- **CHoCH** = break of the last BOS leg's low after an inducement sweep (22 Oct 9:12).
- **CISD** = close below the *body* of the low; it comes first.
- **MSS** = close below the *wick*. CISD only counts at liquidity or a POI (22 Oct 17:58–19:38).

### Setup D: 50% of the leg (premium/discount)
- Use the fib box (0/0.5/1) on the leg or zone. Enter a sell above 50% or a buy below 50%. If the pullback doesn't reach the
  zone, use the 50% of the impulse candle.
- Sources: 24 Oct 12:58–13:22, 1:38:34, 1:41:54.

### Setup E: Bookmap absorption scalp (crypto)
- At a POI, watch Bookmap. If there's a big bubble at the wick (e.g. 30–44 lots) and the move stalls, sellers (or buyers)
  are trapped.
- Enter on the next reversal candle, with a very small SL; take a quick 1:1.5–1:4 and exit.
- Sources: 20 Oct 1:23:07–1:25:05, 1:35:22; 23 Oct 1:36:23; 24 Oct 2:17:42.

### Setup F: SMT divergence (BTC/ETH)
- Trade the coin where SMT formed, after a CISD, on the pullback. Example: ETH long at about 1:3 RR.
- Sources: 22 Oct 1:05:02–1:06:39; 24 Oct 11:56–12:49, 44:30.

### Time rule (used as a filter)
- After a sweep, if price can't **close back above** the level within about **20 minutes** (four 5m candles), expect the move
  down. He also waits for the 1H candle to close before acting (24 Oct 1:51:19–1:55:26; 20 Oct 30:30; 22 Oct 20:40).
- He calls this "timing zones" / his own maths. **Unclear**, not explained (24 Oct 2:18:39–2:20:50).

---

## 6. Trade management, risk and sizing

**Partial booking (his core rule):**
- At **1:1 – 1:2** (most often "1:1.2"), **book 50%** and move the SL to cost ("CTC").
- Hold the rest to the bigger target and **trail**. A later stop-out then costs roughly nothing.
- Sources: 21 Oct 23:11–24:11, 33:00; 22 Oct 2:36, 45:46; 20 Oct 19:52–21:11, 1:21:51; 24 Oct 2:29:05.

**Book a second chunk:** after more profit, book another half of the remainder (21 Oct 34:56).

**Targets:**
- First target 1:2 is also mentioned (22 Oct 2:08:49).
- Targets sit at liquidity: equal highs/lows, SSL/BSL (22 Oct 11:19).

**Stops:**
- "SL should be fixed, TP should not."
- About 50–70 pips max on gold; the SL is bigger when volume and candles are big (22 Oct 1:23:51–1:24:38).
- Exit the short only if price **closes above** the invalidation line; before that, hold (24 Oct 2:24:38–2:28:26).
- If the SL hits but the bias hasn't changed, **re-enter** with a new SL (21 Oct 29:29). He contradicts this on 22 Oct 7:03, where
  he says not to chase re-entries. **Contradiction**.

**Sizing:**
- Risk under **1% of capital** per trade (20 Oct 21:18).
- Small accounts: risk $2–3 of $30; lot 0.01–0.02, so half can be booked (24 Oct 2:04:57, 2:50:51).
- Cent account for small capital (21 Oct 37:50).

**Counter-trend scaling:** with **big capital only**, he keeps adding sells as price rises. He tells small accounts not to
(20 Oct 1:22:15).

**Hedging / "recycle & rebalance":** small opposite positions on pullbacks. He refuses to explain it to beginners
(21 Oct 28:10, 37:01; 23 Oct 1:05:54). **Unclear.**

---

## 7. Timeframes, sessions, news, what he avoids

- **Timeframes:** bias W/D/4H/1H; setup 15m/5m; entry 5m or 1m. FRVP drawn on the higher TF, executed on the lower.
  He says gold and EURUSD are his main markets; EURUSD is his "favourite" and cleanest chart (21 Oct 52:39; 20 Oct 57:05).
- **Session:**
  - He goes live about **3:00–3:30 pm**, assumed IST, for 2–4 hours. He plans 2–6 pm sessions.
  - He says the market moves little during his live hours (22 Oct 1:11:18), so most trades go to Telegram.
  - He gives **no specific killzone or session rule**. **Unclear.**
- **Days:**
  - **No real trading Saturday/Sunday** (low volume); the 24 Oct trades were paper.
  - Trade **Monday–Friday** (24 Oct 2:04:15, 3:07:43).
- **News:**
  - Don't chase minor news (23 Oct 3:16; 22 Oct 1:33:59).
  - He mentions CPI on the 28th.
  - **No rule** for trading around red news. **Unclear.**
- **What he avoids:**
  - Trading in the middle of the FRVP range.
  - Buying against a bearish fractal.
  - Entering on boxes or zones without a pattern or confirmation (22 Oct 1:21:36).
  - Entering on a big signal candle; wait for a small candle instead (23 Oct 21:08).
  - FOMO.
  - Plain support/resistance and trend lines (22 Oct 1:23:06; 24 Oct 10:19).
  - Chasing his late entries (22 Oct 1:13:10).
  - Selling gold when it's "oversold" (22 Oct 1:52:19).

---

## 8. What Eyes FootPrint actually computes vs. what his method needs

| His method (from the lives) | Eyes FootPrint (`eyes_footprint_original.pine`) |
|---|---|
| Zones = **FRVP on a hand-picked impulse**: POC (most traded price), VAH/VAL (70% value area). | Five lines from the **last 50 bars' highest high / lowest low**: 0, 25, 50, 75, 100%. No volume profile, no POC/VAH/VAL. Lines move every bar. |
| Red line above (sell), black POC in the middle (target), green below (buy). | Similar colour layout: 100% red (dotted) at the top, 50% grey in the middle, 0% green (dotted) at the bottom; 75% is green, 25% red. But the 50% line is the **range midpoint**, not the POC, and the 0/100% lines are just the 50-bar extremes. |
| "Bubbles" = **Bookmap**: real order book / traded volume on crypto, showing absorption and trapped traders at the wick. | Bubbles only on bars whose range **touches one of the five lines**. "Delta" = each 1m candle's whole volume counted + if green, − if red. On XAUUSD that volume is **broker tick count**. Bubble placed at the hlc3 of the busiest 1m candle. |
| Entry confirmation: sweep, then **close** below/above, FVG, rejection candle, absorption. | No sweep, structure, FVG or close logic. Bubbles on the live bar can change until close; any new 50-bar high/low "touches" 100%/0%. |
| "50% zone" = 50% of a **leg or zone he picks** (fib box). | 50% = midpoint of the rolling 50-bar range. |
| Works on 1m–5m for entries. | Needs a chart TF above 1m (default LTF = 1m). On Free plan, older bars may lack 1m data. |

**Partly matches:** the colour scheme and the "sell high in the range / buy low / target the middle" idea.

**Doesn't match:** where the levels come from (impulse-anchored volume vs rolling 50-bar high/low), what a bubble means
(order-book absorption vs candle-colour volume at a line touch), and the confirmation logic.

---

## 9. Screen checks done (built-in browser, 1080p frames)

| Live / time | What's on screen |
|---|---|
| 23 Oct 24:05 | EURUSD 5m (FXCM). FRVP with red VAH, black POC, green VAL; circled sweep above the red line; red candle forming. No Eyes FootPrint. |
| 23 Oct 14:08 | BTC/USD 5m. "50% zone" = hand-drawn blue box + lines. |
| 23 Oct 19:46 | Gold 5m (TVC). Red/black/green FRVP lines, hand-drawn "FVG" box, "Minor BuySide Liquidity" label, projected path arrows. |
| 23 Oct 1:08:15–1:08:23 | FRVP settings dialog (Inputs + Style), table in §2.1. |
| 23 Oct 1:10:08 | Fib Retracement settings ("Malaysian fib"), levels in §2.3. |
| 23 Oct 1:30:52 | Gold 5m. Short position tool after a wick above the minor BSL; red candle; target below (worked example). |
| 23 Oct 1:03:00 | Silver 5m (OANDA). Plain chart while he talks about "the indicator" being footprint-based. Nothing shown. |
| 21 Oct 14:27 | Gold **1m** (TVC). FRVP red/black/green, FVG box, circled high sweep. |
| 21 Oct 1:48:43 | EURUSD 5m (FXCM). "50% zone" = hand-drawn green boxes. |
| 20 Oct 59:32–59:40 | BTC/USD 1m. Short position drawn, "Minor BuySide Liquidity" / SSL labels. No footprint overlay yet. |
| 22 Oct 1:57:06 | Gold 1m. Legend **"Eyes Smart Structure Engine 4 20 1.5"** (paid indicator): ribbon, coloured candles, zones. |
| 24 Oct 1:43:31 | BTC 5m, TradingView **paper trading**. FRVP on the left; fib box with 0 / 0.5 / 1. |

---

## 10. Worked examples (from the lives)

1. **Gold short from the red zone, 21 Oct.**
   - Plan at 4:36 and 16:07–17:46: sell the FVG after a rejection above the red zone; SL ≈ $4; TP 1:3.
   - Entry at 19:55, ≈1:1 by 21:09.
   - At 23:20 he explains booking 50%; by 34:56 he books a second chunk.
   - https://www.youtube.com/watch?v=b0NAPRNyoxA&t=976s
2. **Gold red-candle short, 23 Oct 1:30:14–1:31:10.**
   - Liquidity grab, then a red candle closes on 1m at the zone. Enter; TP at POC ≈ 1:2.6. Screen at 1:30:52.
   - https://www.youtube.com/watch?v=A3-hEpzHkmk&t=5414s
3. **EURUSD FRVP sweep, 23 Oct 22:21–24:17.**
   - How to draw FRVP; sweep above the red line; red candle; entry at its low; TP1 POC, TP2 VAL.
   - https://www.youtube.com/watch?v=A3-hEpzHkmk&t=1341s
4. **Gold long with partial booking, 20 Oct 19:27–24:28.**
   - Counter-bias pullback buy (his own; he tells followers not to). Books 50% at ≈1:1.5, holds for 1:6–1:10.
   - https://www.youtube.com/watch?v=6VTHI15UG4w&t=1167s
5. **BTC red-zone retest short, paper, 24 Oct 1:22:59–1:29:14.**
   - Close below the red zone, retest, sell; SL above. This trade later went to ≈1:1.2 and was stopped (2:29:45–2:31:20)
     because no one booked.
   - https://www.youtube.com/watch?v=mfVj251fsQc&t=4979s
6. **BTC "no FVG, no trade", 20 Oct 52:41–53:54.**
   - Red zone, liquidity and close below were all there, but no FVG formed, so he skips it.
   - https://www.youtube.com/watch?v=6VTHI15UG4w&t=3161s

---

## 11. Unclear / contradictions (flagged, not filled in)

- **Re-entry after SL:** recommended on 21 Oct (29:29), discouraged on 22 Oct (7:03).
- **"Fractal only" vs taking counter-trend trades:** he trades against bias himself and says "take the trade the market shows"
  (22 Oct 1:28:11), but tells followers "sell only".
- **"Malaysian fib":** which level is the entry and why those numbers.
- **Line "timing" / his "own maths":** 24 Oct 2:18:39–2:20:50.
- **Hedging / recycle-rebalance:** not explained.
- **Session times and news rules:** none given.
- **What Eyes FootPrint is for:** never discussed in these five lives. Might be covered in his regular videos or the paid
  group's lectures, which weren't part of this study.
