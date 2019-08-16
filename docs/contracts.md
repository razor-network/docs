#Contracts
These are the contracts for Razor network testnet.

##Deployment
1. Install `truffle`
2. Install `npm i`
3. Run `ganache-cli ganache-cli -i 420 -a 100`
4. Run tests `truffle test`
5. For `bigSchelling.js` large number of accounts are required `ganache-cli -s 0 -i 420 -a 101`
6. For testing with cli, set blocktime `ganache-cli -s 0 -i 420 -a 30 -b 5`
7. Deploy on ganache `truffle migrate --reset`
8. create `.secret` file with mnemonic of the private key used to deploy on rinkeby
9. Deploy on rinkeby (.secret file must be present with mnemonic of the private key used to deploy) `truffle migrate --network rinkeby --reset`
