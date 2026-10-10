Enter file contents here# Hours to liq if mark is flat

Jupiter Perps returns borrowFeesUsd and createdTime. It does not return hours-to-liq. Estimate for a long:

hours = (mark - liq) / ((borrowFeesUsd / hoursOpen / sizeUsd) * entry)

Units: borrowFeesUsd is micro-USD (/1e6). createdTime is unix seconds.

Worked example from live keeper wallet GoGMQHHrxgRBRqFSLaKRCffrjLfsaDcFz3HAC73CG4zm, 2026-10-10 ~09:10 UTC, 9.80h open:

- borrow paid $0.366 -> $0.037/h
- size $2370.82, entry $109.192, mark $110.02, liq $107.317
- liq walks ~$0.0017/h toward mark
- ~65 days to liq if mark is flat (SL still sits at $107.55)

See also NOTES.md.
