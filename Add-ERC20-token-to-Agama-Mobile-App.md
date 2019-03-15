# Easy steps to add ERC20 token to Agama Mobile

The Agama mobile code comprises of two parts. Agama wallet library and MeteorJS app. This assetchain adding guide will cover both. All the files needs changing are linked. If you want to add Bitcoin compatible coins follow [this guide](https://github.com/KomodoPlatform/agama-mobile/wiki/Add-a-Bitcoin-Compatible-coin-to-Agama-Mobile).

### Agama wallet library
- Add a contract ID [`https://github.com/pbca26/agama-wallet-lib/blob/dev/src/eth-erc20-contract-id.js`](https://github.com/pbca26/agama-wallet-lib/blob/dev/src/eth-erc20-contract-id.js)
- Add token decimals (optional, only if it's different from default 18 value) [`https://github.com/pbca26/agama-wallet-lib/blob/dev/src/eth-erc20-decimals.js`](https://github.com/pbca26/agama-wallet-lib/blob/dev/src/eth-erc20-decimals.js)
- Submit a PR, use dev branch!

### MeteorJS app
- Drop a 60 x 60 px logo into [`https://github.com/KomodoPlatform/agama-mobile/tree/dev/public/images/cryptologo/eth`](https://github.com/KomodoPlatform/agama-mobile/tree/dev/public/images/cryptologo/eth)
- Add ERC20 ticker to coins file [`https://github.com/KomodoPlatform/agama-mobile/blob/dev/imports/ui/actions/coins.js#L80`](https://github.com/KomodoPlatform/agama-mobile/blob/dev/imports/ui/actions/coins.js#L80)
- Add asset chain name to translation file [`https://github.com/KomodoPlatform/agama-mobile/blob/dev/imports/ui/translate/en.js#L475`](https://github.com/KomodoPlatform/agama-mobile/blob/dev/imports/ui/translate/en.js#L475).
- Submit a PR, use dev branch!

Please make sure an ERC20 is working in Agama mobile before making a commit. Pull requests containing partial information or not working assets/servers will remain unmerged until all requirements are fulfilled.