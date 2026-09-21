# $STONKS

`$STONKS` is the StonksPad platform token on BNB Chain.

Contract: `0xc9d825E83AadA475bD4d38C8ca984eD746277777`

## Role in the platform

- **In every launch.** Every StonksPad token rewards its holders with $STONKS alongside the stocks the creator picks. It cannot be removed from a launch.
- **Constant buy pressure.** The vault of every token buys $STONKS on PancakeSwap with the holders' reward share.
- **Constant burn.** 80% of the platform's own fee share is used to buy $STONKS and send it to the burn address `0x…dEaD`, permanently reducing supply.

Both flows are executed by the keeper and verifiable on-chain: look for `buyStocks` calls on any vault and `buyAndBurn` calls on the Treasury.

## Trading

$STONKS trades on PancakeSwap (V2, paired with QQQB) and on flap.sh.
