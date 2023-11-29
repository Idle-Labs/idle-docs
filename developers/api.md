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

* Ethereum mainnet `https://api.idle.finance`&#x20;
* Polygon zkEVM `https://api-zkevm.idle.finance`
* OP mainnet: `https://api-optimism.idle.finance`&#x20;

### Endpoints

{% swagger method="get" path="" baseUrl="api.idle.finance" summary="pools" %}
{% swagger-description %}
Return all the network pools for both BY and YTs.
{% endswagger-description %}

{% swagger-parameter in="header" name="<token>" type="" required="true" %}
Authentication using Bearer token
{% endswagger-parameter %}
{% endswagger %}

{% swagger method="get" path="" baseUrl="api.idle.finance" summary="tvls" %}
{% swagger-description %}
Return the total value locked (TVL) per underlying token
{% endswagger-description %}

{% swagger-parameter in="header" name="<token>" required="true" %}
Authentication using Bearer token
{% endswagger-parameter %}
{% endswagger %}

{% swagger method="get" path="" baseUrl="api.idle.finance" summary="rates" %}
{% swagger-description %}
Return historical daily data for Senior Best Yield vaults in a given calendar range.&#x20;
{% endswagger-description %}

{% swagger-parameter in="query" name="<params>" %}
[Params](api.md#less-than-params-greater-than) to filter data
{% endswagger-parameter %}

{% swagger-parameter in="path" name="<address>" required="true" %}
Underlying token address
{% endswagger-parameter %}

{% swagger-parameter in="query" name="frequency" type="86400" %}
Seconds in one day
{% endswagger-parameter %}

{% swagger-parameter in="header" name="<token>" required="true" %}
Authentication using Bearer token
{% endswagger-parameter %}
{% endswagger %}

{% swagger method="get" path="" baseUrl="api.idle.finance" summary="junior-rates" %}
{% swagger-description %}
Return historical daily data for Junior Best Yield vaults in a given calendar range.&#x20;
{% endswagger-description %}

{% swagger-parameter in="query" name="<params>" %}
[Params](api.md#less-than-params-greater-than) to filter data
{% endswagger-parameter %}

{% swagger-parameter in="path" name="<address>" required="true" %}
Underlying token address
{% endswagger-parameter %}

{% swagger-parameter in="query" name="frequency" type="86400" %}
Seconds in one day
{% endswagger-parameter %}

{% swagger-parameter in="header" name="<token>" required="true" %}
Authentication using Bearer token
{% endswagger-parameter %}
{% endswagger %}

{% tabs %}
{% tab title="<params>" %}
The query string params are:

* `start`: filter results from a specific timestamp
* `end`: filter results to a specific timestamp
* `isRisk` (true/false): if true returns only result for risk-adjusted strategy (deprecated), if false returns only result for Best Yield vaults
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

* Return historical daily data for the Senior Best Yield DAI vault from 22 July 2020 to 24 July 2020 in descending order.

{% code overflow="wrap" %}
```html
https://api.idle.finance/rates/0x6b175474e89094c44da98b954eedeac495271d0f?start=1595412616&end=1595581466&isRisk=false&frequency=86400&order=desc
```
{% endcode %}

* Return the latest data for Senior Best Yield DAI vault.&#x20;

<pre data-overflow="wrap"><code><strong>https://api.idle.finance/rates/0x6b175474e89094c44da98b954eedeac495271d0f?isRisk=false&#x26;order=desc&#x26;limit=1
</strong></code></pre>

* Return the available Yield Tranches on Optimism&#x20;

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
