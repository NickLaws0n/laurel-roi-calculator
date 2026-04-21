# Laurel ROI Calculator

A one-page calculator that turns a firm's timekeeper count into an annual billable-revenue recovery figure, using Laurel AI's published utilization-lift math.

**Live:** https://nicklaws0n.github.io/laurel-roi-calculator/

Built so any CSM, AE, or SE can plug in a firm's numbers in ~15 seconds and walk into a call with a defensible uplift figure — without re-deriving the math every time.

## Who this is for

Anyone on the Laurel team (CSMs, AEs, SEs) who wants to talk about dollar impact with a firm and would rather pull up a link than rebuild a spreadsheet. Fork it, tweak the defaults, make it yours.

## How to use

1. Open the link.
2. Enter the firm's **timekeeper count** and **average hourly rate**.
3. Adjust **hours recovered per day**, **working days**, or **adoption %** if you want to model a specific scenario.
4. Read the number. The scale table below shows sensitivity at 25 / 50 / 75 / 100% adoption.

Nothing is stored. No tracking. Works offline after first load.

## The formula

```
Daily recovery per user   = hours_recovered_per_day × avg_hourly_rate
Active users              = total_timekeepers × adoption_%
Annual recovery (firm)    = daily_recovery_per_user × active_users × working_days
```

Example: 1,500 TK × 0.4 hrs × $350/hr × 250 days × 100% = **$52.5M annual uplift**.

## Default assumptions

| Variable | Default | Where it comes from |
|---|---|---|
| Hours recovered / day | 0.4 | Laurel enterprise-customer average |
| Avg hourly rate | $350 | Mid-market Am Law blended placeholder — override with the firm's real rate |
| Working days / year | 250 | Standard billing calendar (52w × 5d minus holidays) |
| Adoption % | 100 | Full adoption. Model a ramp (25 → 50 → 75 → 100%) for rollout pitches. |

All defaults are visible and editable in the UI. The in-page "Assumptions" section explains the reasoning for each — and flags what *isn't* modeled (realization-rate haircut, narrative-quality write-down reduction, OCG compliance cost avoidance).

## What's not modeled

- **Realization rate.** Firms collect 85–92% of billed hours. If you want a conservative number, multiply the output by the firm's realization rate.
- **Write-down reduction from better narratives.** Laurel's AI-generated narratives tend to reduce client write-downs; that upside sits on top of the hours figure.
- **OCG / compliance cost avoidance.** Violations are expensive; Laurel's OCG-rules engine reduces them. Not counted here.

The calculator is intentionally conservative. The real number for most firms is higher than what it shows.

## Running locally

It's one HTML file. Clone and open:

```bash
git clone https://github.com/NickLaws0n/laurel-roi-calculator.git
cd laurel-roi-calculator
open index.html
```

No build step, no dependencies beyond Google Fonts (loaded from CDN).

## License

MIT. Fork, modify, rebrand, embed — whatever's useful.

## About

Built by [Nick Lawson](https://github.com/NickLaws0n) while interviewing for a CSM role at Laurel AI, April 2026. Shared with the team in case it's useful. Not affiliated with Laurel.

If you're on the Laurel team and want a tweak (different defaults, additional inputs, embedded in another page), open an issue or message me.
