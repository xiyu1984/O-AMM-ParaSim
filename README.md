# O-AMM-Simulation Parachain Node

We provide an intuitive on-chain prototype to demonstrate the off-chain calculation and on-chain verification mechanisms, whose advantages are described [here](https://github.com/xiyu1984/o-amm/blob/main/Principle%20of%20Omniverse%20AMM.md#gas-mechanism).  

## How to try
### Start local Node
* Clone this repo, and build it.
  ```sh
  cargo build --package node-template --release
  ```
* Start the node locally.
  ```sh
  ./target/release/node-template --dev
  ```
* Go to [polkadot.js.org/apps](https://polkadot.js.org/apps/#/explorer) and connect to the local node.

### Try is manually
* Go to [off-chain-calc](./off-chain-calc/) and follow the [tutorial](./off-chain-calc/README.md) to operate.  
