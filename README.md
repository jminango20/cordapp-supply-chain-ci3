# Proof of Concepts of Corda Blockchain Technology Applied on the Supply Chain Area

This repository shows the proof of concepts (PoC) implemented in CorDapp of the corresponding article.
This repository simulates a supply chain workflow.
It's been created based on the CorDapp template provided [here](https://github.com/corda/cordapp-template-kotlin). 

The main parties of the workflow are the:
* `Producer`,
* `Distributor A`,
* `Distributor B`,
* `Final Destination`,
* `Notary`,

Each cargo from the Producer must be send to Distributor A, later to Distributor B, then the
cargo arrives to Final Destination via a pre-arranged list of co-operating parties.

The main *flows* are the following:
* `EnterFlow`: triggered by the Producer that will be the first in the supply chain, notifying all the involved distributors about the expected cargo to be send.
* `ArrivalFlow`: triggered when the cargo arrives at the Distributor A or Distribuitor B, notifying all the involved parties that the cargo has arrived at the next station.
* `ExitFlow`: triggered by the final destination that is the last in the chain, essentially notifying the other parties that the cargo has been delivered.

The cargo items are represented via a `LinearState` in the ledger.

## How to run this code from terminal

* Deploy nodes
```
./gradlew deployNodes
```
* Start the nodes
```
./build/nodes/runnodes
```