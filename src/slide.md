---
marp: true
paginate: true
---

# Fe言語に触れてみる

---

## 自己紹介
- [haryu703](https://twitter.com/haryu703)
- コインチェック株式会社 (2020~)

---
## Fe言語とは
- https://github.com/ethereum/fe
- Ethereum向けのスマートコントラクト記述用言語
  - SolidityやVyperと同類
  - Solidityなどと同様、YULという中間言語を利用する
- RustとPythonに影響された文法
- まだalpha版

---
## インストール
```bash
$ curl -fsSL https://github.com/ethereum/fe/releases/download/v0.19.1-alpha/fe_amd64 -o fe
$ chmod +x ./fe
```
- インストーラなどはないのでバイナリをダウンロードするだけ

---

## Usage
```bash
$ ./fe
fe 0.19.1-alpha
The Fe Developers <snakecharmers@ethereum.org>
An implementation of the Fe smart contract language

USAGE:
    fe <SUBCOMMAND>

OPTIONS:
    -h, --help       Print help information
    -V, --version    Print version information

SUBCOMMANDS:
    build    Build the current project
    check    Analyze the current project and report errors, but don't build artifacts
    help     Print this message or the help of the given subcommand(s)
    new      Create new fe project
```

---

## 使ってみる
```bash
$ curl -fsSLO https://raw.githubusercontent.com/ethereum/fe/master/crates/test-files/fixtures/demos/erc20_token.fe
$ ./fe build erc20_token.fe
Compiled erc20_token.fe. Outputs in `output`
$ ls output/ERC20
ERC20_abi.json  ERC20.bin
```

- ERC20.bin は hex の bytecode
- ERC20_abi.json はコントラクトのABI
  - 若干おかしい？
    - `function`が全部`payable`になってる

---

## 読んでみる
https://github.com/haryu703/ccstudy-sp-2022-08/blob/master/example/erc20_token.fe

---

## 終わりに

- 完成度やエコシステムが充実すれば使いやすそう
- 想像以上にalpha版
