# Jedi Secured Messaging Network

## Introduction

The Galactic Empire continues to intercept our communications. A new technology discovered in the archives of Terra on the outer rim has provided us with the solution.
We will use this blockchain technology to communicate with our different bases around the galaxy.

## Required Software

* Blockchain tools, Geth & Puppeth (all included in this message)
* Windows/Mac running Unix based software such as Terminal or GitBash

## Initial Commands

All Jedi Masters must create and initialize new nodes in their respective chains to activate communication with the network

### Node Creation

* Open your Unix interface
* Run the commands inside the quotes 
	* "./geth --datadir jedi1 account new"
	* "./geth --datadir jedi2 account new"
* Record the public addresses and passwords of each account in your saber memory
* Run the commands inside the quotes
	* "./puppeth"
	* "jediknights"
	* "2" - Configure new genesis
	* "1" - Create new genesis from scratch
	* "2" - Clique - proof-of-authority
	* Use the default time of 15 seconds for the blocktime
	* Input the public addresses of the two nodes created above one at a time
	* Input the public addresses again to be pre-funded (one at a time)
	* Do not prefun the precompile addresses, input "no"
	* Utilize 199 for the network ID (or any three digit number above 100)

### Export Network Settings

* Run the commands inside the quotes
	* "./puppeth"
	* "jediknights"
	* "2" - Manage existing genesis
	* "2" - Export genesis configuration
	* Press enter for the default folder

### Node Initilization

* Run the commands inside the quotes
	* "./geth --datadir jedi1 init jediknights.json"
	* "./geth --datadir jedi2 init jediknights.json"

### Commence Mining

* Open two Unix interfaces in separate windows
* In window 1, run:
	* "./geth --networkid 199 --port 30310 --datadir jedi1 --password pw.txt --unlock "0x71A51060BA0D596605c4909DEEe490Ff47021fb7" --mine --miner.threads 1 --ipcdisable --allow-insecure-unlock --syncmode full --rpc"
* In window 2, run:
	* "./geth --networkid 199 --datadir jedi2 --unlock "0xeE43bca5D8F20f14BD9258897c750413D01543d0" --port 30311 --mine --password pw.txt --bootnodes "enode://e537a17c40d5f6f9eb109cfa3daeae65c13e25c5292e405194a49d1af473856da7e87f994767cedb9258e729a4fdc124d4d5dc880831180ba8a6ff96d6553218@127.0.0.1:30310" --ipcdisable --allow-insecure-unlock"

#### Definitions

* ./ geth - initialized geth
* networkdid *number* - network id number for the blockchain
* port 30310 - local port for blockchain connection
* datadir - name of the node
* password - txt file with password from saber memory
* unlock - unlocks the chain
* mine - start mining new blocks
* miner.threads - number of CPU threads to utilize for mining
* ipcdisable - our Jedi network runs on Windows, this is needed so our firewalls permit transmission
* syncmode - method of syncing
* allow-insecure-unlock - opens chain for transmission 
* rpc - this allows our nodes to communicate
* bootnodes - this communicates the network settings to the node


## Network Setup

## Disclosure

