# Signal Garden

![Signal Garden gameplay](https://raw.githubusercontent.com/raindogkitetu/friendsdk/main/games/signal-garden/media/signal-garden-960.png)

**Project name**

Signal Garden

**Builder / contact**

raindog_kitetu · X [@raindog_kitetu](https://x.com/raindog_kitetu) · GitHub [@raindogkitetu](https://github.com/raindogkitetu)

**Category**

Economy Potential (also relevant: Token Activity and Character Spotlight)

**What did you build?**

A personalized signal garden that grows around the player's verified Rare Friend.
Buy a simulated 1 RF Signal Seed, choose one of twelve plots, reveal a bloom, then
keep it for harmony or harvest its fixed RF value. The Friend's real on-chain family
and art seed determine its bloom affinity and three signal plots, so each owned
Generations NFT produces a distinct garden and strategy without changing RF odds.

**How does it use Rare Friends?**

The selected Generations NFT is the center of the game. FriendSDK verifies fresh
ownership before play, and Signal Garden reads the Friend's canonical animation,
family and art seed through public SDK APIs. Its official sprite lives at the center
of the garden; family sets one of four bloom affinities; seed marks three glowing
plots. Those traits affect non-financial harmony only and never alter the published
reward table.

Every planting is modeled as RF activity. The exact preview has an 85% expected
harvest. A reviewed production economy would route the remaining 15% transparently:
10% burned and 5% sent to a fully specified seasonal community vault. That split is
clearly labeled as a future model; this submission does not claim a live burn.

An in-game Token activity receipt makes the loop measurable: acquired seeds,
signals planted, cumulative simulated RF spent, proposed burn and proposed vault
allocation all update from the verified SDK ledger. **Cumulative simulated RF spend
also stays visible in the main HUD, including the 360 px layout, so Token Activity
is visible before opening any menu.** Harvesting reopens a scarce plot while the
gross-spend total remains, making repeat RF activity visible rather than reducing
the loop to a net-balance snapshot.

For every 10 simulated Signal Seeds, the model exposes **10 RF gross activity,
8.5 RF expected harvest liability, 1 RF proposed burn and 0.5 RF proposed seasonal
vault**. These are model values, not live transfers.

**Source code**

[https://github.com/raindogkitetu/friendsdk](https://github.com/raindogkitetu/friendsdk) · FriendSDK v0.1.2 · game path: `games/signal-garden`

**Playable demo / how to run**

[https://raindogkitetu.github.io/friendsdk/](https://raindogkitetu.github.io/friendsdk/)

The hosted preview requires a browser wallet on Robinhood mainnet (chain 4663)
holding a hardwired Generations NFT, generation 1 or higher. The SDK freshly verifies
ownership before mounting the game. Preview balances and results are simulated; no
RF funding, private key or transaction signature is required.

To run locally with Node.js 22+ on Linux or Ubuntu/WSL2:

```sh
git clone https://github.com/raindogkitetu/friendsdk.git
cd friendsdk
npm ci
npm run build
npm run dev:game -- games/signal-garden
```

**How do you play?**

1. Connect a wallet and choose an eligible Friend.
2. Choose **Buy a seed · 1 RF** and confirm the simulated action.
3. Choose an empty plot. Planting consumes one seed and reveals one bloom.
4. Keep it for harmony or harvest its fixed simulated RF value.
5. Fill twelve plots, or harvest blooms to reopen space and continue.
6. Open **Simulated activity** (or **Guide → View activity receipt** on a narrow
   screen) to inspect cumulative RF activity and the proposed production split.

Mouse, touch and keyboard navigation work. The game is silent by design and includes
a reduced-motion setting. Interrupted settlement is recoverable through **Resume
signal** without purchasing or consuming a second seed.

**Costs and rewards**

Everything is simulated and labeled.

| Result | Chance | Fixed harvest | Base harmony |
| --- | ---: | ---: | ---: |
| Dewbud | 50% / 5,000 bps | 0.4 RF | 1 |
| Sunpetal | 30% / 3,000 bps | 1 RF | 2 |
| Prismvine | 15% / 1,500 bps | 1.5 RF | 4 |
| Starbloom | 5% / 500 bps | 2.5 RF | 8 |

- Seed price: 1 RF.
- Expected harvest: exactly 0.85 RF / 85%.
- Maximum harvest and reserve per seed: 2.5 RF.
- One seed produces exactly one bloom.
- Kept blooms retain their fixed simulated liability with no expiry during the
  runtime session.
- Harmony has no RF value. Family-affinity and signal-plot bonuses do not alter odds.

**Production-economy potential**

The proposed live split per 1 RF planting is 0.85 RF expected harvest liability,
0.10 RF burned and 0.05 RF sent to a seasonal vault. The burn is proportional and
predictable rather than dependent on a player's loss. Kept blooms make the Friend
visibly personal; harvesting returns the disclosed value and reopens scarce garden
space. Community seasons can later fund fully covered garden goals and opt-in
exhibitions.

The receipt tracks gross seed purchases, not net wallet movement. That makes the
intended repeat-spend loop auditable at a glance: each new seed adds exactly 1 RF of
simulated activity, 0.10 RF to the proposed burn counter and 0.05 RF to the proposed
season-vault counter, even when an earlier bloom has been harvested.

FriendSDK v0.1.2 does not expose burn, season-vault, persistence or additional-item
actions. A real version therefore requires a reviewed contract, funded reserves,
explicit wallet confirmations and published season rules. This entry contains no
live contract or transaction flow.

**What have you tested?**

Run on 2026-09-20 with FriendSDK v0.1.2 and Node.js 24:

- SDK build: pass.
- `friendsdk check`: pass; weights 10,000 bps, expected reward 0.85 RF, maximum
  reward 2.5 RF.
- Deterministic economy assertions: pass.
- Focused browser flow at 960 px and 360 px: pass.
- The browser flow covers verified runtime startup, canonical artwork, buy,
  confirmation, interrupted-settlement recovery, reveal, keep, inspect, harvest,
  cumulative token-activity accounting, reduced motion and viewport bounds.
- Browser console, sandbox and unexpected-signing checks: pass.

The automated browser fixture is read-only and exists only in tests. Public builds
retain the real wallet and ownership gate.

**Known limitations and wallet/fund risks**

- All RF activity and the proposed 10% burn / 5% vault split are simulated.
- Garden placement is session-local because the SDK has no persistence API. A child
  frame reload rebuilds visible blooms from host inventory but not their old plots;
  a full runtime reload resets the preview.
- Trading, swaps, creator fees, wearables, additional currencies and live upgrades
  are not implemented.
- Connecting reads wallet identity and owned Friends. The game has no signer,
  arbitrary calldata, private-key access, deployment or bankroll withdrawal power.
- Official Rare Friends production publication requires separate review.

**Credits**

Built with FriendSDK v0.1.2 (Apache-2.0 source license and repository artwork
notice): runtime, wallet/Friend verification, canonical Generations art reader,
sandbox bridge and simulated ledger. Signal Garden's UI, bloom vectors, rules,
scoring and economy model are original. No third-party assets are used.
