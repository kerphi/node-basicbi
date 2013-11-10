node-basicbi
============

node-basicbi is a simple business intelligence tool written in NodeJS.

What does this tool:
- Gathers periodicaly numeric data from your business through HTTP REST connectors JSON formatted.
- Stores these data into a local database TODO
- Provides a Web interface to visualize evolution of your data through time

Global parameter
================

```json
{ fetchAtStartup: true,
  xxx: false,
}
```

Data source parameters
======================

You can add as much as data sources you want. Each data source must have these parameters:

* `name` : TODO
* `url`: TODO
* `cron`: TODO (classic crontab format: `m h dom mon dow`)

Example:
```json
{ name: 'My business trends',
  url: 'http://my-business/stats/basicbi.json',
  cron: '0 5 * * 1' // at 5 a.m every week
}
```

Data source format
==================

Returned data by the HTTP REST endpoint must be JSON formated. And must be key/value formatted: key is a human readable string and value us a number.

Returned JSON example:
```json
{ "Number of clients": 175,
  "Highest sale": 1800 }
```

Installation
============

```
git clone https://github.com/kerphi/node-basicbi
cd node-basicbi
npm install
npm start
```

Then browse http://127.0.0.1:7979

Dependencies
============

- https://github.com/ncb000gt/node-cron
- https://github.com/mikeal/request
