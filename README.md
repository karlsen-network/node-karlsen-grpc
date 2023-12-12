# Karlsen gRPC interface

Karlsen gRPC module is a basic request/response wrapper for interfacing with [Karlsend](https://github.com/karlsen-network/karlsend)

## Installing karlsen-grpc

```
npm install -g @karlsen/grpc
```

## Cloning karlsen-grpc

```
git clone https://github.com/karlsen-network/node-karlsen-grpc
cd node-karlsen-grpc
npm install
```

## Example

```js
const { Client } = require('@karlsen/grpc');

const client = new Client({
    host:"127.0.0.1:42210"
});
client.connect();
client.verbose = true;

try {
    let response = await client.call('getMempoolEntriesRequest', { });
    console.log(response);
} catch(ex) {
    ...
}

client.call('getVirtualSelectedParentBlueScoreRequest', { }).then((response)=>{
    console.log(response);
}).catch((err)=>{
    console.log('error:',err);
})
```
