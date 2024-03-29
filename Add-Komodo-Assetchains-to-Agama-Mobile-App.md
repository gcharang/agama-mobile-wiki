# Easy steps to add Komodo asset chain to Agama Mobile

The Agama mobile code comprises of two parts. Agama wallet library and MeteorJS app. This assetchain adding guide will cover both. All the files needs changing are linked. If you want to add Bitcoin compatible coins follow [this guide](https://github.com/KomodoPlatform/agama-mobile/wiki/Add-a-Bitcoin-Compatible-coin-to-Agama-Mobile).

### Agama wallet library
- Add an electrum server for your KMD asset chain [`https://github.com/pbca26/agama-wallet-lib/blob/dev/src/electrum-servers.js#L1`](https://github.com/pbca26/agama-wallet-lib/blob/dev/src/electrum-servers.js#L1)
- Add a fixed fee for your asset chain [`https://github.com/pbca26/agama-wallet-lib/blob/dev/src/fees.js#L1`](https://github.com/pbca26/agama-wallet-lib/blob/dev/src/fees.js#L1)
- Add an asset chain to the list of kmd assets [`https://github.com/pbca26/agama-wallet-lib/blob/dev/src/coin-helpers.js#L1`](https://github.com/pbca26/agama-wallet-lib/blob/dev/src/coin-helpers.js#L1)
- Add an asset chain explorer [`https://github.com/pbca26/agama-wallet-lib/blob/dev/src/coin-helpers.js#L51`](https://github.com/pbca26/agama-wallet-lib/blob/dev/src/coin-helpers.js#L51)
- Submit a PR, use dev branch!

### MeteorJS app
- Drop a 60 x 60 px logo into [`https://github.com/KomodoPlatform/agama-mobile/tree/dev/public/images/cryptologo/btc`](https://github.com/KomodoPlatform/agama-mobile/tree/dev/public/images/cryptologo/btc)
- Add explorer url to whitelist [`https://github.com/KomodoPlatform/agama-mobile/blob/dev/mobile-config.js#L118`](https://github.com/KomodoPlatform/agama-mobile/blob/dev/mobile-config.js#L118)
- Add asset chain ticker to coins file [`https://github.com/KomodoPlatform/agama-mobile/blob/dev/imports/ui/actions/coins.js#L39`](https://github.com/KomodoPlatform/agama-mobile/blob/dev/imports/ui/actions/coins.js#L39)
- Add asset chain name to translation file [`https://github.com/KomodoPlatform/agama-mobile/blob/dev/imports/ui/translate/en.js#L344`](https://github.com/KomodoPlatform/agama-mobile/blob/dev/imports/ui/translate/en.js#L344).
- Submit a PR, use dev branch!

Please make sure an asset chain is working in Agama mobile before making a PR. Pull requests containing partial information or not working assets/servers will remain unmerged until all requirements are fulfilled.