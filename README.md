Every PaaS
==========

Considering running your Node.JS app on a Platform-as-a-Service provider such
as Heroku, dotCloud, Nodejitsu - or testing it with Travis or doing testing &
continuous deployment with Strider?

EveryPaaS handles all the annoying platform-specific details so that you don't
have to. EveryPaas also makes local development a breeze according to 12-factor
app best practices.

EveryPaaS detects which environment your app is running in and abstracts away
the details of how to connect to external resources.

If you write your app with EveryPaaS, you will be able to seamlessly run it on
your dev box and any of a number of platform providers - without changing a
single line of code!

Supported Platforms
-------------------

* Heroku
* Nodejitsu
* Strider
* Travis CI
* dotCloud
* Your dev box

Supported Services
------------------

* MongoDB - `everypaas.getMongodbUrl()`
  - including MongoLab and MongoHQ in Heroku Marketplace

* MySQL - `everypaas.getMysqlUrl()`
  - including ClearDB and Xeround in Heroku Marketplace

* PostgreSQL - `everypaas.getPostgresqlUrl()`

* Redis - `everypaas.getRedisUrl()`
  - including Redis To Go and Open Redis in Heroku Marketplace

* Solr - `everypaas.getSolrUrl()`
  - including Web Solr in Heroku Marketplace


Installation
------------

EveryPaaS is available in NPM. Simply type `npm install everypaas` to install
it.

Usage
-----

EveryPaaS has a very simple API. When you require EveryPaaS, it will detect
which environment it is running in.

Example:

```
var everypaas = require('everypaas')

var mongodbUrl = everypaas.getMongodbUrl()
```

Complete API
------------

***Functions***

**MongoDB**

`everypaas.getMongodbUrl()` - Returns the URL for the MongoDB service. On Heroku, this will work with both MongoLab and MongoHQ add-ons.

**MySQL**

`everypaas.getMongodbUrl()` - Returns the URL for the MySQL service. On Heroku, this will work with both ClearDB and Xeround add-ons.

**PostgreSQL**

`everypaas.getPostgresqlUrl()` - Returns the URL for the PostgreSQL service.

**Redis**

`everypaas.getRedisUrl()` - Returns the URL for the Redis service. On Heroku, this will work with both Redis To Go and Open Redis add-ons.

**Solr**

`everypaas.getRedisUrl()` - Returns the URL for the Solr service. On Heroku, this will work with the Web Solr add-on.

***Properties***

`everypaas.paas` - The detected platform. Value is one of:

  - `everypaas.HEROKU` (Heroku)
  - `everypaas.DOTCLOUD` (dotCloud)
  - `everypaas.STRIDER` (Strider)
  - `everypaas.TRAVIS` (Travis)
  - `everypaas.NODEJITSU` (Nodejitsu)
  - `everypaas.NONE` (dev box / unknown)

`everypaas.herokuEnvironment` - Contains the full Heroku configuration environment.

`everypaas.dotCloudEnvironment` - Contains the full dotCloud configuration
environment. This can be useful to retrieve custom confuration variables or if
you have multiple instances of the same service.


