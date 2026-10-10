# Jupiter Perps v2 notes from a live keeper

Public wallet: GoGMQHHrxgRBRqFSLaKRCffrjLfsaDcFz3HAC73CG4zm
Open tx: 5gFmPnYZUkLtstoYjzth2jkKJH791HYVDUj5PcwGpvkbWVvLv5qLLmqjfCRwe2N1nTB6dXqnpTbmgGpSraurDJsT
Position: 2rRnSu4hRp69JhxitxAEKVR5otsFxZ1B6LKpzgNJpo5d

Tried: live SOL-USD long on jup.ag Perps plus perps-api.jup.ag with header x-perps-api-version: v2.

## What the public docs still miss

1. v2 header is required. Without x-perps-api-version: v2, POST /positions/increase 404s. With it, the API returns a VersionedTransaction.

2. Rent reserve is not in the UI. Venue minimum is $10 collateral after fees. Keep about 0.014 SOL native for the position plus TP plus SL accounts.

3. TP/SL are separate accounts, not one bracket. I set TP $111.70 / SL $107.55 on a ~$109.19 entry, with SL 23 bps above computed liq (~$107.30).

4. No hours-to-liq-if-flat. A 50x long on ~0.45 SOL collateral is ~$2370 notional. Mark can sit inside a $0.20 band for hours while equity swings $5-8 because of borrow plus mark.

## Builder asks

- Document the v2 header on every /positions/* example.
- Print the rent reserve next to the collateral input.
- Expose borrow-to-liq-hours on the open position card.
