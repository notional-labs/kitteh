# Kitteh: tendermint in Rust

## Why rust?

* C is too slow to write this much code rapidly
* C++ is dying, outside of the Boost libraries
* Go presents problems
  * CGO FFI
  * memory leaks
  * it is necessary to use Go in a non-idiomatic manner when building a blockchain, because we require determinism
    * goroutines aren't good for deterministic software
    * channels aren't
  * emxample
* Better low level library support
* Lower memory consumption for blockchain applications in production
* More rigorous compiler
* V, Nim, and Zig aren't mature enough yet


## 






## Theses

* IBC or similar proof based systems will be used for:
  * blockchain scaling
  * safety
  * communication between distinct networks
* Rust is the most suitable language for:
  * blockchains
  * static blockchain applications, like the cosmos-sdk
  * smart contracts
* Substrate/Grandpa/BEEFY lack the clear finality guarantees that tendermint brings
* In every known case, when building these systems in Go, we encounter:
  * Issues with the garbage collecgtor
  * Issues with CGO FFI
  * Memory Leaks
* Tendermint can be ported to rust for less than $1,000,000 in less than one year
  * The "surgical" practices of Informal Systems result in the dumb kind of conservatism
* Context switching between Rust and Go as currently seen throughtout Cosmos is extremely harmful to developer productivity.  
  * This also seems to affect the productiivty of humans leveraging LLMs and such
* AI systems will soon do most programming tasks, but they'll require skilled humans to verify the code.

## Tools

Kitteh should be primarily developed by humans using LLMs.  This approach will let us move more rapidly than our counterparts, and deliver software at a lower cost than our counterparts.

To ensure the growth of an ecosystem around kitteh, we should document our techniques.  Within 2 years we should anticipate the development of systems that are able to read, understand, and optimize kitteh's codebase. 

* OpenAI 128k token "turbo"
  * 
* xAI
* 01ai
* cursor editor


## What shouldn't change

* ABCI
* Consensus
* 

## What needs to be removed

* 26657 
  * the RPC & websocket

## What needs to change

* tight coupling of consensus and p2p -- consensus code should not be in p2p and vice versa
* the current p2p stack in favor of libp2p
