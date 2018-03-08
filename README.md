# The Ultimate Collection of Ethereum, Solidity and Smart Contracts Interview Questions

You can use this collection of questions for interviews or as a cheatsheet to refresh your knowledge.
Feel free to contribute to the list.

## Table of Contents

  1. [Ethereum](#ethereum)
  1. [Ethereum client (Geth)](#ethereum-client-geth)
  1. [Smart Contracts and Solidity](#smart-contracts-and-solidity)
  

## Ethereum

**Q**: What is the value token for Ethereum?
>**A**: Ether (ETH)


**Q**: What is the difference between Wei and Ether?
**A**: Wei is a denomination, like cents to Dollars or pennies to Pounds. 1 ETH = 10^18 Wei

**Q**: What is the average block time in Ethereum?
**A**: ~14 seconds

**Q**: What is the average block size in Ethereum?
**A**: Around 2KB, although it depends.

**Q**: Does Ethereum support scripting? If so, what types of scripting?
**A**: Yes. It supports Smart Contracts 

**Q**: How do you get Ethers?
**A**: There are a few ways: 
    1. Become a miner
    2. Trade other currencies
    3. Ether faucets like https://faucet.metamask.io
    4. Receive Ethers from others

**Q**: Where do Ethers come from?
**A**: 60 million were first created in a presale in 2014. Also, ethers are created when a block is mined.

**Q**: What is a node?
**A**: A node is essentially a computer, connected to the network, which processes transactions.

**Q**: How many Ethereum networks are you familiar with?
**A**: There are three types of network - Live Network (Main), Test Network (Ropsten, Rinkeby) and Private Network.

**Q**: What are some ways to interact with a network?
**A**: You can either use a Wallet or a DApp

**Q**: Can you "hide" a transaction?
**A**: No. All transactions are visible to everyone.

**Q**: Where are transactions recorded?
**A**: In the public ledger.

**Q**: What are the ids of those networks?
**A**: Live (id=1), Ropsten (id=3), Rinkeby (id=4), Private (assigned by the developer)

**Q**: So I can mine some Ethers in Rinkeby and transfer them to Live network, right?
**A**: No, you can't transfer Ether between networks.

**Q**: Why would you have a private network?
**A**: There are many reasons, but mainly because of data privacy, distributed database, permissions control and testing.

**Q**: How can you easily see details about transactions and blocks?
**A**: Using blockchain explorers like etherscan.io or live.ether.camp
 
**Q**: What about private network?
**A**: You can do it using open source explorer clients (like https://github.com/etherparty/explorer)

**Q**: What is consensus in blockchain?
**A**: The process of validating transactions (creating blocks) following a specific protocol (like Ethereum).

**Q**: What are the two commonly used consensus models in blockchain?
**A**: Proof of work and proof of stake.

**Q**: Explain proof of work in a simple way.
**A**: It is essentially a puzzle which miners have to solve in order to generate proof of work and validate a transaction. It is computationally intensive.

**Q**: Explain proof of stake in a simple way.
**A**: The creator of the block is chosen randomly by means of wealth and age (stake). It is not computationally intensive.

**Q**: What consensus model does Ethereum use?
**A**: As of the beginning of 2018 it uses Proof of work but it is going to switch to Proof of stake.

**Q**: How can you mine Ethers?
**A**: Using a wallet or geth cli

**Q**: What is used to sign transactions?
**A**: User's private key.

**Q**: Can you recover your Ethereum account after losing your private key?
**A**: Yes, you can use your 12 word mnemonic.



## Ethereum client (Geth)

**Q**: What are some ways to connect to a node?
**A**: IPC-RPC, JSON-RPC and WS-RPC.

**Q**: So what is Geth?
**A**: Geth is an Ethereum cli client.

**Q**: What is the default way of connecting to a geth client?
**A**: IPC-RPC is enabled by default, every other RPC is disabled.

**Q**: What geth APIs are you aware of?
**A**: Admin, eth, web3, miner, net, personal, shh, debug and txpool.

**Q**: Which RPCs can you use to connect to a geth client over the network?
**A**: You can connet to a geth client over the network using JSON-RPC and WS-RPC. IPC-RPC can only connect to geth clients on the same machine.

**Q**: If you pass option --rpc which RPC gets enabled?
**A**: JSON-RPC.

**Q**: Which RPC APIs are enabled by default?
**A**: eth, web3 and net. 

**Q**: How would you enable admin api for JSON RPC?
**A**: By using the option --rpcapi 

**Q**: What does the option --datadir do?
**A**: It specifies where the blockchain will be stored.

**Q**: What is geth's "fast" sync, and why is it faster?
**A**: Instead of processing the entire blockchain one link at a time and replay all transactions that ever happened, fast sync downloads transaction receipts along with the blocks and pulls an entire recent state database.

**Q**: What does --testnet do?
**A**: It connects the client to Ropsten network. 

**Q**: Starting the geth client dumps a lot of output on the screen. How would you reduce the noise?
**A**: By setting --verbosity to a lower number (default is 3)

**Q**: How can you connect one geth client to another using IPC-RPC?
**A**: First start a geth client, copy its pipe location, then start another geth client using the same datadir and passing --attach with the pipe location.

**Q**: How would you load custom javascript files into your geth console?
**A**: By passing --preload and the path of the file. 

**Q**: Where are geth client accounts stored?
**A**: In the keystore directory.

**Q**: What do you have to do with an account in order to make transactions?
**A**: You have to unlock that account with --unlock by passing the account address or index. You can also specify a --password file where all passwords reside for each account.

**Q**: You mentioned something about indexes. What determines the account index?
**A**: The order in which you add the accounts.

**Q**: Is it possible to mine using geth?
**A**: Yes, by passing --mine option.

**Q**: What is "etherbase"?
**A**: This is the account which receives the mining awards, which is account with index 0.





## Smart Contracts and Solidity

**Q**: So what is a Smart Contract?
**A**: It is computer code written in multiple languages. Smart contracts live on the network. They enforce rules and perform actions, negotiated by participants in those contracts. 

**Q**: What languages can Smart Contracts be written in? 
**A**: Solidity, which is the most commonly used language, Serpent and Lisp Like Language

**Q**: Example of a Smart Contract use case?
**A**: A popular Seller-Buyer scenario where a Buyer deposits money in the smart contracts, Seller sees the deposit and sends the goods, Buyer receives the goods and releases the payment.

**Q**: What is Metamask?
**A**: Metamask is a tool which helps you to easily interact with the Ethereum networks in your browser

**Q**: What node does Metamask use?
**A**: It uses infura.io

**Q**: What does Metamask NOT support?
**A**: Mining and contract deployment.

**Q**: Is execution of contracts free?
**A**: No, invoking contract methods is a transaction.

**Q**: Is accessing a Smart Contract state free?
**A**: Yes, querying state is not a transaction.

**Q**: Who executes the contracts?
**A**: Miners.

**Q**: Why does it cost money to invoke a method on a Smart Contract?
**A**: Some methods, which do not modify the state of the contract and have no logic other than returning a value, are free.
Apart from sending ether as a payment, invoking methods that make change the state cost money also because they require gas for execution.

**Q**: Why is there gas, more precisely?
**A**: Since miners execute contract code on their machines, they must cover their costs from executing the code requested by a caller.

**Q**: Does gas price determine when a transaction is processed?
**A**: Yes and no. The higher the gas price, the more likely your transaction will be mined. Despite, gas price is not a guarantee for faster transaction processing.

**Q**: What does the gas usage in a transaction depend on?
**A**: It depends on amount of storage, and type and number of instructions (opt codes). Each EVM opt code has a fixed amount of gas. 

**Q**: And how is transaction fee calculated?
**A**: Gas used * gas price (specified by the caller)

**Q**: If an execution of a Smart Contract costs less than the specified gas, does the user get a refund?
**A**: Yes

**Q**: What happens if the execution of a Smart Contract costs more than the specified gas?
**A**: The user doesn't get a refund and also the execution halts as soon as all the gas is used up and no changes are made to the contract.

**Q**: Who pays for Smart Contracts invocation?
**A**: The user who invokes the contract.

**Q**: What do nodes run Smart Contracts code on? 
**A**: EVM - Ethereum Virtual Machine. EVM follows the EVM specification, which is part of the Ethereum protocol. EVM is simply a process on the node.

**Q**: What does the EVM need in order to run a Smart Contract?
**A**: It needs the contract's bytecode which is generated from compiling a higher-level language such as Solidity.

**Q**: What are the segments of EVM on a higher level?
**A**: Memory area, Stacks and Execution engine.

**Q**: What is Remix?
**A**: An online tool for developing, testing and deloying contracts. It's great for quickly building and testing lightweight contracts but not for more complex ones.

**Q**: In Remix, what nodes can you connect to?
**A**: You can connect to a public node using Metamask, local node using Geth and simulated memory node in the Javascript VM.

**Q**: What is a DApp and why is it different than a normal App?
**A**: An App usually consists of a client which communicates to some centralized resources (owned by an organization). 
There is a mid-tier connecting to a centralized data tier. If information in the centralized data tier is lost, it cannot be recovered (easily).
DApp means Decentralized Application. DApps interact with the network via Smart Contracts. The data they work with resides in the contract instance.
Centralized data can be compromised more easily than decentralized.





## DApps and web3

**Q**: Is the front end of a DApp restricted to any technology/framework?
**A**: No. You can use anything you want, like HTML, CSS, JS, Java, Python, the list goes on.

**Q**: What does the front end use in order to connect to the backend (Smart Contracts)?
**A**: Web3 API libraries.

**Q**: What do you need in order to interact with a contract from a DApp?
**A**: The contract's ABI and bytecode. 

**Q**: What is the ABI used for?
**A**: ABI is a description of the public interface of a contract, which is used by DApps for invoking the contract.

**Q**: What is the bytecode used for?
**A**: The EVM on each node requires bytecode in order to execute the contract code.

**Q**: Why would you use BigNumber library?
**A**: Because Javascript does not handle big numbers correctly.

**Q**: Why is it necessary to always check if the web3 provider is set in the beginning of your web DApp code?
**A**: Because Metamask injects it and overwrites the any other web3 with its own.

**Q**: Why would you use version web3 js 1.x instead of 0.2x.x?
**A**: Mainly because its async calls use promises instead of callbacks, which is preferred in the javascript world.

**Q**: How to list accounts in web3 1.x?
**A**: web3.eth.getAccounts

**Q**: What is the difference between .call and .send?
**A**: .send sends a transaction and costs moeny while .call queries the state of the contract.

**Q**: Is sending one ether like this ".send({ value: 1 })" okay?
**A**: No, you send 1 wei. Transactions always work with wei.

**Q**: So in order to send 1 ether I have to mutiply the value by 10^18?
**A**: You can use the util method web3.utils.toWei(1, 'ether')

**Q**: What do I have to specify when calling ".send()"?
**A**: You must specify "from" which is the sender address. Everything else is optional.

**Q**: The only function of web3.eth.sendTransaction() is to send ethers to a specific address, is that correct?
**A**: No, you can also invoke contract methods.

**Q**: Do you know any solutions for scalability in Ethereum?
**A**: 2-layer protocols. Possible solutions are state channels and plasma.
