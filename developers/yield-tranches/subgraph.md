---
description: Developers > Yield Tranches > Subgraph
---

# Subgraph

Idle uses a [subgraph](https://thegraph.com/docs/about/introduction#what-the-graph-is) for indexing and organizing data from the Yield Tranches `IdleCDO` smart contract. This subgraph can be found on The Graph hosted service and can be used to query Idle YTs data:

* **YTs subgraph** [https://thegraph.com/hosted-service/subgraph/samster91/idle-tranches](https://thegraph.com/hosted-service/subgraph/samster91/idle-tranches)
* **Graphql endpoint**
  * Ethereum [https://api.thegraph.com/subgraphs/name/samster91/idle-tranches](https://api.thegraph.com/subgraphs/name/samster91/idle-tranches)
  * Polygon zkEVM [https://api.studio.thegraph.com/query/12583/idle-tranches-zkevm/version/latest ](https://api.studio.thegraph.com/query/12583/idle-tranches-zkevm/version/latest)
  * Optimism [https://api.thegraph.com/subgraphs/name/samster91/idle-tranches-optimism](https://api.thegraph.com/subgraphs/name/samster91/idle-tranches-optimism)
* **Code** [https://github.com/Idle-Labs/idle-tranches-subgraph](https://github.com/Idle-Labs/idle-tranches-subgraph)

<figure><img src="../../.gitbook/assets/image (36).png" alt=""><figcaption></figcaption></figure>

### Useful entities

* _**TrancheInfos**_**:** contains the data of each YTs tranche (type, apr, `virtualPrice`, `totalSupply`) updated every hour
* _**Tranche**_**:** all deployed YTs tranches (id, type)

### Querying YTs

{% hint style="info" %}
Subgraph is case-sensitive. Remember to use all lowercase when inputting tranches' addresses.&#x20;
{% endhint %}

#### Example 1

To obtain the latest _TrancheInfos_ you can use the following query

```graphql
{ 
    trancheInfos(orderBy:"timeStamp", orderDirection:"desc") { 
        id
        apr
        Tranche { 
            id 
        }
        timeStamp
        blockNumber
        totalSupply
        virtualPrice
    }
}
```

#### Example 2

To obtain the latest _TrancheInfos_ for a specific tranche add a `where` filter. Let's query for example the Clearpool Portofino DAI Senior tranche `0xfc96989b3df087c96c806318436b16e44c697102`

```graphql
{ 
    trancheInfos(orderBy:"timeStamp", orderDirection:"desc", 
                 where:{ Tranche:"0xfc96989b3df087c96c806318436b16e44c697102" }) { 
        id
        apr
        Tranche { 
            id 
            CDO {
              id
            }
        }
        timeStamp
        blockNumber
        totalSupply
        virtualPrice
    }
}
```

For more info about GraphQL API, check [TheGraph Documentation](https://thegraph.com/docs/en/developer/graphql-api/).
