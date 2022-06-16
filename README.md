# cryptowallet-cli

> Crypto wallet generator CLI tool (currently works only on Mac and Linux, sorry Windows users)

![Screenshot](https://i.imgur.com/KBb7NqW.png)

---

## Install
```bash
# via Yarn
$ yarn global add @yerofey/cryptowallet-cli

# or via NPM
$ npm i -g @yerofey/cryptowallet-cli
```

## Usage
```bash
# generate random ERC-like wallet (ETH, BNB, POLYGON, ...)
$ cw

# generate random ERC-like wallet with desired prefix
$ cw -p aaa

# generate random BTC wallet (default format: bech32 - "bc1q...")
$ cw -c BTC

# generate random BTC wallet with desired prefix (case-insensitive)
$ cw -c BTC -p ABC

# generate random BTC wallet with desired prefix (case-sensitive)
$ cw -c BTC -P abc

# generate BTC legacy wallet ("1...")
$ cw -c BTC -f legacy

# generate BTC segwit wallet ("3...")
$ cw -c BTC -f segwit

# generate BTC bech32 wallet from mnemonic string
$ cw -c BTC -f bech32 -m "radio bright pizza pluck family crawl palm flame forget focus stock stadium"

# generate N of BTC bech32 wallets from mnemonic string
$ cw -c BTC -f bech32 -n 10 -m "radio bright pizza pluck family crawl palm flame forget focus stock stadium"

# generate ERC-like wallet from mnemonic string
$ cw -m "radio bright pizza pluck family crawl palm flame forget focus stock stadium"

# generate BNB (BEP2) wallet from mnemonic string
$ cw -c BNB -f BEP2 -m "radio bright pizza pluck family crawl palm flame forget focus stock stadium"

# generate BNB (BEP20) wallet from mnemonic string
$ cw -c BNB -f BEP20 -m "radio bright pizza pluck family crawl palm flame forget focus stock stadium"

# generate just a mnemonic string (12 words) to import in any wallet app
$ cw -m

# list all supported blockchains
$ cw -l
```

## Blockchains supported
- `BTC` (Bitcoin) [legacy, segwit, bech32]
- `ETH` (Ethereum)
- `BNB` (Binance Coin) [BEP2, BEP20, ERC20]
- `DOGE` (Dogecoin) [legacy, segwit, bech32]
- `BCH` (Bitcoin Cash)
- `LTC` (Litecoin) [legacy, segwit, bech32]
- `POLYGON` (Polygon)
- `TRX` (Tron)
- `XTZ` (Tezos)
- `DASH` (Dash)
- `DCR` (Decred)
- `ZEC` (Zcash)
- `QTUM` (Qtum)
- `BTG` (Bitcoin Gold)
- `ONE` (Harmony)
- `DGB` (DigiByte)
- `RDD` (ReddCoin)
- `VTC` (Vertcoin)
- `MONA` (MonaCoin)
- `NMC` (NameCoin)
- `PPC` (PeerCoin)
- `BLK` (BlackCoin)
- `VIA` (Viacoin)
- `NBT` (NIX Bridge Token)

*\*all other cryptos that are tokens in the ecosystems like Ethereum, Binance Smart Chain or Polygon and others (EVM compatible) are supported too, you just need to create ERC wallet (that is set by default)*

## Options
* `-b` or `-c` or `--chain`: Specify the blockchain ticker to generate a wallet for
* `-f` or `--format`: Specify the blockchain wallet format (for BTC: legacy, segwit, bech32)
* `-F` or `--filename`: Specify a filename (without extension) to output the data (works only with `-o` argument)
* `-g` or `--geek`: Display some additional "geeky" info
* `-l` or `--list`: List all supported blockchains
* `-m` or `--mnemonic`: Use a bip39 mnemonic phrase (if is set) to generate wallet, or leave it empty to generate new one
* `-n` or `--number`: Specify number of wallets to display (works for HD wallets only, like BTC/LTC/DOGE)
* `-o` or `--output`: Specify a file format (currently only `csv` supported) to output the generated data
* `-p` or `--prefix`: Specify desired prefix for the wallet address (**case-insensitive**)
* `-P` or `--prefix-sensitive`: Specify desired prefix of the wallet address (**case-sensitive**)
* `-s` or `--suffix`: Specify desired suffix for the wallet address (**case-insensitive**)
* `-S` or `--suffix-sensitive`: Specify desired suffix for the wallet address (**case-sensitive**)
* `-v` or `--version`: Display current version of CW tool

## Tested setups
* Node
- [x] v16.12.0
* NPM
- [x] v8.1.0
* Yarn
- [x] v1.23.0

## Highlights
- 24+ blockchains supported
- Generate wallet with desired prefix/suffix
- Generate wallet from mnemonic
- Generate just a mnemonic
- Works fully offline

## TODO
- Windows support
- Show SegWit Bech32 BTC change addresses with additional flag
- SegWit Bech32 wallet address support for all Bitcoin forks
- More EVM compatible cryptos
- tests

## Author
[Yerofey S.](https://github.com/yerofey)

## License
[MIT](https://github.com/yerofey/cryptowallet-cli/blob/master/LICENSE)
