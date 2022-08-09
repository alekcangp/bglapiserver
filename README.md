
<img src="doc/logo.svg" width="350">


## BGLAPI Server for Testnet

### Introduction

BGLAPI Server is based on [BTCAPI Server](https://github.com/bitaps-com/btcapiserver)

BGLAPI Server is a server platform for working with Bitgesell blockchain and the network. 
This project is free and open source and can be used to build various services, 
both non-commercial and commercial, without any legal restrictions.

BGLAPI can be used as a backend for wallets, block explorers, payment processing and analytical platforms.

You can run BGLAPI as a self-hosted solution, or use a third-party public host.

### Requirements

* Python 3.3.3+
* https://github.com/bitaps-com/pybgl
* https://github.com/bitaps-com/aiojsonrpc
* BGL Core 0.1.2+
* Docker

### Installation

Setup your configs in bglapiserver/config (files with “.template” save as with same filename without “.template")

Create 3 containers  (files with “.template” save as with same filename without “.template"):

1) bglapi-server-postgres 

Use build.sh.template and run.sh.template files in bglapiserver/postgres folder 

2) bglapi-engine

Use build.sh.template and run.sh.template files in bglapiserver/app folder 

3) bglapi-server

Use build.sh.template and run.sh.template files in bglapiserver/api folder 

### API Modules

* **Transaction** store and provide information about all bitcoin transactions
* **Merkle proof** store and provide cryptographic proofs of the existence of a transactions in a blocks
* **Transaction history** store and provide historical transactions data for addresses 
* **Address state** store and provide state of addresses
* ~~**Address timeline** store and provide addresses state changes over time by transaction, day and month~~
* ~~**Blockchain analytica** store and provide blockchain analytic~~
* **Mempool analytica** store and provide unconfirmed transactions set analytic
* **Transaction fee analytica** store and provide transactions fee estimation data
* ~~**Nodes discovery** discover and provide list of available bitcoin nodes~~
* ~~**Market data** fetch and provide markets data~~
* ~~**Deterministic wallet** store and provide HD wallets state and historical data~~
* ~~**Payment forwarding** engine for payments forwarding service~~
* ~~**Hot wallet** engine for wallet service~~

### API documentation

Please see full [API documentation](https://github.com/bitaps-com/bglapiserver/tree/master/api)

### API examples

API implementation is available at the endpoint https://api.bglnode.online/rest

##### Block information

``` bash
$ curl --request GET \
>     --url https://api.bglnode.online/rest/block/last \
>     --header 'Content-Type: application/json'

{"data": {"height": 64548,
          "hash": "0009412faa0aaeaa14d1656d7cfb3d64efcbdea177802f644d28963d3d046314", 
          "header": "AAAAID+5ZkcxH89locKRol1kXso0V244MnWcIc2IE769RwUAXeEnhzp6M3+iPt1LPc2vkGl+17SaSSHz6ErMHluVGH6FYfFi//8PH4sdAAAE", 
          "adjustedTimestamp": 1659986309}, 
 "time": 0.0062}
```

Thanks [madnadyka](https://github.com/madnadyka) for support.
