# Test cases

Answers are the score (0-3) of each of the 10 EPDS items, already adjusted for reverse-scored items.
Run `runTests()` in the browser console, or enter the matching answers by hand.

| # | Scenario | Item scores | Expected total | Expected level | Urgent alert |
|---|---|---|---|---|---|
| 1 | No symptoms | 0,0,0,0,0,0,0,0,0,0 | 0 | Low | No |
| 2 | Borderline | 1,1,1,1,1,1,1,1,1,0 | 9 | Possible depression | No |
| 3 | High risk | 2,2,2,2,2,2,2,0,0,0 | 14 | High | No |
| 4 | Self-harm item positive, low total | 0,0,0,0,0,0,0,0,0,1 | 1 | Low | **Yes** |
| 5 | Maximum | 3 x 10 | 30 | High | **Yes** |
| 6 | Unanswered question | any 9 answered | - | Error "Please answer all 10 questions" | No |

Machine-readable versions: `sample_data/sample_responses.json`.
