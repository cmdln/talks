# Store-Query-Presenter

* Kris Walker @kixxauth
* Observing an existing change, especially as demonstrated by React/Flux/Redux
* About underlying data structures, React just a view layer
* History
  * "Most ideas come from previous ideas." -- Alan Kay
  * Reinventon sometimes leads to square wheels
  * Presenter chooses to see that as a side effect of progressive evolution
  * Opinionated tools have been with us for decades
  * Smalltalk created in part due to authors' dislike for Lisp
  * "Burn the diskpacks" - de-couple from backwards compatibility, force progress
  * What was introduced by smalltalk-80
    * Everything is an object
    * Objects only communicate only by passing messages
    * MVC
  * Command/Query Responsibility Segregation came about in response to MVC
    * Redux docs in motivations reference CQRS
  * Growth in sophistication puts pressure on MVC/CRUD as being too simple
  * What CQRS does
    * Splits models into commands and queries
    * Makes message passing a necessity
    * More of an evolutionary step from MVC
  * Martin Fowler has a good article on CQRS
  * Functional programming
    * Erlang/elixir as exampls of message passing in FP
    * Redux looks like messages passing to functions in Erlang
    * Erlang uses pattern matching/case analysis
    * Rather than fixed parameters, signature, match to specific messages passed to a given function
  * Event sourcing
    * Every change to the state of an application represented as an EventObject
    * Allows state to be rewound and replayed
    * Builtin audit trail
    * Can put application into any state by replay events
  * redux as culmination of these ideas, in one place
  * Is MVC getting laid off?
    * Author thinks so
    * Burn the diskpacks moment
  * "Three will be waste from ignorance, but natural selection will ..." -- Dan Ingalls
* Redux
  * Unidirectional data flow
  * Single state Object
  * Functional
* Reducers do work
  * Accept state and action
  * Perform pattern matching
  * Return a different state object, using Object.assign
* React/Flux/Redux breakthroughs
  * Single state object, usually if not de rigeur immutable
  * Passed into reducer functions you define
  * State is not mutated, it is replaced
  * Only way to modify state
* What's missing
  * State structure is not self documented
  * Difficult to understand what is happening with async actions
  * Querying the store is difficult
* Store - Query - Presenter
  * Builds on redux
  * Store::reducers
  * Query::getState() => state object
  * Helpers, command type models that know domain object but just implement actions on it not queries
* Querying
  * Redux library called reselect
  * Provides selectors, basically ways to alias key paths in Immutable.js
