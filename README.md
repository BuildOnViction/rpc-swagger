# VICTION JSON RPC API

JSON is a lightweight data-interchange format. It can represent numbers, strings, ordered sequences of values, and collections of name/value pairs.

JSON-RPC is a stateless, light-weight remote procedure call (RPC) protocol. Primarily this specification defines several data structures and the rules around their processing. It is transport agnostic in that the concepts can be used within the same process, over sockets, over HTTP, or in many various message passing environments. It uses JSON (RFC 4627) as data format.

## The default block parameter


The following methods have an extra default block parameter:

- `eth_getBalance`
- `eth_getCode`
- `eth_getTransactionCount`
- `eth_getStorageAt`
- `eth_call`


When requests are made that act on the state of ethereum, the last default block parameter determines the height of the block.

The following options are possible for the defaultBlock parameter:

- `HEX String` - an integer block number
- `String "earliest"` for the earliest/genesis block
- `String "latest"` - for the latest mined block
- `String "pending"` - for the pending state/transactions

## Curl Examples Explained

The curl options might return a response where the node complains about the content type, this is because the `--data` option sets the content type to `application/x-www-form-urlencoded` . If your node does complain, manually set the header by placing `-H "Content-Type: application/json"` at the start of the call.

## Convert swagger-ui to documents api 

`npm install [-g] widdershins`

Run command:

```

node widdershins --search true --language_tabs 'shell:cURL' 'javascript--nodejs:Node.JS' 'go:GO' 'ruby:Ruby' 'python:Python' --summary swagger.yml -o slate.md

```