# Stock pairs

A "stock pair" is an asset a token rewards its holders with. Every launch includes **$STONKS**; creators can add up to 9 more. Rewards are split equally across the selected assets.

## Available assets (BNB Chain mainnet)

| Symbol | Underlying | Issuer | Price source |
|---|---|---|---|
| STONKS | StonksPad platform token | — | PancakeSwap TWAP (required in every launch) |
| AAPLB | Apple | bStocks | Chainlink |
| GOOGLB | Alphabet | bStocks | Chainlink |
| MSFTB | Microsoft | bStocks | Chainlink |
| NVDAB | Nvidia | bStocks | Chainlink |
| TSLAB | Tesla | bStocks | Chainlink |
| GMEB | GameStop | bStocks | Chainlink |
| QQQB | Nasdaq-100 ETF | bStocks | Chainlink |
| SPYB | S&P 500 ETF | bStocks | Chainlink |
| SPCXB | SpaceX | bStocks | PancakeSwap V3 TWAP |
| SKHYB | SK Hynix | bStocks | PancakeSwap V3 TWAP |
| BABAB | Alibaba | bStocks | PancakeSwap V3 TWAP |
| MSTRB | Strategy (MicroStrategy) | bStocks | PancakeSwap V3 TWAP |

The list grows over time. Contract addresses are on the [Contracts](contracts.md) page.

## How an asset gets listed

An asset must meet two requirements before StonksPad adds it:

1. **Liquidity** — a PancakeSwap pool deep enough (roughly $200k+) that vault purchases do not move the price.
2. **A reference price** — a Chainlink feed for the underlying, or a PancakeSwap pool whose time-weighted average price (TWAP) can be read on-chain.

The reference price is a safety check, not the purchase price: the vault buys on PancakeSwap but refuses any purchase that is more than a few percent worse than the reference. That is what makes it impossible to sandwich the vault.

## Corporate actions

bStocks tokens carry an on-chain "UI multiplier" for stock splits. StonksPad accounts for it, so a split changes neither what the vault buys nor what holders can claim.
