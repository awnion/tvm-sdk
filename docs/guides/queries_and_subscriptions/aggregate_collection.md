# Aggregate Collection

{% hint style="warning" %}
<mark style="color:red;">**Collections is an analytics API (not real-time, though it may look like one).**</mark>

<mark style="color:red;">**Not all filters and sortings are working now. Data is provided only for the past 7 days.**</mark>
{% endhint %}

## When you may need aggregate of collections?

If you want to apply some aggregators like COUNT, MAX, MIN, SUM, AVERAGE on some blockchain data.

## Usage

```javascript
const aggregationFunctionsResults = result = 
        (await client.net.aggregate_collection({
        collection: 'accounts',
        fields: [
            {
                field: "balance",
                fn: "MIN"
            },
            {
                field: "balance",
                fn: "MAX"
            }, {
                field: "balance",
                fn: "AVERAGE"
            }, {
                field: "balance",
                fn: "SUM"
            },
            {
                field: "balance",
                fn: "COUNT"
            }
        ]
    })).values;
console.log("Minimum account balance: " + aggregationFunctionsResults[0]);
console.log("Maximum account balance: " + aggregationFunctionsResults[1]);
console.log("Average balance: " + aggregationFunctionsResults[2]);
console.log("Total balance of all accounts: " + aggregationFunctionsResults[3]);
console.log("Number of accounts: " + aggregationFunctionsResults[4] + '\n');
```

## About collections

There are a few collections with blockchain data:

* _accounts_: blockchain account data;
* _transactions_: transactions related to accounts;
* _messages_: input and output messages related to transactions;
* _blocks_: blockchain blocks.
* _block\_signatures_ : validator block signatures

[Reference](broken-reference)

Sample: [https://github.com/tonlabs/sdk-samples/tree/master/core-examples/node-js/query](https://github.com/tonlabs/sdk-samples/tree/master/core-examples/node-js/query)
