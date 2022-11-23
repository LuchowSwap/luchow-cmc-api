# Documentation for Binance Smart Chain Network

All LuchowSwap pairs consist of two different tokens.

## [`/bsc/api/v1/summary`](https://api.luchowswap.com/bsc/api/v1/summary)

Returns data for the top ~1000 LuchowSwap pairs, sorted by reserves. 

### Request

`GET https://api.luchowswap.com/bsc/api/v1/summary`

### Response

```json5
{
  "updated_at": 1652979950370,              // UNIX timestamp
  "data": {
    "0x..._0x...": {                  // BEP20 token addresses, joined by an underscore
      "price": "...",                 // price denominated in token1/token0
      "base_volume": "...",           // last 24h volume denominated in token0
      "quote_volume": "...",          // last 24h volume denominated in token1
      "liquidity": "...",             // liquidity denominated in USD
      "liquidity_BNB": "..."          // liquidity denominated in BNB
    },
    // ...
  }
}
```

## [`/bsc/api/v1/tokens`](https://api.luchowswap.com/bsc/api/v1/tokens)

Returns the tokens in the top ~1000 pairs on LuchowSwap, sorted by reserves.

### Request

`GET https://api.luchowswap.com/bsc/api/v1/tokens`

### Response

```json5
{
  "updated_at": 1652979950370,              // UNIX timestamp
  "data": {
    "0x...": {                        // the address of the BEP20 token
      "name": "...",                  // not necessarily included for BEP20 tokens
      "symbol": "...",                // not necessarily included for BEP20 tokens
      "price": "...",                 // price denominated in USD
      "price_BNB": "...",             // price denominated in BNB
    },
    // ...
  }
}
```

## [`/bsc/api/v1/tokens/0x...`](https://api.luchowswap.com/bsc/api/v1/tokens/0xF71E950758310faF9f7D51C4F4250C7546086C1f)

Returns the token information, based on address.

### Request

`GET https://api.luchowswap.com/bsc/api/v1/tokens/0xF71E950758310faF9f7D51C4F4250C7546086C1f`

### Response

```json5
{
  "updated_at": 1652979950370,              // UNIX timestamp
  "data": {
    "name": "...",                    // not necessarily included for BEP20 tokens
    "symbol": "...",                  // not necessarily included for BEP20 tokens
    "price": "...",                   // price denominated in USD
    "price_BNB": "...",               // price denominated in BNB
  }
}
```

## [`/bsc/api/v1/pairs`](https://api.luchowswap.com/bsc/api/v1/pairs)

Returns data for the top ~1000 LuchowSwap pairs, sorted by reserves.

### Request

`GET https://api.luchowswap.com/bsc/api/v1/pairs`

### Response

```json5
{
  "updated_at": 1652979950370,              // UNIX timestamp
  "data": {
    "0x..._0x...": {                  // the asset ids of BNB and BEP20 tokens, joined by an underscore
      "pair_address": "0x...",        // pair address
      "base_name": "...",             // token0 name
      "base_symbol": "...",           // token0 symbol
      "base_address": "0x...",        // token0 address
      "quote_name": "...",            // token1 name
      "quote_symbol": "...",          // token1 symbol
      "quote_address": "0x...",       // token1 address
      "price": "...",                 // price denominated in token1/token0
      "base_volume": "...",           // volume denominated in token0
      "quote_volume": "...",          // volume denominated in token1
      "liquidity": "...",             // liquidity denominated in USD
      "liquidity_BNB": "..."          // liquidity denominated in BNB
    },
    // ...
  }
}
```

## [`/bsc/api/v1/pairs/0x...`](https://api.luchowswap.com/bsc/api/v1/pairs/0x1076FCc4dd5f2679F4DeFd2FBf8c7B6fB03C57f2)

Returns data for the pair address, sorted by reserves.

### Request

`GET https://api.luchowswap.com/bsc/api/v1/pairs/0x1076FCc4dd5f2679F4DeFd2FBf8c7B6fB03C57f2`

### Response

```json5
{
  "updated_at": 1652979950370,              // UNIX timestamp
  "data": {
      "pair_address": "0x...",        // pair address
      "base_name": "...",             // token0 name
      "base_symbol": "...",           // token0 symbol
      "base_address": "0x...",        // token0 address
      "quote_name": "...",            // token1 name
      "quote_symbol": "...",          // token1 symbol
      "quote_address": "0x...",       // token1 address
      "price": "...",                 // price denominated in token1/token0
      "base_volume": "...",           // volume denominated in token0
      "quote_volume": "...",          // volume denominated in token1
      "liquidity": "...",             // liquidity denominated in USD
      "liquidity_BNB": "..."          // liquidity denominated in BNB
  }
}
```