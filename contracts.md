# Contracts

All contracts are on **BNB Smart Chain (chain id 56)** and verified on BscScan.

## StonksPad (current generation)

| Contract | Address |
|---|---|
| Vault Factory | `0x53Cc07A3Dd2015Cb84eFfcD0663B5Bd805a6bab4` |
| Treasury | `0x994EF72de824e4B116158a11b8250D4f11377CD3` |
| Vault Beacon | `0xFb634ef0808cc418A76a16B32a3C93049C69d0c0` |
| Vault Implementation | `0xf89953bfe1ECec08b147006C511E3c7E19B5bb6E` |
| $STONKS | `0xc9d825E83AadA475bD4d38C8ca984eD746277777` |

Each launched token has its own vault (a proxy of the implementation above). The vault address is shown on the token page and on flap.sh.

## Flap (infrastructure)

| Contract | Address |
|---|---|
| VaultPortal | `0x90497450f2a706f1951b5bdda52B4E5d16f34C06` |
| Guardian (beacon owner) | `0x9e27098dcD8844bcc6287a557E0b4D09C86B8a4b` |

## Identifying a StonksPad token on-chain

A token was launched by StonksPad if its creation transaction emitted `FlapTaxVaultTokenCreated(token, vault, vaultFactory)` on the Flap VaultPortal with `vaultFactory` equal to the Vault Factory above (or the legacy factory `0x14B8425dd0F3fDd539Fd72e33c08D22a35013A11`).

## Stock tokens

| Symbol | Address |
|---|---|
| AAPLB | `0x431a3bee82e2ca41e49895cbece5bb0f76a89b7a` |
| GOOGLB | `0x3f53de71c126bdabae20f9cd64848d317f6c3238` |
| MSFTB | `0x80106cb3ead06659a5ad19df39d9b4733863b9b0` |
| NVDAB | `0x02fca66c1d1afb4e2a7884261eb00f63598a7436` |
| TSLAB | `0x5b1910eaad6450e50f816082aa078c41f10c292f` |
| GMEB | `0x46ceefda28dd7207059ed19b0acdc026955bb15c` |
| QQQB | `0x205812cdbed920aff76c6580abd681a46d11efc7` |
| SPYB | `0x7138b48df7d98d7e3cc221bfe7192d0a178182d8` |
| SPCXB | `0xbe9d156892e55e7154bcd3cb0fea677f9d3103e1` |
| SKHYB | `0xca750ef65f295bbecd685abf54e82caf297bdb61` |
| BABAB | `0x4ef9d3062c7f6eba4aae4990c5036598c6eff4ec` |
| MSTRB | `0xe87afb3076aeb0f9b14e368de8145ae6a2826a14` |
