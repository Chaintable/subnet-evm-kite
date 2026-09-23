# DeBank Kite Fork

This repository is Chaintable's fork of `gokite-ai/subnet-evm` for integrating Kite mainnet (chainID 2366) into the DeBank generic blockchain node pipeline.

## Kite v1.15.0 and later

Kite upstream moved Subnet-EVM into `gokite-ai/avalanchego/graft/subnet-evm`.
The maintained writer implementation now lives in
`Chaintable/avalanchego-x-kite/graft/subnet-evm`, including pipeline hooks and
the existing Kite TxDenyList extension. This repository retains the
`kite-writer` image build/release workflows; `Dockerfile.debank` builds both
the host and plugin from the single `AVALANCHE_VERSION` commit pinned in those
workflows. The legacy Go sources here are retained for history and are no
longer used in v1.15.0 images.

Change node code in `avalanchego-x-kite`, then update the pinned commit here.
The plugin ID, executable locations and `vm-trace-config` interface are
unchanged. Both components must be upgraded together for plugin protocol 46.

## Historical layout

- `debank` branch — DeBank extension layer (PipelineTracer hook + Dockerfile.debank + GHA workflows) cherry-picked on top of `gokite-ai/subnet-evm@feature/tx-deny-list`
- `upstream` branches — pure sync with `gokite-ai/subnet-evm`, no DeBank patches

## Key references

- Integration plan: `~/code/task_kite/kite_integration_plan.md` (DeBank internal)
- Execution log: `~/code/task_kite/docs/todo.md` (DeBank internal)
- Output ECR image: `public.ecr.aws/b2h7a5c4/chaintable/kite-writer`
- Plugin VMID: `pJhES6xZkqZxjxMqHiucbpBTTnB97EjL5aTYSynmWBoF26v9e`
- Kite mainnet IDs: Subnet `21uUaTxVdR3Sp6SJhpcSrdH1g66aFoE8mPQDvwKJCjXNexo5y6`, Blockchain `3USaEfTcoUhHxpKXvpAG916UKCUEyjrtkg2hBArBG3JyDP7my`
