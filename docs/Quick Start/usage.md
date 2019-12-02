# Use the Oracle
Razor network is currently live on Görli Ethereum testnet. So you can deploy your applications on Görli and use Razor to fetch data for your applications.

## Create a new query
You can currently make two kinds of queries on Razor.

1. A simple one-time Query
2. A datafeed which gets updated every epoch

### Create a datafeed query using RazorScan
RazorScan provides an easy to use GUI to create datafeed queries on Razor Easily.

1. Make sure you are using a ethereum compatible browser (e.g. Chrome + Metamask) and set the network to Görli testnet.
2. You will need some Görli ether to pay for transaction fees.
3. Go to [https://razorscan.io/#/query](https://razorscan.io/#/query) and enter a URL which reponds with a JSON formatted data
2. Enter a JSON Selector
3. Enter the name of the datafeed
4. Click "Test query"
5. You can create the query by clicking "Create query" button.
6. Currently, it may take upto 20 minutes for the query to be answered.
7. You can go to [https://razorscan.io/#/custom](https://razorscan.io/#/custom) to see results of your query.

### Creating datafeed programmatically
You can create the datafeed programmatically as well by interacting with the Job Manager contract.
The source code for job manager can be found here: [JobManager.sol](https://github.com/razor-network/contracts/blob/master/contracts/Core/JobManager.sol)

The Address of the job manager contract can be found [here](https://github.com/razor-network/contracts/blob/master/ADDRESSES.md)

Note: Currently creating queries on Razor is free of cost.


## Get the results from the Oracle
You can access the proxy delegator contract to get the results of the datafeeds.

1. You will need to know the "Job ID" of your query. You can go to [https://razorscan.io/#/custom](https://razorscan.io/#/custom) and select your query to know the Job ID of your query.
2. You can call the "getResult" method of Delegator to get latest result of your query. The source of the contract is here : [Delegator.sol](https://github.com/razor-network/contracts/blob/master/contracts/Delegator.sol)
3. You can alternatively call "getJob" method of the same contract to get more information about the query such as name, url, selector, etc.
4. The address of the delegator contract can be found [here](https://github.com/razor-network/contracts/blob/master/ADDRESSES.md)
