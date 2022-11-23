# Documentation for Ethereum Network

All LuchowSwap pairs consist of two different tokens.

## [`/eth/api/v1/summary`](https://api.luchowswap.com/eth/api/v1/summary)

Returns data for the top ~1000 LuchowSwap pairs, sorted by reserves. 

### Request

`GET https://api.luchowswap.com/eth/api/v1/summary`

### Response

```json5
{
  "updated_at": 1652979950370,              // UNIX timestamp
  "data": {
    "0x..._0x...": {                  // ERC20 token addresses, joined by an underscore
      "price": "...",                 // price denominated in token1/token0
      "base_volume": "...",           // last 24h volume denominated in token0
      "quote_volume": "...",          // last 24h volume denominated in token1
      "liquidity": "...",             // liquidity denominated in USD
      "liquidity_ETH": "..."          // liquidity denominated in ETH
    },
    // ...
  }
}
```

## [`/eth/api/v1/tokens`](https://api.luchowswap.com/eth/api/v1/tokens)

Returns the tokens in the top ~1000 pairs on LuchowSwap, sorted by reserves.

### Request

`GET https://api.luchowswap.com/eth/api/v1/tokens`

### Response

```json5
{
  "updated_at": 1652979950370,              // UNIX timestamp
  "data": {
    "0x...": {                        // the address of the ERC20 token
      "name": "...",                  // not necessarily included for ERC20 tokens
      "symbol": "...",                // not necessarily included for ERC20 tokens
      "price": "...",                 // price denominated in USD
      "price_ETH": "...",             // price denominated in ETH
    },
    // ...
  }
}
```

## [`/eth/api/v1/tokens/0x...`](https://api.luchowswap.com/eth/api/v1/tokens/0xA5Ef74068d04ba0809B7379dD76Af5Ce34Ab7C57)

Returns the token information, based on address.

### Request

`GET https://api.luchowswap.com/eth/api/v1/tokens/0xA5Ef74068d04ba0809B7379dD76Af5Ce34Ab7C57`

### Response

```json5
{
  "updated_at": 1652979950370,              // UNIX timestamp
  "data": {
    "name": "...",                    // not necessarily included for ERC20 tokens
    "symbol": "...",                  // not necessarily included for ERC20 tokens
    "price": "...",                   // price denominated in USD
    "price_ETH": "...",               // price denominated in ETH
  }
}
```

## [`/eth/api/v1/pairs`](https://api.luchowswap.com/eth/api/v1/pairs)

Returns data for the top ~1000 LuchowSwap pairs, sorted by reserves.

### Request

`GET https://api.luchowswap.com/eth/api/v1/pairs`

### Response

```json5
{
  "updated_at": 1652979950370,              // UNIX timestamp
  "data": {
    "0x..._0x...": {                  // the asset ids of ETH and ERC20 tokens, joined by an underscore
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
      "liquidity_ETH": "..."          // liquidity denominated in ETH
    },
    // ...
  }
}
```

## [`/eth/api/v1/pairs/0x...`](https://api.luchowswap.com/eth/api/v1/pairs/0x1e3aeEDFEF45B96173D533a3F2844aAFB5836B5B)

Returns data for the pair address, sorted by reserves.

### Request

`GET https://api.luchowswap.com/eth/api/v1/pairs/0x1e3aeEDFEF45B96173D533a3F2844aAFB5836B5B`

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
      "liquidity_ETH": "..."          // liquidity denominated in ETH
  }
}
```