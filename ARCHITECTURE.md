# Architecture: Maa Mann

A single-page, serverless, offline web app. No backend, no database, no network calls.

```
 ASHA / ANM worker (phone browser)
            |
            v
   index.html  (HTML + CSS + JavaScript)
   +--------------------------------------------+
   | Language selector -> UI text + questions   |
   | EPDS form (10 items, radio buttons)        |
   | scoreEPDS(): total, risk level, item-10    |
   |   urgent flag                              |
   | Result view: risk level + referral advice  |
   |   + Tele-MANAS 14416 / 112 if urgent       |
   +--------------------------------------------+
            |
            v
   Nothing stored or transmitted (memory only; cleared on reset/reload)
```

## Components
| Component | Role |
|---|---|
| `QUESTIONS` | The 10 EPDS items with option scores (reverse-scored items already mapped). |
| `LANGS` | UI text per language. Add a validated translation under `LANGS.<code>.questions`. |
| `scoreEPDS()` | Pure function: sums scores, applies cut-offs (0-8 low, 9-12 possible, 13+ high), flags item 10 > 0 as urgent. |
| `render()` / `showResult()` | Builds the form and the result card using `textContent` (no HTML injection). |

## Design decisions
- Offline and static so it works in low-connectivity villages and can be hosted free (GitHub Pages) or opened from a file.
- No personal data collected: removes privacy and consent risk for the prototype.
- Self-harm item overrides the total score and always shows the urgent pathway.

## Roadmap
1. Validated Tamil and other state-language EPDS versions.
2. Optional anonymous aggregate reporting for PHC dashboards.
3. Follow-up reminders and referral completion tracking.
4. PHQ-9 and other tools; integration with state maternal health programmes.
