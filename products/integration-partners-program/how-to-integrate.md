---
description: Products > Integration Partners program > Overview > How to integrate
---

# How to integrate

### How does the process of integration work?

1. Apply using the [Integration Partners program form](https://idlefinance.typeform.com/to/PUC7nO)
2. Idle Leagues will review your application and contact you back
3. Once a League representative confirms that you are eligible to join the program, you can start working on the integration
4. Development updates are required every 2 weeks
5. Once in production, enjoy the fee-sharing!

{% hint style="info" %}
📖 Architecture, codebase, interface, and methods are detailed in the [Developers](broken-reference) chapter.
{% endhint %}

Idle provides a full suite of DeFi yield products easy to integrate into your products. No need to stitch together disparate protocols or spend months integrating and updating yield functionality.

As an integration partner, the methods you should look for are

* <mark style="color:red;">`mintIdleToken`</mark> method, where your <mark style="color:blue;">`_referral`</mark> Ethereum/Polygon address will be embedded

{% content-ref url="../../developers/best-yield/methods/mintidletoken.md" %}
[mintidletoken.md](../../developers/best-yield/methods/mintidletoken.md)
{% endcontent-ref %}

* <mark style="color:red;">`redeemIdleToken`</mark>&#x20;

{% content-ref url="../../developers/best-yield/methods/redeemidletoken-1.md" %}
[redeemidletoken-1.md](../../developers/best-yield/methods/redeemidletoken-1.md)
{% endcontent-ref %}

### Technical documentation

More technical and detailed information regarding Idle strategies integration can be found in the [Developers chapter](broken-reference) under the [Best Yield](../../developers/best-yield/) and the [Perpetual Yield Tranches](../../developers/perpetual-yield-tranches/) documentation.&#x20;

{% hint style="info" %}
Best Yield and Perpetual Yield Tranches are [ERC-4626](../../developers/networks-and-codebase/erc-4626-standard.md) compatible and should ease the effort needed when integrating the strategies.&#x20;
{% endhint %}
