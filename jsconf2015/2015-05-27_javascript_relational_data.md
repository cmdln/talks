* There are libs for interacting with RDBMSes
  * Node doesn't assume these exist, though, unlike older servers
  * No common API for RDBMS access
  * What exists is database specific
  * Or there is a mix of ORM/query layer, making it harder to drop down to SQL directly
  * Lack of transaction APIs
  * Often just same save API across all stores
  * Often have to assemble pieces needed
* Cobbled together two libraries to address these challenges
* Knex.js (as  in the K\*nex toy)
  * "Standardize some of the inconsistencies in SQL"
  * From context of ES/JS, fair enough that it seems strange, the incompatibilities
  * JS chaining to build expressions
  * Uses promises for result, exception handling
  * Supports joins, sub-queries - the latter with closures
  * Transactions challenging in async - connection has to be passed around for them to work at all
  * Knex takes care of this for you, making this more seamless
  * Newly added nested transactions
    * Calling trx on something already in a transaction transparently creats a save point
  * Batteries included - callbacks, streams, events, etc.
* Bookshelf.js - an ORM
  * Abstracts the building in queries
  * Includes association types
  * Has polymorphic associations
  * Builds on Knex, so can drop down to raw queries if needed
  * Eager loading - to address the N+1 query problem
    * Explicit, declarative
    * withRelated functionality
  * Tx'es are a little cruder in Bookshelf - cx has to be passed in options arg
* Can do isomorphic JS
  * But shared models are not as great in practice as you'd think
  * Very different concerns on server, in client in terms of data needs
* Not first, hopefully not the last to do this
  * OpenRecord - like ActiveRecord
  * Sequelize - no TX support, rough APIs but improving; new PostgreSQL feature support!!
  * azul.js - in response to Knex, Bookshelf
  * SQL Bricks
  * node-sql - driver support has improve considerably, recently
  * Knex Query Lab - in browser, interactive client
  * Bookends - nested data loading, querying
  * endpoints - JSON client lib
  * sails - has its own ORM, may use Knex for query building
