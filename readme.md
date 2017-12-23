# cardano-api

Promise wrapper for the [Cardano API](https://cardanodocs.com/technical/explorer/api/).  
### This is not quite finished :/

```js
const { cardano } = require('cardano-api')

const query = {
    address: 'Ae2tdP...fQwGpm' // the address to check
}

// promise
cardano.address(query)
  .then(data => console.log('address', data))
  .catch(err => console.log('err', err))

// async/await
const myCardanoFunc = async () => {
  try {
    const data = await cardano.address(query)
    console.log(data)  
  }
  catch(err) { console.log(err) }
}

myCardanoFunc()
```

# Supported Endpoints

#### cardano.address() - [/api/addresses/summary/{address}](https://cardanodocs.com/technical/explorer/api/#path--api-addresses-summary--address-)

```js
// Get summary information about an address
const query = {
    address: 'Ae2tdP...fQwGpm'  // Required, wallet address to check
}

cardano.address(query)
  .then(data => console.log('address', data))
```

#### cardano.block() - [/api/blocks/summary/{hash}](https://cardanodocs.com/technical/explorer/api/#path--api-blocks-summary--hash-)
```js
// Get block's summary information
const query = {
    hash: '52659d...195a70' // Required, block hash to check
}

cardano.block(query)
  .then(data => console.log('block', data))
```

#### cardano.pagesTotal() - [/api/blocks/pages/total](https://cardanodocs.com/technical/explorer/api/#path--api-blocks-pages-total)

```js
// Get the list of total pages
const query = {
    pageSize: 3 // Optional
}

cardano.pagesTotal(query)
  .then(data => console.log('blockTotal', data))
```

#### cardano.genesisAddress() - [/api/genesis/address/pages](https://cardanodocs.com/technical/explorer/api/#path--api-genesis-address-pages)

```js

const query = {
    page: 1,        // Optional
    pageSize: 3,    // Optional
    redeemed: true  // Optional
}

cardano.genesisAddress(query)
  .then(data => console.log('genesisAddress', data))
```

#### cardano.genesisPagesTotal() - [/api/genesis/address/pages/total](https://cardanodocs.com/technical/explorer/api/#path--api-genesis-address-pages-total)

```js
const query = {
    pageSize: 3,    // Optional
    redeemed: true  // Optional
}

cardano.genesisPagesTotal(query)
  .then(data => console.log('genesisPagesTotal', data))
```

#### cardano.genesisSummary() - [/api/genesis/address/pages/total](https://cardanodocs.com/technical/explorer/api/#path--api-genesis-summary)

```js
cardano.genesisSummary()
  .then(data => console.log('genesisSummary', data))
```

#### cardano.epoch() - [/api/search/epoch/{epoch}](https://cardanodocs.com/technical/explorer/api/#path--api-search-epoch--epoch-)

```js
// Search the blocks by epoch and slot
const query = {
    epoch: 3,   // Required, epoch to check
    slot: 24    // Optional
}

cardano.epoch(query)
  .then(data => console.log('epoch', data))
```

#### cardano.transaction() - [/api/txs/summary/{txid}](https://cardanodocs.com/technical/explorer/api/#path--api-txs-summary--txid-)

```js
// Get summary information about a transaction
const query = {
    txid: 'f3d468...3ac99b' // Required, transaction to check
}

cardano.transaction(query)
  .then(data => console.log('transaction', data))
```

#### cardano.transactionLast() - [/api/txs/last](https://cardanodocs.com/technical/explorer/api/#path--api-txs-last)

```js
// Get information about the 20 latest transactions
cardano.transactionLast()
  .then(data => console.log('transactionLast', data))
```

### test

``` npm test```

### issues

Something not working?  Please [open an issue](https://github.com/funador/cardano-api/issues)

### cardano tips
 ```DdzFFzCqrht8iQ2utWYssBnfGvSqkGfM7fxHXZWoB57ormT17td1CY4Eye7bADF6HpeGC57vwV5ZPzmVjiZRQEkAD9Rc4P8LDF7FfYne```
 
 ##### Cheers!