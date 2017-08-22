# Moeda fundraiser contracts

To run the tests you need a recent version of node (probably at least 7.7.x) as this project is using async/await, and some ES2015+ syntax.

To run the testsuite:
```
npm install
npm test
```

Furthermore if you want to run using `truffle test` you need to make sure that your testrpc instance is:

1. Running on port 8945
2. Has at least 4 accounts

#### Running tests in Parity/Geth

You need the above requirements and in addition the node needs to run in geth 
compatiblity mode, with the first 4 accounts returned by `account list` unlocked
and those accounts need to have a balance of at least 50 ETH.

Parity example
```
parity --chain dev --geth --unlock <list of accounts> --password <password file> --rpcport 8945
```

Where password file is a file with N passwords, one per line if you're unlocking N accounts.

### Known issues

* The test suite sometimes crashes due to a snapshot bug in ethereumjs-testrpc.

### Security Audit

A [security audit] of the contracts(https://github.com/BlockchainLabsNZ/moeda-contracts/blob/audit/audit.md) has been conducted by [Blockchain Labs](https://blockchainlabs.nz)