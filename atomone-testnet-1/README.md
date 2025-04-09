# 🔗 `atomone-testnet-1`

![chain-id](https://img.shields.io/badge/chain%20id-atomone--testnet--1-blue?style=for-the-badge)
![version: v1.1.2](https://img.shields.io/badge/version-v1.1.2-green?style=for-the-badge)

## Versions

- [v2.0.0-rc1](./upgrades/v2.0.0-rc1.md) - [v2.0.0-rc1](https://github.com/atomone-hub/atomone/releases/tag/v2.0.0-rc1)
- [Security upgrade v1.1.2](./upgrades/v1.1.2.md) - [v1.1.2](https://github.com/atomone-hub/atomone/releases/tag/v1.1.2) (current)
- [Genesis](./upgrades/genesis.md) - [v1.1.1](https://github.com/atomone-hub/atomone/releases/tag/v1.1.1)

## Operate the node

### Install the binary

- You can install the proposed chain binary from github release page

https://github.com/atomone-hub/atomone/releases/tag/v1.1.2

- Build from the source

You need to have [go](https://go.dev/doc/install) installed

```sh
$ git clone https://github.com/atomone-hub/atomone.git
$ cd atomone
$ git checkout v1.1.2
$ make install
```

### Setup [genesis.json](https://atomone.fra1.digitaloceanspaces.com/genesis.json)

```bash
$ wget -O $HOME/.atomone/config/genesis.json https://atomone.fra1.digitaloceanspaces.com/genesis.json
```


### Recommendations

| minimum-gas-prices | 0.025uatone                                          |
|--------------------|------------------------------------------------------|
| seeds              | see [./seeds.txt](./seeds.txt)                       |
| persistent_peers   | see [./persistent_peers.txt](./persistent_peers.txt) |


## Hardware recommendation

AtomOne is a relatively simple and vanilla Cosmos SDK chain with minor modifications. The recommended minimum hardware requirements should be enough to comfortably be able to run a validator node.

- 4 Cores
- 8 GB RAM
- 512 GB disk space (could increase over time, will need to monitor disk usage)


## Network informations

You can get a list of public Explorers, RPCs, seed node, persistent_peers... on [testnet.cosmos.directory/atomone](https://testnet.cosmos.directory/atomone)
