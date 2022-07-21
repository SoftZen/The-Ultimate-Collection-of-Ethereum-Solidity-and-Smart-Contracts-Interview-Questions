# The Ultimate Collection of Ethereum, Solidity and Smart Contracts Interview Questions

You can use this collection of questions for interviews or as a cheatsheet to refresh your knowledge.

Feel free to contribute to the list.

## Table of Contents

  1. [Ethereum](#ethereum)
  1. [Ethereum client (Geth)](#ethereum-client-geth)
  1. [Smart Contracts and Solidity](#smart-contracts-and-solidity)
  1. [DApps and web3](#dapps-and-web3)
  1. [Solidity](#solidity)

## Ethereum

 What is the value token for Ethereum?
>Ether (ETH)


 What is the difference between Wei and Ether?
>Wei is a denomination, like cents to Dollars or pennies to Pounds. 1 ETH = 10^18 Wei



 What is the average block time in Ethereum?
>~14 seconds

 What is the average block size in Ethereum?
>Around 2KB, although it depends.

 Does Ethereum support scripting? If so, what types of scripting?
>Yes. It supports Smart Contracts 

 How do you get Ethers?
>There are a few ways: 
    1. Become a miner
    2. Trade other currencies
    3. Ether faucets like https://faucet.metamask.io
    4. Receive Ethers from others

 Where do Ethers come from?
>60 million were first created in a presale in 2014. Also, ethers are created when a block is mined.

 What is a node?
>A node is essentially a computer, connected to the network, which processes transactions.

 How many Ethereum networks are you familiar with?
>There are three types of network - Live Network (Main), Test Network (Ropsten, Rinkeby) and Private Network.

 What are some ways to interact with a network?
>You can either use a Wallet or a DApp

 Can you "hide" a transaction?
>No. All transactions are visible to everyone.

 Where are transactions recorded?
>In the public ledger.

 What are the ids of those networks?
>Live (id=1), Ropsten (id=3), Rinkeby (id=4), Private (assigned by the developer)

 So I can mine some Ethers in Rinkeby and transfer them to Live network, right?
>No, you can't transfer Ether between networks.

 Why would you have a private network?
>There are many reasons, but mainly because of data privacy, performances, distributed database, permissions control and testing.

 How can you easily see details about transactions and blocks?
>Using blockchain explorers like etherscan.io or live.ether.camp
 
 What about private network?
>You can do it using open source explorer clients (like https://github.com/etherparty/explorer)

 What is consensus in blockchain?
>The process of validating transactions (creating blocks) following a specific protocol (like Ethereum).

 What are the two commonly used consensus models in blockchain?
>Proof of work and proof of stake.

 Explain proof of work in a simple way.
>It is essentially a puzzle which miners have to solve in order to generate proof of work and validate a transaction. It is computationally intensive.

 Explain proof of stake in a simple way.
>The creator of the block is chosen randomly by means of wealth and age (stake). It is not computationally intensive.

 What consensus model does Ethereum use?
>As of the beginning of 2018 it uses Proof of work but it is going to switch to Proof of stake.

 How can you mine Ethers?
>Using a wallet or geth cli

 What is used to sign transactions?
>User's private key.

 Can you recover your Ethereum account after losing your private key?
>Yes, you can use your 12 word mnemonic.



## Ethereum client (Geth)

 What are some ways to connect to a node?
>IPC-RPC, JSON-RPC and WS-RPC.

 So what is Geth?
>Geth is an Ethereum cli client.

 What is the default way of connecting to a geth client?
>IPC-RPC is enabled by default, every other RPC is disabled.

 What geth APIs are you aware of?
>Admin, eth, web3, miner, net, personal, shh, debug and txpool.

 Which RPCs can you use to connect to a geth client over the network?
>You can connet to a geth client over the network using JSON-RPC and WS-RPC. IPC-RPC can only connect to geth clients on the same machine.

 If you pass option --rpc which RPC gets enabled?
>JSON-RPC.

 Which RPC APIs are enabled by default?
>eth, web3 and net. 

 How would you enable admin api for JSON RPC?
>By using the option --rpcapi 

 What does the option --datadir do?
>It specifies where the blockchain will be stored.

 What is geth's "fast" sync, and why is it faster?
>Instead of processing the entire blockchain one link at a time and replay all transactions that ever happened, fast sync downloads transaction receipts along with the blocks and pulls an entire recent state database.

 What does --testnet do?
>It connects the client to Ropsten network. 

 Starting the geth client dumps a lot of output on the screen. How would you reduce the noise?
>By setting --verbosity to a lower number (default is 3)

 How can you connect one geth client to another using IPC-RPC?
>First start a geth client, copy its pipe location, then start another geth client using the same datadir and passing --attach with the pipe location.

 How would you load custom javascript files into your geth console?
>By passing --preload and the path of the file. 

 Where are geth client accounts stored?
>In the keystore directory.

 What do you have to do with an account in order to make transactions?
>You have to unlock that account with --unlock by passing the account address or index. You can also specify a --password file where all passwords reside for each account.

 You mentioned something about indexes. What determines the account index?
>The order in which you add the accounts.

 Is it possible to mine using geth?
>Yes, by passing --mine option.

 What is "etherbase"?
>This is the account which receives the mining awards, which is account with index 0.





## Smart Contracts and Solidity

 So what is a Smart Contract?
>It is computer code written in multiple languages. Smart contracts live on the network. They enforce rules and perform actions, negotiated by participants in those contracts. 

 What languages can Smart Contracts be written in? 
>Solidity, which is the most commonly used language, Serpent and Lisp Like Language

 Example of a Smart Contract use case?
>A popular Seller-Buyer scenario where a Buyer deposits money in the smart contracts, Seller sees the deposit and sends the goods, Buyer receives the goods and releases the payment.

 What is Metamask?
>Metamask is a tool which helps you to easily interact with the Ethereum networks in your browser

 What node does Metamask use?
>It uses infura.io

 What does Metamask NOT support?
>Mining and contract deployment.

 Is execution of contracts free?
>No, invoking contract methods is a transaction.

 Is accessing a Smart Contract state free?
>Yes, querying state is not a transaction.

 Who executes the contracts?
>Miners.

 Why does it cost money to invoke a method on a Smart Contract?
>Some methods, which do not modify the state of the contract and have no logic other than returning a value, are free.
Apart from sending ether as a payment, invoking methods that make change the state cost money also because they require gas for execution.

 Why is there gas, more precisely?
>Since miners execute contract code on their machines, they must cover their costs from executing the code requested by a caller.

 Does gas price determine when a transaction is processed?
>Yes and no. The higher the gas price, the more likely your transaction will be mined. Despite, gas price is not a guarantee for faster transaction processing.

 What does the gas usage in a transaction depend on?
>It depends on amount of storage, and type and number of instructions (opt codes). Each EVM opt code has a fixed amount of gas. 

 And how is transaction fee calculated?
>Gas used * gas price (specified by the caller)

 If an execution of a Smart Contract costs less than the specified gas, does the user get a refund?
>Yes

 What happens if the execution of a Smart Contract costs more than the specified gas?
>The user doesn't get a refund and also the execution halts as soon as all the gas is used up and no changes are made to the contract.

 Who pays for Smart Contracts invocation?
>The user who invokes the contract.

 What do nodes run Smart Contracts code on? 
>EVM - Ethereum Virtual Machine. EVM follows the EVM specification, which is part of the Ethereum protocol. EVM is simply a process on the node.

 What does the EVM need in order to run a Smart Contract?
>It needs the contract's bytecode which is generated from compiling a higher-level language such as Solidity.

 What are the segments of EVM on a higher level?
>Memory area, Stacks and Execution engine.

 What is Remix?
>An online tool for developing, testing and deloying contracts. It's great for quickly building and testing lightweight contracts but not for more complex ones.

 In Remix, what nodes can you connect to?
>You can connect to a public node using Metamask, local node using Geth and simulated memory node in the Javascript VM.

 What is a DApp and why is it different than a normal App?
>An App usually consists of a client which communicates to some centralized resources (owned by an organization). 
There is a mid-tier connecting to a centralized data tier. If information in the centralized data tier is lost, it cannot be recovered (easily).
DApp means Decentralized Application. DApps interact with the network via Smart Contracts. The data they work with resides in the contract instance.
Centralized data can be compromised more easily than decentralized.

 What exactly is EVM bytecode?
>EVM bytecode is a low-level programming language that is compiled from a high-level programming     language like Solidity. EVM is a virtual machine that sits between the operating system and the application layer to reduce OS dependency. Ethereum smart contracts, thanks to EVM, can be run on nearly any computer. The EVM bytecode comprises opcodes, which are EVM elementary instructions. These opcodes define basic operations such as adding two numbers (ADD), loading data from memory (mload), and so on. The Ethereum yellow paper defines over 100 of these opcodes. We need higher languages like Solidity to help us reason at a higher level of abstraction because coding directly using opcodes would be incredibly tiresome
 
 What is a library and how many types are there?
>A library is a piece of code that other smart contracts can re-use. There are 2 types of libraries:
 Deployed- They have their own address, and several other smart contracts can use them.
 Embedded- They don’t have their own address and are deployed as part of the code of the smart contract that uses them.

 Is it feasible to send a transaction without having to charge customers for gas?
>You’ll often find this question among the Solidity developer interview questions, and the answer is Yes. You'd have people sign a message on the front end first. The message and signature would then be routed to a centralized backend (off-chain) that would establish a transaction and include the payload (message + signature). This means that instead of the user's wallet, the app's wallet will cover gas costs. A smart contract will validate the signature's validity and perform an activity on behalf of the user on the blockchain.

 What are two APIs that a smart-contract uses to interact with?
>This is one of the most popular Solidity interview questions. eth_sendTransaction (transaction) and eth_call (call) are the two APIs that are used by a smart contract to interface. Transactions are expensive (gas) and can change the blockchain. Calls don't cost anything; therefore, they can't change the blockchain. However, calls can return a value, which isn't the case with transactions.

 How can you protect yourself from re-entrancy attack?
>You will frequently come across this Solidity developer interview question.
Solution 1: Lower balances and update other state variables before invoking the other contract. Solution 2: Implement a re-entrancy guard that uses a variable to determine when a call is second in the stack. Solution 3: Limit the amount of gas available to the called contract. This is automatically done if you use transfer().

 What is the equivalence of Javascript console.log for debugging in Solidity?
>This question is often a part of the Solidity developer interview questions. In Solidity, there is no comparison; however, you can use events, even if they aren't built for this.


## DApps and web3

 Is the front end of a DApp restricted to any technology/framework?
>No. You can use anything you want, like HTML, CSS, JS, Java, Python, the list goes on.

 What does the front end use in order to connect to the backend (Smart Contracts)?
>Web3 API libraries.

 What do you need in order to interact with a contract from a DApp?
>The contract's ABI and bytecode. 

 What is the ABI used for?
>ABI is a description of the public interface of a contract, which is used by DApps for invoking the contract.

 What is the bytecode used for?
>The EVM on each node requires bytecode in order to execute the contract code.

 Why would you use BigNumber library?
>Because Javascript does not handle big numbers correctly.

 Why is it necessary to always check if the web3 provider is set in the beginning of your web DApp code?
>Because Metamask injects it and overwrites the any other web3 with its own.

 Why would you use version web3 js 1.x instead of 0.2x.x?
>Mainly because its async calls use promises instead of callbacks, which is preferred in the javascript world.

 How to list accounts in web3 1.x?
>web3.eth.getAccounts

 What is the difference between .call and .send?
>.send sends a transaction and costs moeny while .call queries the state of the contract.

 Is sending one ether like this ".send({ value: 1 })" okay?
>No, you send 1 wei. Transactions always work with wei.

 So in order to send 1 ether I have to mutiply the value by 10^18?
>You can use the util method web3.utils.toWei(1, 'ether')

 What do I have to specify when calling ".send()"?
>You must specify "from" which is the sender address. Everything else is optional.

 The only function of web3.eth.sendTransaction() is to send ethers to a specific address, is that correct?
>No, you can also invoke contract methods.

 Do you know any solutions for scalability in Ethereum?
>2-layer protocols. Possible solutions are state channels and plasma.

## Solidity

 Is Solidity statically or dynamically typed?
>It is statically typed, which means that types are known at compilation.

 What is the equivalent to the Java "Class" in Solidity?
>It's the Contract.

 What is an instance of a contract?
>An instance of a contract is the deployed contract on the blockchain.

 Give me a couple of differences between Java and Solidity.
>Solidity supports multiple inheritance but doesn't support overloading

 What is the very first thing you must specify in a Solidity file?
>The version of Solidity compiler, which is specified as ^0.4.8. It is necessary because it prevents incompatibility errors which can be introduced when compiling with another version.

 What does a contract consist of?
>It consists mainly of storage variables, functions and events.

 What types of functions are there?
>There is a constructor, fallback function, constant functions and functions that modify the contract state.

 What error will I get if I put multiple contract definitions into a single Solidity file?
>It is perfectly fine to put multiple contract definitions into a single Solidity file.

 What are some ways in which two contracts can interact?
>A contract can invoke, create and inherit from another contract(s).

 What happens when you try to deploy a file with multiple contracts?
>The compiler only deploys the last contract in that file and all other contracts are ignored.

 What if I have a huge project, do I need to keep all my related contracts into a single file?
>You can use import statement to import a file, `import "./MyOtherContracts.sol"`

 Can I only import local files?
>You can also import files using HTTP (even from Github), `import "http://github.com/<owner>/<repo>/<path to the file>"`

What parts is the memory of an EVM divided into?
>It is divided into Storage, Memory and Calldata

Explain Storage
>Think of it as a database. Each contract manages its own Storage variables. It is a key-value datastore (256 bit key & value). The read and write are more costly in terms of gas used per execution.

Explain Memory
>It is a temporary storage. The data is lost once the execution terminates. You can allocate complext datatypes like arrays and structs.

Explain Calldata
>It can be tought of as the callstack. It is temporary, non-modifiable, and it stores EVM execution data.

What variables are stored in the Storage and Memory areas respectively?
>State variables and local variables (wich are references to the state variables) are stored in Storage. Function arguments are located in Memory area.

Take a look at the following code and explain which part of the code corresponds to wich memory area:
```
contract MyContract {
  // part 1
  uint count;
  uint[] totalPoints;
  
  function localVars(){
    // part 2
    uint[] localArr;

    // part 3
    uint[] memory memoryArr;

    // part 4
    uint[] pointer = totalPoints;
  }
}
```
> Part 1 - Storage. 
> Part 2 - Storage (array size points to the same location as counter).
> Part 3 - Memory.
> Part 4 - Reference to Storage.

Can I do this: 
  `function doSomething(uint[] storage args) internal returns(uint[] storage data) {...}`
>Yes, you can force the arguments of a function to be of type storage. In this case if you do not pass a storage reference, the compiler will complain.
