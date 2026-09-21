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

## Reward assets (stock registry)

Every asset a launch can reward its holders with is registered in the Vault Factory. 32 assets are registered today ($STONKS, listed above, plus the 31 below). The list grows over time; the authoritative source is the factory itself: `getStockList()` and `getStock(address)`.

| Symbol | Tab | Address |
|---|---|---|
| AAPLB | RWA | `0x431a3BEE82E2ca41e49895CbECE5bB0F76A89b7A` |
| GMEB | RWA | `0x46cEeFDa28Dd7207059ed19B0acdc026955bb15C` |
| GOOGLB | RWA | `0x3F53De71c126BdaBAe20f9cD64848d317f6C3238` |
| METAB | RWA | `0x7425889FE94F9d693E8daefE88BCCed6AcFEf4c0` |
| MSFTB | RWA | `0x80106cb3EAD06659A5ad19DF39D9b4733863B9b0` |
| NVDAB | RWA | `0x02Fca66C1D1aFB4E2A7884261eB00F63598a7436` |
| QQQB | RWA | `0x205812CdBed920aFf76C6580abD681a46D11efc7` |
| SPYB | RWA | `0x7138b48df7D98D7e3cc221BfE7192D0a178182D8` |
| TSLAB | RWA | `0x5b1910eAaD6450E50f816082Aa078C41F10C292f` |
| XAUT | RWA | `0x21cAef8A43163Eea865baeE23b9C2E327696A3bf` |
| BABAB | RWA | `0x4eF9d3062c7F6ebA4AAE4990c5036598C6eff4ec` |
| CRCLB | RWA | `0x80f3D493EBCe97e343c53D29a137942416B4ffC0` |
| FXIon | RWA | `0x9b8E987e6fEc8Cf1380C4dcA7071e2C7853AEEA1` |
| HOODB | RWA | `0xA394dCEa3fd3847fD793afBFd163E2e3858B7c65` |
| INTCB | RWA | `0xe614E2fc6C787035FF51f452e8E826Bfd32D5283` |
| MSTRB | RWA | `0xE87afb3076AeB0f9B14E368DE8145ae6a2826A14` |
| SKHYB | RWA | `0xCA750eF65f295BBECd685Abf54e82CAf297BDB61` |
| SNDKB | RWA | `0x3eE4dF61bd4F867E349BEaE8bFE07bc31b4850fb` |
| SOXLB | RWA | `0xd97d097a89113fa59b76c572E5b2Eb647E8eefaf` |
| SPCXB | RWA | `0xbe9D156892E55e7154BcD3cB0FEA677F9D3103E1` |
| ASTER | CRYPTO | `0x000Ae314E2A2172a039B26378814C252734f556A` |
| BTCB | CRYPTO | `0x7130d2A12B9BCbFAe4f2634d864A1Ee1Ce3Ead9c` |
| DOGE | CRYPTO | `0xbA2aE424d960c26247Dd6c32edC70B295c744C43` |
| ETH | CRYPTO | `0x2170Ed0880ac9A755fd29B2688956BD959F933F8` |
| SOL | CRYPTO | `0x570A5D26f7765Ecb712C0924E4De545B89fD43dF` |
| U | CRYPTO | `0xcE24439F2D9C6a2289F741120FE202248B666666` |
| USD1 | CRYPTO | `0x8d0D000Ee44948FC98c9B98A4FA4921476f08B0d` |
| USDC | CRYPTO | `0x8AC76a51cc950d9822D68b83fE1Ad97B32Cd580d` |
| USDT | CRYPTO | `0x55d398326f99059fF775485246999027B3197955` |
| CMC20 | CRYPTO | `0x2f8A339B5889FfaC4c5A956787cdA593b3c36867` |
| UUSD | CRYPTO | `0x61a10E8556BEd032eA176330e7F17D6a12a10000` |
