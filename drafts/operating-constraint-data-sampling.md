# Operating Constraint Data Sampling
Numerous methods for validating "intent operating constraints" requiring historical onchain data probably exist.

Below are two examples for how it can be done today.

## Light Client
To access historical onchain `Events` a light client can be used to verify Event Log bundles.

<img width="100%" alt="enforcers-lightclient" src="https://github.com/delegatable/research/assets/3408362/12ff57f5-6efb-4070-863e-bb2764245914">

Events can be verified onchain by verifying an Ethereum merkle proofs.

Examples of verify state with merkle proofs
- https://github.com/zmitton/eth-proof
- https://github.com/pipeos-one/goldengate/blob/master/contracts/contracts/lib/MPT.sol
- https://github.com/lorenzb/proveth
- https://github.com/figs999/Ethereum/blob/master/EventStorage.sol

Resources:
- https://medium.com/coinmonks/ethereum-data-transaction-receipt-trie-and-logs-simplified-30e3ae8dc3cf

## Zero-Knowledge
To access historical onchain `Storage` a coprocessor (like https://github.com/axiom-crypto/axiom-sdk) can be used to create proofs of blockchain storage slots.

<img width="100%" alt="enforcer-zk" src="https://github.com/delegatable/research/assets/3408362/46eb21ec-5c96-4aff-a799-55c3338a92d9">


