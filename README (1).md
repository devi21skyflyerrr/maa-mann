# Maa Mann: Postpartum Depression Screening Aid for ASHA / ANM Workers

Team **White Coat** | Hack for Social Cause, VBYLD 2027 | Theme: Healthcare, Wellbeing & Service Delivery
SDGs: 3 (Good Health & Well-being), 5 (Gender Equality), 10 (Reduced Inequalities)

## Problem
Postpartum depression is common but often goes unnoticed in rural and underserved areas because of stigma, few trained mental health staff, and no simple screening tool for frontline workers.

## Solution
An offline, mobile-friendly web app. The ASHA/ANM worker asks the mother the 10 questions of the Edinburgh Postnatal Depression Scale (EPDS). The app instantly gives a score, a risk level and referral guidance. If question 10 (thoughts of self-harm) is positive, an urgent alert appears with Tele-MANAS 14416 and 112.

**This is a screening aid, not a diagnosis.**

## Features
- 10-item EPDS with automatic scoring (reverse-scored items handled)
- Risk levels: 0-8 low, 9-12 possible depression, 13+ high risk
- Urgent pathway whenever item 10 is above zero
- Language selector, ready for validated translations
- Works offline; no data stored or sent
- Large touch targets, keyboard focus, mobile layout

## Setup
No installation and no environment variables are needed.
1. Download or clone this repository.
2. Open `index.html` in any modern browser (works offline).
3. Optional hosting: enable GitHub Pages (Settings > Pages > deploy from `main` branch, root).

Environment variables: none. Dependencies: none.

## Testing
Open the browser console and run `runTests()`. Expected results are in `TEST_CASES.md` and `sample_data/sample_responses.json`.

## Adding a language
Add an entry to `LANGS` in `index.html` with the UI strings and a `questions` array in the same order and scoring as `QUESTIONS`. **Use only a validated EPDS translation.** Missing strings fall back to English.

## Documentation
- `ARCHITECTURE.md`: design and roadmap
- `TEST_CASES.md`: test scenarios
- `LICENSE`: MIT

## Clinical references
Cox JL, Holden JM, Sagovsky R (1987). Detection of postnatal depression: development of the 10-item Edinburgh Postnatal Depression Scale. *British Journal of Psychiatry*, 150, 782-786.

## AI usage disclosure
AI assistance (Claude, by Anthropic) was used to draft the application code, documentation and form text. Idea selection, clinical content review and final checks were done by the author. Estimated share of AI assistance in the final work: see the presentation (slides 6-7).

## Limitations
Prototype only. Not clinically validated as a deployed tool, not a diagnostic device, and not a substitute for professional assessment.
