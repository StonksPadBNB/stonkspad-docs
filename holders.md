# For holders

Holding a StonksPad token means earning a slice of real tokenized stocks, paid from the token's own trading taxes.

## How rewards accrue

- Every trade pays the token's tax. The holder-reward share of that tax lands in the token's vault as BNB.
- The keeper converts that BNB into the token's chosen stock tokens (for example NVDAB, SPCXB, STONKS) on PancakeSwap.
- When at least $20 worth of stocks has accumulated for a token, a **distribution epoch** is published: a snapshot of all holders at a specific block, and each holder's share, proportional to their balance.

Your share in an epoch is `your balance ÷ eligible supply`, applied to each stock separately. Eligible supply excludes the liquidity pool, the vault, the token contract, burn addresses and any wallet below the token's minimum holding.

## Claiming

1. Open **Claim** on [stonkspad.sh](https://stonkspad.sh) and sign in (X login or your own wallet).
2. Each epoch shows its status:
   - **Verified · claimable at …** — the independent verifier confirmed the distribution; claims open 30 minutes after verification.
   - **24h window** — not yet verified; claims open 24 hours after publication.
   - **Claimable** — press Claim. All stocks in that epoch are sent in a single transaction.
3. Claim to your own wallet, or enter any other address.

There is no deadline. Unclaimed epochs stay claimable.

If you signed in with X, StonksPad pays the network fee for your first claims from a small gas top-up, so an empty wallet is not a problem.

## Tokens sent to your X handle

Anyone can send StonksPad tokens to an X handle. If someone sends tokens to yours before you have ever used StonksPad, they wait in a wallet that only your X account can unlock. Sign in with X and you will find them, together with any stock rewards they earned in the meantime.

## What you get

Stock tokens on BNB Chain are ordinary BEP-20 tokens issued by regulated providers (for example Binance's bStocks). Once claimed they are in your wallet: hold them, trade them on PancakeSwap, or use them anywhere else on BNB Chain.
