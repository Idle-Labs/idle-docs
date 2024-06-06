---
description: Developers > API
---

# API

### Authentication&#x20;

For authentication, users need to use the Bearer authentication scheme by adding the following header to their request: **Authorization** -> Bearer `<token>`.

{% hint style="info" %}
To request full access to the APIs please fill out [this form](https://idlefinance.typeform.com/to/CzRkDH).
{% endhint %}

### Network endpoints

Idle's smart contracts are deployed on multiple networks, hence users should use the appropriate endpoint to retrieve the information needed

* Ethereum `https://api.idle.finance`&#x20;
* Polygon zkEVM `https://api-zkevm.idle.finance`
* Optimism `https://api-optimism.idle.finance`&#x20;

### Endpoints

### pools

<mark style="color:blue;">`GET`</mark> `api.idle.finance`return all the network pools for both Best Yield and Yield Tranches vaults.&#x20;

#### Headers

<table><thead><tr><th width="223">Name</th><th width="189">Type</th><th>Description</th></tr></thead><tbody><tr><td>&#x3C;token><mark style="color:red;">*</mark></td><td></td><td>Authentication using Bearer token</td></tr></tbody></table>

## tvls

<mark style="color:blue;">`GET`</mark> `api.idle.finance`return the total value locked (TVL) per underlying token.

#### Headers

<table><thead><tr><th width="224">Name</th><th>Type</th><th>Description</th></tr></thead><tbody><tr><td>&#x3C;token><mark style="color:red;">*</mark></td><td>String</td><td>Authentication using Bearer token</td></tr></tbody></table>

## rates

<mark style="color:blue;">`GET`</mark> `api.idle.finance`return historical daily data for Best Yield vaults in a given calendar range.&#x20;

#### Path parameters

<table><thead><tr><th width="225">Name</th><th>Type</th><th>Description</th></tr></thead><tbody><tr><td>&#x3C;address><mark style="color:red;">*</mark></td><td>String</td><td>Underlying token address</td></tr></tbody></table>

#### Query parameters

<table><thead><tr><th width="227">Name</th><th>Type</th><th>Description</th></tr></thead><tbody><tr><td>&#x3C;params></td><td>String</td><td><a href="api.md#less-than-params-greater-than">Params</a> to filter data</td></tr><tr><td>frequency</td><td>86400</td><td>Seconds in one day</td></tr></tbody></table>

#### Headers

<table><thead><tr><th width="226">Name</th><th>Type</th><th>Description</th></tr></thead><tbody><tr><td>&#x3C;token><mark style="color:red;">*</mark></td><td>String</td><td>Authentication using Bearer token</td></tr></tbody></table>

{% tabs %}
{% tab title="<params>" %}
The query string params are:

* `start`: filter results from a specific timestamp
* `end`: filter results to a specific timestamp
* `isRisk` (true/false): if true returns only results for risk-adjusted strategy (deprecated), if false returns only results for Best Yield vaults
* `frequency`: seconds between two records
* `order` (asc/desc): order results by timestamp
* `limit`: limit results
{% endtab %}

{% tab title="<address>" %}
Represents the underlying token address:

* DAI: `0x6b175474e89094c44da98b954eedeac495271d0f`
* USDC: `0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48`
* USDT: `0xdac17f958d2ee523a2206206994597c13d831ec7`
* WETH: `0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2`
{% endtab %}
{% endtabs %}

### Request examples

* Return historical daily data for the Best Yield DAI vault from 22 July 2020 to 24 July 2020 in descending order.

{% code overflow="wrap" %}
```html
https://api.idle.finance/rates/0x6b175474e89094c44da98b954eedeac495271d0f?start=1595412616&end=1595581466&isRisk=false&frequency=86400&order=desc
```
{% endcode %}

* Return the latest data for Best Yield DAI vault.&#x20;

<pre data-overflow="wrap"><code><strong>https://api.idle.finance/rates/0x6b175474e89094c44da98b954eedeac495271d0f?isRisk=false&#x26;order=desc&#x26;limit=1
</strong></code></pre>

* Return the available Yield Tranches on Polygon zkEVM

{% code title="cURL" overflow="wrap" %}
```javascript
curl -H "Authorization: Bearer YOUR_TOKEN" "https://api-zkevm.idle.finance/pools"
```
{% endcode %}

{% code title="Axios" %}
```javascript
const data = await axios
  .get("https://api-zkevm.idle.finance/pools", {
    headers:{ Authorization: `Bearer YOUR_TOKEN` }
  })
  .catch(err => {
    // Handle request error
  });
```
{% endcode %}

{% code title="Request" %}
```javascript
const request = require('request');

const apiUrl = 'https://api-zkevm.idle.finance/pools';
const accessToken = 'YOUR_TOKEN';

const options = {
  url: apiUrl,
  method: 'GET',
  headers: {
    'Authorization': `Bearer ${accessToken}`
  },
};

request(options, (error, response, body) => {
  if (error) {
    console.error(error);
  } else {
    console.log(response.statusCode);
    console.log(body);
  }
});
```
{% endcode %}
