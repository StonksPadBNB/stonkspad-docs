# For creators

## Launching a token

1. Go to **Create Token** on [stonkspad.sh](https://stonkspad.sh). Sign in with X (a custodial wallet is created for you) or connect your own wallet (MetaMask or any BNB Chain wallet).
2. **Token details**: name, ticker, image, description and optional links (website, X, Telegram, etc.). The image and description are stored on IPFS.
3. **Pairs**: choose the assets your holders will be rewarded with. `$STONKS` is always included; add up to 9 more from the RWA (tokenized stocks) and Crypto tabs. Rewards are split equally between the selected assets.
4. **Trading fees**: buy and sell tax (0–10% each). An optional **anti-farmer period** limits certain liquidity tricks in the first days.
5. **Fee distribution**: decide how the tax is split:
   - **Creator** — goes to your fee destinations as claimable BNB.
   - **Holder rewards** — goes into the stock pool (minimum 1%).
   - **Burn** — burns the token itself (handled natively by Flap).
   - **Liquidity** — adds liquidity (handled natively by Flap).
6. **Minimum holding for rewards** (optional): holders below this balance do not receive stock rewards. Useful to keep dust wallets out of distributions.
7. **Creator fee destination**: one or more rows, each a **wallet address** or an **X handle**, with a percentage. The X handle does not need to have used StonksPad before.
8. **Airdrop at launch** (optional): up to 20 X handles, each with a percentage of your initial buy. Tokens are sent right after the launch confirms.
9. **Initial buy** (optional): buy a portion of your own token in the same transaction as the launch.

Launch cost is the BNB network fee plus your initial buy. StonksPad does not charge a launch fee.

## After launch

- **My Tokens** shows every token you created, its market cap, volume, launch progress, reward assets and fee destinations.
- **Claim** shows your claimable creator fees (BNB). You can claim to your own wallet or to any address you choose.
- Your token appears on flap.sh as well, with its vault visible under Flap's vault section.

## Fee destinations explained

Fees are paid out to **wallets**. When you route fees to an X handle, StonksPad creates a wallet for that handle and credits the fees there. The owner of the X account unlocks it simply by signing in with X. If they already have a StonksPad account, the fees appear in it directly.

If an X account is renamed and someone else takes the old handle, hand-over of the wallet waits 24 hours and notifies the previous owner, so fees cannot be hijacked by a quick rename.

## Graduation

Tokens launch on the Flap bonding curve. When the curve fills, the token graduates to a PancakeSwap V2 pool with locked liquidity, exactly like every Flap token. Trading on StonksPad continues seamlessly; the tax and the vault keep working after graduation.
