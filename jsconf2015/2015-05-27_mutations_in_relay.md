# Mutations and Subscriptions in Relay

Laney Kuenzel

http://2015.jsconf.us/speakers.html#kuenzel

* GraphQL
  * JSON object of only keys, not value in the tuples
  * Indicates shape of results
  * Queries can be composed
* Relay builds up parent and child component queries to fetch all data
  * Single store for GraphQL data rather than stores for specific uses, components
  * Consolidates rendering and data query local to component
  * Helps address prop/state bleed up the component tree
* Mutations are how React, Flux, Relay support user interactions
* Code smell - custom end point, data, etc., etc., etc. when adding new mutations
* Structured write API in GraphQL helps address this
  * But doesn't address the shape of the results
  * Each end point may be used by multiple, very different clients
  * Naive approach was a success flag or an id in response to a mutation
  * May trigger second round trip, or just rely on optimistic update that could be incorrect
* GraphGL supports mutations
  * Type of mutation
  * Any input, an id or two
  * Query for data after executing the mutation
