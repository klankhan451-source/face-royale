# Face Royale — Step 1 Design

**What it is:** An original top-down 2D arena battler (HTML5 Canvas + vanilla JS, one self-contained `index.html`). One player + 19 bot fighters drop into an arena, loot weapons, fight inside a shrinking zone — last one standing wins. General genre ideas only (shrinking zone, loot, last-one-standing); all names, art, and code are original. Source of scope: `~/workspace/game_research/analysis_2026-11-25.md` (Concept A MVP).

## Signature features
- **Photo face:** the player may upload a photo; it is center-cropped to a circle **on-device only** (canvas; never uploaded — stated in the UI) and becomes the character's head in the lobby, in-game, and on the results poster. 6 built-in cartoon faces for anyone who skips the photo. Character name entry.
- **Choose your city:** 6 arenas at launch — Dhaka, New York, London, Dubai, Paris, Tokyo. Each has its own ground palette, seeded building layout, and simple canvas-drawn landmark silhouettes/signage. Gameplay is identical; look and layout differ.

## Match design
- 20 fighters, ~4–7 minute matches. Kill feed, alive counter, zone timer, minimap.
- Zone shrinks in stages with escalating outside damage.
- Weapons (loot): Pistol, Shotgun, Rifle, Sniper — distinct damage / range / fire-rate / spread — plus Medkits. Everyone starts with a weak training pistol.
- Player ability: **Shield** (3 s of heavy damage reduction, 18 s cooldown).
- Bots: 3 personalities (Aggressive / Cautious / Looter). They loot, path to the zone, heal, and fight each other — the alive count falls without the player.
- Controls: touch — left virtual joystick, hold-to-fire button with auto-aim at nearest enemy in range; desktop WASD/arrows + mouse/Space.

## Progression (localStorage only — no server, no accounts)
- Coins per match (placement + kills), spent on 6 outfits (direct purchase, earned coins only — **no real-money purchases in Step 1**).
- Rank points → 5-tier ladder: Bronze → Silver → Gold → Platinum → Diamond.
- Daily reward (once per calendar day) + 3 daily missions (Win 1 match / 5 kills today / Play 3 matches).

## Screens
Home (face + name + city picker + shop + missions + PLAY) → Match (HUD) → Results (placement, coins, victory/defeat poster canvas with face + city + stats, downloadable as an image).

## Step 1 exclusions (deferred to Step 2+)
Real multiplayer, accounts, ads SDKs, real-money purchases, public photo sharing, extra modes. Photo processing is 100% on-device; target audience framing 13+; photo always optional.

## Tech / deploy
- Single `index.html`, DPR capped for low-end phones, bot AI ticked at low frequency, only visible entities drawn.
- Live at https://klankhan451-source.github.io/face-royale/ (repo `face-royale` on klankhan451-source).
- A `window.__FR` debug handle is exposed for automated play-testing.
