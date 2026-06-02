---
name: tmp-split-1000
description: "TMP split 1000 — fractionalize fee rights into 1000 ERC-1155 units via GroupBuyEscrowV6 self-split."
tags: [bankr, base, tmp, token-marketplace, split, fractionalize, 1000, erc-1155, group-buy, v6, custodial]
version: 1
tmp_skill_version: "1"
homepage: https://github.com/anondevv69/TMP-Skill-Split-1000
---

# TMP Split 1000 — fractionalize fee rights

**Install:**

```text
install TMP split 1000 at https://github.com/anondevv69/TMP-Skill-Split-1000
```

**Prerequisite:** hybrid TMPR mint **`phase: ready`** — run mint via main skill or **`fractionalize-autopilot.md`** first.

**Agent guide:** https://www.tokenmarketplace.shop/agent.md

---

## One-line intents (split only)

| User says | You do | File |
|-----------|--------|------|
| **Split into 1000** / **fractionalize** / **1000 nfts** | Mint if needed → V6 self-split | **`fractionalize-autopilot.md`** |
| **Keep all units** | Same — seller gets all 1000 | **`split-1000-autopilot.md`** |
| **Just deployed — split 1000** | Same thread: mint loop → split | **`fractionalize-autopilot.md`** |
| Custodial **approve blocked** | 3× retry → transfer TMPR to EOA → site wizard | **`split-custodial-approve-block.md`** |

**NOT this skill:** `POST /api/list/dual` (that's sell 100%) · Doppler dashboard · 1000 OpenSea listings.

---

## Mandatory APIs

```http
GET https://www.tokenmarketplace.shop/api/mint/status?tokens={launch0x}&wallet={linked}
```

After split:

```http
GET https://www.tokenmarketplace.shop/api/claim/hybrid-status?token={launch}&wallet={linked}
```

Expect **`unitsHeld`** = 1000 (or user’s expected balance).

---

## On-chain (V6 self-split)

| Step | Action |
|------|--------|
| 1 | `approve` TMPR → **GroupBuyEscrowV6** `0x56bd948671955D0Ed82a88f136779cB76f551e0C` |
| 2 | `createPartialSale` — designatedBuyer = seller, ~0.0001 ETH self-split |
| 3 | `contribute` full price |
| 4 | `finalize` → 1000 ERC-1155 units to seller |

Details: **`split-1000-autopilot.md`**

---

## After split

- **List units:** install [TMP-Skill-Listing](https://github.com/anondevv69/TMP-Skill-Listing) → `share-market-list-autopilot.md`
- **Buy / claim:** [bankr-tmp-skill](https://github.com/anondevv69/bankr-tmp-skill)

---

## File map

| File | Use |
|------|-----|
| **`fractionalize-autopilot.md`** | Full mint + split conversation |
| **`split-1000-autopilot.md`** | On-chain steps after mint ready |
| **`split-custodial-approve-block.md`** | Scanner / approve failures |
| **`references/hybrid-escrow-mint-blocker.md`** | Mint escrow blocked |
| **`references/custodial-approve-block-retry.md`** | Retry policy |
