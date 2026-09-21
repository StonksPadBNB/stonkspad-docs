# Stock pairs

A "stock pair" is an asset a token rewards its holders with. Every launch includes **$STONKS**; creators can add up to 9 more. Rewards are split equally across the selected assets.

## Available assets (BNB Chain mainnet)

33 assets are registered today: 21 on the **RWA** tab (tokenized stocks, ETFs and gold) and 12 on the **Crypto** tab. The tables below mirror the on-chain registry of the StonksPad Vault Factory (last updated 2026-09-21).

### RWA tab

| Symbol | Underlying | Issuer / type | Price source | Tab |
|---|---|---|---|---|
| AAPLB | Apple | bStocks | Chainlink | RWA |
| GMEB | GameStop | bStocks | Chainlink | RWA |
| GOOGLB | Alphabet | bStocks | Chainlink | RWA |
| METAB | Meta Platforms | bStocks | Chainlink | RWA |
| MSFTB | Microsoft | bStocks | Chainlink | RWA |
| NVDAB | Nvidia | bStocks | Chainlink | RWA |
| QQQB | Nasdaq-100 ETF (QQQ) | bStocks | Chainlink | RWA |
| SPYB | S&P 500 ETF (SPY) | bStocks | Chainlink | RWA |
| TSLAB | Tesla | bStocks | Chainlink | RWA |
| XAUT | Gold (1 troy ounce) | Tether Gold | Chainlink | RWA |
| BABAB | Alibaba | bStocks | PancakeSwap V3 TWAP | RWA |
| BNCB | CEA Industries | bStocks | PancakeSwap V3 TWAP | RWA |
| CRCLB | Circle | bStocks | PancakeSwap V3 TWAP | RWA |
| FXIon | China Large-Cap ETF (FXI) | Ondo | PancakeSwap V3 TWAP | RWA |
| HOODB | Robinhood | bStocks | PancakeSwap V3 TWAP | RWA |
| INTCB | Intel | bStocks | PancakeSwap V3 TWAP | RWA |
| MSTRB | Strategy (MicroStrategy) | bStocks | PancakeSwap V3 TWAP | RWA |
| SKHYB | SK Hynix | bStocks | PancakeSwap V3 TWAP | RWA |
| SNDKB | Sandisk | bStocks | PancakeSwap V3 TWAP | RWA |
| SOXLB | Semiconductor Bull 3x ETF (SOXL) | bStocks | PancakeSwap V3 TWAP | RWA |
| SPCXB | SpaceX | bStocks | PancakeSwap V3 TWAP | RWA |

### Crypto tab

| Symbol | Underlying | Issuer / type | Price source | Tab |
|---|---|---|---|---|
| STONKS | StonksPad platform token | — | PancakeSwap V2 TWAP (required in every launch) | CRYPTO |
| ASTER | Aster | Native BEP-20 | Chainlink | CRYPTO |
| BTCB | Bitcoin | Binance-Peg token | Chainlink | CRYPTO |
| DOGE | Dogecoin | Binance-Peg token | Chainlink | CRYPTO |
| ETH | Ethereum | Binance-Peg token | Chainlink | CRYPTO |
| SOL | Solana | Binance-Peg token | Chainlink | CRYPTO |
| U | US dollar | Stablecoin | Chainlink | CRYPTO |
| USD1 | US dollar | Stablecoin | Chainlink | CRYPTO |
| USDC | US dollar | Stablecoin | Chainlink | CRYPTO |
| USDT | US dollar | Stablecoin | Chainlink | CRYPTO |
| CMC20 | CoinMarketCap 20 index | Index token | PancakeSwap V3 TWAP | CRYPTO |
| UUSD | US dollar | Stablecoin | PancakeSwap V3 TWAP | CRYPTO |

**The list grows over time.** New assets are added as soon as they meet the listing requirements below; the create page always shows the live registry. Contract addresses are on the [Contracts](contracts.md) page.

## How an asset gets listed

An asset must meet two requirements before StonksPad adds it:

1. **Liquidity** — a PancakeSwap pool deep enough (roughly $200k+) that vault purchases do not move the price.
2. **A reference price** — a Chainlink feed for the underlying, or a PancakeSwap pool whose time-weighted average price (TWAP) can be read on-chain.

The reference price is a safety check, not the purchase price: the vault buys on PancakeSwap but refuses any purchase that is more than a few percent worse than the reference. That is what makes it impossible to sandwich the vault.

## Corporate actions

Tokenized stocks such as bStocks carry an on-chain "UI multiplier" for stock splits. StonksPad accounts for it, so a split changes neither what the vault buys nor what holders can claim.
