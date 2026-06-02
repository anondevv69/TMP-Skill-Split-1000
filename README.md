# TMP-Skill-Split-1000

Bankr skill pack for **splitting / fractionalizing** fee rights into **1000 ERC-1155 units** on [Token Marketplace](https://www.tokenmarketplace.shop).

## Install

```text
install TMP split 1000 at https://github.com/anondevv69/TMP-Skill-Split-1000
```

## Covers

- `GET /api/mint/status` → mint until **`ready`**
- GroupBuyEscrowV6 **self-split** (same as site “Split into 1000 shares”)
- Custodial **approve** blocks → retries → EOA + site fallback
- Verify **`unitsHeld`** via hybrid-status

## Does not cover

- Selling 100% (`POST /api/list/dual`) → use [TMP-Skill-Listing](https://github.com/anondevv69/TMP-Skill-Listing)
- Buying shares / CTO contribute → use [bankr-tmp-skill](https://github.com/anondevv69/bankr-tmp-skill)

## Related

| Skill | Repo |
|-------|------|
| Full hub (buy, list, claim) | [bankr-tmp-skill](https://github.com/anondevv69/bankr-tmp-skill) |
| List units after split | [TMP-Skill-Listing](https://github.com/anondevv69/TMP-Skill-Listing) |

## Agent.md

https://www.tokenmarketplace.shop/agent.md
