# How it works

Every StonksPad token is a **Flap tax token**: a small tax is charged on each buy and sell. Instead of sending that tax to a single creator wallet, StonksPad routes it into a dedicated **vault** that belongs to the token. The vault is where the magic happens.

```
   trade on the bonding curve / PancakeSwap
                    │
                    ▼  buy/sell tax
             Flap TaxProcessor
                    │  (Flap keeps its protocol fee)
                    ▼
        ┌──────────────────────┐
        │   StonksPad Vault    │  one vault per token
        └──────────────────────┘
          │               │            │
   platform fee      creator fees   stock pool
          │               │            │
     Treasury         claimable    buys the chosen
   80% burn STONKS     by wallet   stock tokens on
   10% Broker Reserve  or X handle PancakeSwap
   10% platform                        │
                                       ▼
                             holder distributions
                             (claim on the site)
```

## Step by step

1. **Launch.** The creator fills in the token details, picks up to 10 stock pairs (STONKS is always included), sets the buy/sell tax and decides how the tax is split between creator fees and holder rewards. The token is created on Flap with the StonksPad vault as its tax recipient.

2. **Trade.** People buy and sell on the site (or anywhere else the token trades). On the bonding curve, trades go through Flap; after graduation, through PancakeSwap. Each trade pays the tax.

3. **Collect.** Flap's tax processor forwards the token's tax revenue to its vault. The vault immediately sets aside the platform fee and splits the rest: creator routes get their percentage as claimable BNB, the stock pool gets the holders' percentage.

4. **Buy stocks.** A keeper service regularly converts the stock pool into the chosen stock tokens on PancakeSwap, protected by price oracles (Chainlink or on-chain TWAP) so nobody can front-run the vault at a bad price.

5. **Distribute.** Every hour the keeper checks each vault. When at least $20 of undistributed stocks has accumulated, it snapshots the token's holders, computes each holder's share and publishes the distribution on-chain, with the full holder list stored on IPFS.

6. **Verify.** An independent verifier, running on a separate server with its own key, recomputes the snapshot from chain data. If it matches, claims open 30 minutes later. If the verifier does not confirm, claims open after 24 hours instead, giving time to cancel a bad distribution.

7. **Claim.** Holders claim their stocks from the site. Creators claim their BNB fees any time. Everything is pull-based: your rewards wait for you in the vault.

## What makes it different

- **Multiple stocks per token.** A launch can reward holders with up to 10 different assets at once, split equally.
- **Fee routing to X handles.** A creator can send fees to any X account, even one that has never used StonksPad. The recipient just logs in with X to find their earnings waiting.
- **Everything on-chain and open.** The vault code is public and verified on BscScan; the distribution lists are on IPFS; the vault is visible on flap.sh like any other Flap vault.
- **The platform shrinks its own token.** 80% of StonksPad's share of every token's fees is used to buy and burn $STONKS.
