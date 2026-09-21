# Security

StonksPad is built on the assumption that servers can be hacked. Funds and rewards are protected by contract rules, not by trust in the operator.

## Vault design

- **One vault per token.** Each vault only ever holds that token's revenue and stocks.
- **Pull-based.** Creator fees and holder rewards are claimed, never pushed. Nothing can be "sent to the wrong place" by the operator.
- **No emergency withdrawal.** There is no function that lets anyone drain a vault.
- **Receive is dumb.** When tax arrives, the vault only records it. All real work (buying stocks, distributing) happens in separate, rate-limited functions.

## Who can do what

| Role | Powers | Cannot |
|---|---|---|
| **Keeper** | Buy stocks, publish distributions, poke TWAP | Move funds, change the holder list after publishing, claim for anyone |
| **Verifier** (separate server, separate key) | Approve a distribution it has independently recomputed | Publish, cancel, move funds |
| **Platform admin** (hardware-style wallet, never on a server) | Register stocks, set caps, cancel a bad distribution, set keeper/verifier | Withdraw funds, alter balances |
| **Flap Guardian** | Upgrade the vault code, everything the admin can | Withdraw funds |

## Distribution safety

A distribution is a list computed off-chain; the chain cannot check it by itself. StonksPad adds two layers:

1. **Independent verification.** A second service, on its own server with its own key, recomputes the holder snapshot from raw chain data at the same block and approves the distribution only if the root matches byte-for-byte. Approval opens claims after 30 minutes.
2. **Time lock.** Without approval, claims stay closed for 24 hours, during which the admin (or Flap's Guardian) can cancel. A newly set verifier is inert for 24 hours, so a stolen admin key cannot install its own verifier and skip the lock.

The full holder list of every distribution is published on IPFS. Anyone can recompute it.

## Price safety

Vault purchases are checked against a reference price (Chainlink, or an on-chain TWAP over 30 minutes) with a deviation cap. Purchases are also capped per call and rate-limited. Front-running the vault into a bad price fails on-chain.

## Upgrades

Vaults are upgradeable beacon proxies. The only address that can upgrade them is **Flap's Guardian** — not StonksPad. Any upgrade goes through Flap's review.

## Custodial wallets

Users who sign in with X get a wallet whose key is managed by a separate signer service that is not reachable from the internet, with per-transaction and daily limits. Users can export their private key at any time.

## Audits

- Vault contracts pass Flap's vault specification checks (no failures).
- Independent review of the web application and signer (red-team), findings fixed.
- Flap partner audit: *pending / in progress* — this page will link the report when available.

Contract source is verified on BscScan for every deployed contract.
