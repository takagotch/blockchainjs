### blockchainjs
---
https://github.com/chromaway/blockchainjs

```js
var blockchainjs = require('blockchainjs')
var connector = new blockchainjs.connector.Chromanode({networkName: 'testnet'})
var address = 'xxx'

function showUTXO(address) {
  connector.addressQuery([address], {status: 'unspent'})
    .then(function (result) {
      console.log('UTXO for ' + address + ':')
      result.transactions.forEach(function (unspent) {
        console.log('Unspent in txid: ' + unspent.txid)
      })
      if (result.transactions.length === 0) {
        console.log('nothing...')
      }
      console.log('')
    })
}

connector.on(address, showUTXO)
connector.connect()
connector.subscribe({event: 'touchAddress', address: address})
showUTXO(address)


var blockchainjs = require('blockchainjs')

var connector = new blockchainhs.connector.Chromanode({networkName: 'testnet'})
connector.connector()

var storage = new blockchainjs.storage.Memory({
  networkName: 'testnet',
  compactMode: true
})

var blockchain = new blockchainjs.blockchain.Verified(connector, {
  storage: storage,
  networkName: 'testnet',
  testnet: true,
  compactMode: true,
  chunkHashes: blockchainjs.chunkHashes.testnet
})

blockchain.on('syncStop', blockchainjs.util.makeSerial(function () {
  return blockchain.getHeader(blockchain.latest.hash)
    console.log('Current header: ', header)
}))
```

```
```

```
```


