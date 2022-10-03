# crypto-dev-notes
Notes taken as projects are built and courses are taken. This is starting out as a raw brain dump of notes, observations, project ideas, and more. Over time as this evolves, will try to adjust this to be more structured for newcomers.


## Learn Blockchain, Solidity, and Full Stack Web3 Development with JavaScript – 32-Hour Course

### General Notes
- *Blockchain Oracle* - Any device that interacts with the off-chain world to provide external data or computation to smart contracts
- The difference between smart contracts and hybrid smart contracts have some off chain data component
- Web 1 --> permissionless open sourced web with static content
- Web 2 --> permissioned web w/ dynamic content. Companies run *your* agreements on *their* servers
- Web 3 --> permissionless web w/ dynamic content. Decentralized censorship resistant networks run *your* agreements. *You* also own part of the protocol instead of just the product
- SCs (smart contracts) pave the way for immutable, trust minimized agreements. The three key points are decentralization, flexibility & transparency, and speed & efficiency (TODO: give an example of how to read and interpret a deployed SC. It would be especially nice to show counterparty risk being removed in the example)
- Testnet faucet: https://faucets.chain.link/
- TODO: Add a section on gas fee calculations
- Keccak-256 is the hashing algorithm used by Ethereum. A hash is a unique fixed length string which is meant for identifying a peice of data. This fixed length string is the output of the aforementioned hash algorithm. Example, f(x) where x is the data, and the output of f(x) is the unique fixed length string.
- The block, nonce, and data are passed through this hashing algorithm to get the unique string
- The private key is only known to the holder, and is used to sign transactions. The Elliptic Curve Digital Signature algorithm is what is used to generate the public key pair. People can verify transactions signed by the private key, by using the public key.
- Transaction Free = (Block Base Fee Per Gas + Max Priority Fee Per Gas) * Gas Used
- Blockchains have limited blockspace for transactions. The base gas fee for Ethereum will vary depending on usage. The key point is that the more transactions that are occurring (i.e. the more people that use Ethereum), the higher your gas fee will be so that *your* transaction can be included in the next block. The gas fee gets algorithmically adjusted so that all the blocks are 50% full. If they are more than 50% full, the base fee goes up (and vice versa). The longer the blockchain gets, the harder it is to tamper with.
- PoW and PoS fall under consenus (the mechanism used to agree on blockchain state)
- Chain selection and sybil resistance are 2 major components for a consensus mechanism.


## EVM Deep Dive
- For anyone reasonably experienced in programming at the beginner level, they should know that when a smart contract is compiled, the runtime bytecode generated contains all the functions defined in the contract.
- When viewing the compiled runtime bytecode of the contract, we can view a subset of the bytecode and see how this corresponds to a set of what's called *EVM opcodes*
- EVM opcodes are 1 byte in length, with 256 different possible opcodes (a finite set). The EVM only uses 140 unique opcodes.
- When a smart contract's function is called, there is calldata provided to specify the function signature being called, along with the corresponding arguments.
- Remember earlier how we mentioned the Keccak algorithm being used for Ethereum? The function signatures are defined as the first four bytes of the Keccak hash's canonical representation of the function signature.
- Canoncial representation of function signatures is the following: function name, function argument type

## Helpful Links
- https://www.youtube.com/watch?v=ZloHVKk7DHk
- https://andersbrownworth.com/blockchain
- eth-converter.com
- https://www.youtube.com/watch?v=MGemhK9t44Q
- EVM opcode references: https://www.ethervm.io/ https://www.evm.codes/?fork=grayGlacier
- EVM deep dive
