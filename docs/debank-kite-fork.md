# DeBank Kite Fork

This repository is Chaintable's fork of `gokite-ai/subnet-evm` for integrating Kite mainnet (chainID 2366) into the DeBank generic blockchain node pipeline.

## Layout

- `debank` branch — DeBank extension layer (PipelineTracer hook + Dockerfile.debank + GHA workflows) cherry-picked on top of `gokite-ai/subnet-evm@feature/tx-deny-list`
- `upstream` branches — pure sync with `gokite-ai/subnet-evm`, no DeBank patches

## Key references

- Integration plan: `~/code/task_kite/kite_integration_plan.md` (DeBank internal)
- Execution log: `~/code/task_kite/docs/todo.md` (DeBank internal)
- Output ECR image: `294354037686.dkr.ecr.ap-northeast-1.amazonaws.com/blockchain/kite-x`
- Plugin VMID: `pJhES6xZkqZxjxMqHiucbpBTTnB97EjL5aTYSynmWBoF26v9e`
- Kite mainnet IDs: Subnet `21uUaTxVdR3Sp6SJhpcSrdH1g66aFoE8mPQDvwKJCjXNexo5y6`, Blockchain `3USaEfTcoUhHxpKXvpAG916UKCUEyjrtkg2hBArBG3JyDP7my`
