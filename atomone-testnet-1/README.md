**🔗 `atomone-testnet-1`**

![chain-id](https://img.shields.io/badge/chain%20id-atomone--testnet--1-blue?style=for-the-badge)
![version: v1.0.0](https://img.shields.io/badge/version-v1.0.0-green?style=for-the-badge)
![genesis-time](https://img.shields.io/badge/%E2%8F%B0%20genesis%20time-2025--01--22T14%3A00%3A000000000Z-red?style=for-the-badge)

> [!NOTE]
> The atomone-testnet-1 is a community initiative designed to test and validate the foundational components of the AtomOne blockchain.
> Its primary purpose is to provide a controlled environment for validators, developers, and community members to explore, test and optimize network functionalities before their official deployment/release.
> By participating in this testnet, participants can register their nodes in the genesis block, fine-tune their configurations, and help ensure the network's robustness and security.
 
**Register in the Genesis**

To register your validator node in the `genesis.json` you will need to provide a signed `gentx` with an initial delegation of at least `1000000uatone`. To create your own genesis transaction (`gentx`) you will have to choose the following parameters for your validator: `commission-rate` (>=0.05), `commission-max-rate`, `commission-max-change-rate`, `min-self-delegation` (>=1), `website` (optional), `details` (optional), `identity` ([keybase](https://keybase.io/) key hash, used to get validator logos in block explorers - optional), `security-contact` (email - optional).

The `commission-rate`, `commission-max-rate`, `commission-max-change-rate` are free to set to the value you want, this values are just for example, note that 0.05 is 5%.

```sh
# Init node
$ atomoned init your-moniker --chain-id atomone-testnet-1

# Create key, remember to store your mnemonic
$ atomoned keys add your-key-name

# Set initial balance
$ atomoned genesis add-genesis-account your-key-name 10000000uatone

# Create the gentx
$ atomoned genesis gentx your-key-name 1000000uatone \
  --node-id $(atomoned tendermint show-node-id) \
  --chain-id atomone-testnet-1 \
  --commission-rate 0.05 \
  --commission-max-rate 0.1 \
  --commission-max-change-rate 0.05 \
  --min-self-delegation 1 \
  --website "https://foo.network" \
  --details "My validator" \
  --identity "id-from-keybase" \
  --security-contact "security@foo.network"
```

**Operate the node**

**Install the binary**

- You can install the proposed chain binary from github release page

https://github.com/atomone-hub/atomone/releases/tag/v1.0.0

- Build from the source

You need to have [go](https://go.dev/doc/install) installed

```
$ git clone https://github.com/atomone-hub/atomone.git
$ cd atomone
$ git checkout v1.0.0
$ make install
```

**Recommendations**

| minimum-gas-prices | 0.001uatone |
| --- | --- |
| seeds | see [./seeds.txt](https://github.com/atomone-hub/atomone-validator-community/blob/main/atomone-1/seeds.txt) |
| persistent_peers | see [./persistent_peers.txt](https://github.com/atomone-hub/atomone-validator-community/blob/main/atomone-1/persistent_peers.txt) |

**Hardware recommendation**

AtomOne is a relatively simple and vanilla Cosmos SDK chain with minor modifications. The recommended minimum hardware requirements should be enough to comfortably be able to run a validator node.

- 4 Cores
- 8 GB RAM
- 512 GB disk space (could increase over time, will need to monitor disk usage)

**Network informations**

You can get a list of public Explorers, RPCs, seed node, persistent_peers... on [cosmos.directory/atomone](https://testnet.cosmos.directory/atomone)
