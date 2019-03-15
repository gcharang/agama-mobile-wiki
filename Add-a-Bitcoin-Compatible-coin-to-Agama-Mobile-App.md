# Easy steps to add a Bitcoin compatible coin to Agama Mobile

The Agama mobile code comprises of two parts. Agama wallet library and MeteorJS app. This Bitcoin compatible adding guide will cover both. All the files needs changing are linked. If you want to add a Komodo asset chain follow [this guide](https://github.com/KomodoPlatform/agama-mobile/wiki/Add-Komodo-Assetchains-to-Agama-Mobile-App).

### Agama wallet library
- Add network params [`https://github.com/pbca26/agama-wallet-lib/blob/dev/src/bitcoinjs-networks.js`](https://github.com/pbca26/agama-wallet-lib/blob/dev/src/bitcoinjs-networks.js). Make use of isPoS or isZcash flags if applicable in your case.
- Add an electrum server [`https://github.com/pbca26/agama-wallet-lib/blob/dev/src/electrum-servers.js#L1`](https://github.com/pbca26/agama-wallet-lib/blob/dev/src/electrum-servers.js#L1)
- Add a safe fixed fee (per transaction) [`https://github.com/pbca26/agama-wallet-lib/blob/dev/src/fees.js#L1`](https://github.com/pbca26/agama-wallet-lib/blob/dev/src/fees.js#L1).
- Add an explorer [`https://github.com/pbca26/agama-wallet-lib/blob/dev/src/coin-helpers.js#L62`](https://github.com/pbca26/agama-wallet-lib/blob/dev/src/coin-helpers.js#L62)
- Submit a PR, use dev branch!

### MeteorJS app
- Drop a 60 x 60 px logo into [`https://github.com/KomodoPlatform/agama-mobile/tree/dev/public/images/cryptologo/btc`](https://github.com/KomodoPlatform/agama-mobile/tree/dev/public/images/cryptologo/btc)
- Add explorer url to whitelist [`https://github.com/KomodoPlatform/agama-mobile/blob/dev/mobile-config.js#L118`](https://github.com/KomodoPlatform/agama-mobile/blob/dev/mobile-config.js#L118)
- Add coin ticker to coins file [`https://github.com/KomodoPlatform/agama-mobile/blob/dev/imports/ui/actions/coins.js#L39`](https://github.com/KomodoPlatform/agama-mobile/blob/dev/imports/ui/actions/coins.js#L39)
- Add coin name to translation file [`https://github.com/KomodoPlatform/agama-mobile/blob/dev/imports/ui/translate/en.js#L344`](https://github.com/KomodoPlatform/agama-mobile/blob/dev/imports/ui/translate/en.js#L344).
- Submit a PR, use dev branch!

### How to get network params
- pubKeyHash: https://github.com/KomodoPlatform/komodo/blob/fbb3b3e9a0c432173a8d733ebbcbd7b0324d58df/src/chainparams.cpp#L169
- scriptHash: https://github.com/KomodoPlatform/komodo/blob/fbb3b3e9a0c432173a8d733ebbcbd7b0324d58df/src/chainparams.cpp#L170
- wif: https://github.com/KomodoPlatform/komodo/blob/fbb3b3e9a0c432173a8d733ebbcbd7b0324d58df/src/chainparams.cpp#L171
- bip32 public: https://github.com/KomodoPlatform/komodo/blob/fbb3b3e9a0c432173a8d733ebbcbd7b0324d58df/src/chainparams.cpp#L172
- bip32 private: https://github.com/KomodoPlatform/komodo/blob/fbb3b3e9a0c432173a8d733ebbcbd7b0324d58df/src/chainparams.cpp#L173

#### Note: you need to convert pubKeyHash (PUBKEY_ADDRESS), scriptHash (SCRIPT_ADDRESS) and wif (SECRET_KEY) decimal values to hexadecimal representation. Use this website to do conversion https://www.binaryhexconverter.com/decimal-to-hex-converter.
`PUBKEY_ADDRESS conversion example (KMD): 60 dec -> 0x3c hex`

In case if SECRET_KEY consists of two decimal numbers (e.g. 63 + 128) sum them up and use the result (192) on the converter website listed above.

If you can't find chainparams.cpp in your code base try checking one of these files https://docs.komodoplatform.com/barterDEX/get-listed-barterDEX.html#search-for-the-information-on-github.

Please make sure a Bitcoin compatible coin is working in Agama mobile before making a PR. Pull requests containing partial information or not working assets/servers will remain unmerged until all requirements are fulfilled.