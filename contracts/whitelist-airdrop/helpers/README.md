merkle-airdrop-cli
==================

This is a helper client shipped along contract.
Use this to generate root, generate proofs and verify proofs

## Installation

```shell
yarn install
yarn link
```

Binary will be placed to path.

## Airdrop file format

```json
[
  { "address": "wasm1k9hwzxs889jpvd7env8z49gad3a3633vg350tq", "amount": "1"},
  { "address": "wasm1uy9ucvgerneekxpnfwyfnpxvlsx5dzdpf0mzjd", "amount": "1"}
]
```

## Commands

**Generate Root:**
```shell
merkle-airdrop-cli generateRoot --file ../testdata/airdrop_stage_2_list.json
```

**Generate proof:**
```shell
merkle-airdrop-cli generateProofs --file ../testdata/airdrop_stage_1_list.json \
  --address terra1tt66jqq5u4xygxdw69nhk98jvrz0hjd4xaz766 \
  --amount 1
```

**Verify proof:**
```shell
PROOFS='[ "27e9b1ec8cb64709d0a8d3702344561674199fe81b885f1f9c9b2fb268795962","280777995d054081cbf208bccb70f8d736c1766b81d90a1fd21cd97d2d83a5cc","3946ea1758a5a2bf55bae1186168ad35aa0329805bc8bff1ca3d51345faec04a"
]'
merkle-airdrop-cli verifyProofs --file ../testdata/airdrop.json \
  --address terra1tt66jqq5u4xygxdw69nhk98jvrz0hjd4xaz766 \
  --amount 1 \
  --proofs $PROOFS
```
