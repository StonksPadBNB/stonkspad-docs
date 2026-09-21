# Fees

StonksPad is designed so that everyone's incentives point the same way: more trading means more stocks for holders, more fees for creators and more $STONKS burned.

## Trading tax

Set by the creator at launch: **0–10% on buys and 0–10% on sells**. This is the only fee traders pay beyond the normal network fee.

## Where the tax goes

For every 100 BNB of tax collected:

| Recipient | Share | Notes |
|---|---|---|
| Flap protocol | 10 | Flap's fee for the launch infrastructure, taken before anything reaches the vault. |
| StonksPad platform | 10 | Taken by the vault (11.1% of what it receives, which equals 10% of gross). |
| Creator + holders | 80 | Split between creator fees and holder rewards according to the creator's settings. |

So a creator who chooses "Creator 20% / Holder rewards 80%" effectively earns 16% of gross tax, and holders receive 64% of gross tax as stocks.

## The platform's share

StonksPad's 10% does not go to a company wallet. It goes to the **Treasury** contract, which splits it:

| Share | Use |
|---|---|
| **80%** | Buys $STONKS on PancakeSwap and burns it permanently. |
| **10%** | Stonks Broker Reserve |
| **10%** | Platform operations. |

The split is hard-coded in the Treasury contract and can be verified on-chain.

## Operations reserve

Buying stocks and publishing distributions costs gas. Rather than the platform paying it, each vault reimburses the keeper from its own stock pool, **capped** per call, per day and by gas price (hard maximum 0.01 BNB per call and 0.1 BNB per vault per day; live caps are far lower, around 0.0002 / 0.005 BNB). Reimbursement never touches creator fees or the platform share, and is limited to 5% of the pool per call so small vaults are protected.

## No other fees

- No launch fee.
- No claim fee (network gas only; X-login users get a gas top-up).
- No fee on tokens sent to X handles.
