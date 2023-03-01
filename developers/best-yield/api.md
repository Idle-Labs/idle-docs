---
description: Developers > Best Yield > API
---

# API

### Authentication&#x20;

For authentication, you need to use the Bearer authentication scheme. To use it, add the following header to your request: **Authorization** -> Bearer `<token>`.

{% hint style="info" %}
To request full access to the Best Yield APIs please fill out [this form](https://idlefinance.typeform.com/to/CzRkDH).
{% endhint %}

### Endpoints

#### Historical data

`https://api.idle.finance/rates/[address]?[params]`

{% tabs %}
{% tab title="<address>" %}
Represents the underlying token address:\


* DAI: `0x6b175474e89094c44da98b954eedeac495271d0f`
* USDC: `0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48`
* USDT: `0xdac17f958d2ee523a2206206994597c13d831ec7`
* WETH: `0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2`
{% endtab %}

{% tab title="<params>" %}
The query string params are:\


* `start`: filter results from a specific timestamp
* `end`: filter results to a specific timestamp
* `isRisk` (true/false): if true returns only result for risk-adjusted strategy, if false returns only result for Best Yield strategy
* `frequency`: seconds between two records
* `order` (asc/desc): order results by timestamp
* `limit`: limit results
{% endtab %}
{% endtabs %}

{% swagger method="get" path="" baseUrl="api.idle.finance" summary="rates" %}
{% swagger-description %}
Return historical daily data for Best Yield strategies in a given calendar range. 
{% endswagger-description %}

{% swagger-parameter in="query" name="<params>" %}


[Params](api.md#less-than-params-greater-than)

 to filter data
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

{% swagger method="get" path="" baseUrl="api.idle.finance" summary="pools" %}
{% swagger-description %}
Return all the supported assets with APR and token details.
{% endswagger-description %}

{% swagger-parameter in="header" name="<token>" required="true" %}
Authentication using Bearer token
{% endswagger-parameter %}
{% endswagger %}

### Request examples

Return DAI historical daily data for the Best Yield strategy from 22 July 2020 to 24 July 2020 in descending order descending.

{% code overflow="wrap" lineNumbers="true" %}
```html
https://api.idle.finance/rates/0x6b175474e89094c44da98b954eedeac495271d0f?start=1595412616&end=1595581466&isRisk=false&frequency=86400&order=desc
```
{% endcode %}

Return the latest data for DAI Best Yield

{% code overflow="wrap" lineNumbers="true" %}
```
https://api.idle.finance/rates/0x6b175474e89094c44da98b954eedeac495271d0f?isRisk=false&order=desc&limit=1
```
{% endcode %}
