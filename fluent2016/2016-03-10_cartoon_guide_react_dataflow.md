# Cartoon Guide to React Data Flow

* code-cartoons.com
* Data handling - capturing user input, persisting throughout UI
* Wilds because a lot of options, may be hard to choose one
* Flux
  * action -> dispatcher -> store -> view then back to action
  * Developed along with React to address inconsistency in Facebook's UI
  * Source of problem was way they were handling data
  * Started with more traditional MVC
    * With two way data between models and views
    * Also with dependencies and messages between models
  * Could all be happening asynchronously
  * Made it hard to predict behavior
  * Lin thinks about it as actors or characters
    * Action creator - telegraph operator, formats actions which are just objects
    * The dispatcher - switchboard operator, route actions to callbacks, stores
    * The store - overcontrolling bureaucrat, no accessors/mutators, only way in is actions
    * The view and controller view - (or presentational view and container view)
      * View or presentational view - received props, renders something visible
      * Controller or container view - has a little more smarts about how everything works, pass props down to other views
* Redux
  * Inspired by elm, other ideas from other tools
  * In particular ways of debugging - hot reloading, time travel debugging
    * Hot reloading allows changes to function defs without losing current state
    * Have to split state and functions into their own separate objects
    * Time travel allows getting to a particular state, step-by-step
    * To implement, state needs to be immutable and transition by replacing each step of state
    * Combine techniques for pretty powerful debugging
  * Differences from traditional flux
    * State gets passed around to reducers that produce next evolution of state
    * Reducers do not change state, create and return a copy
    * In between stores and views, view layer binding that binds data to views
* Relay
  * Bridges into fetching from the server
  * Provides convenience for fetching based on models, graph differences
  * Integrates with local cache
  * Supports optimistic updates
  * Relay is a framework, more so than just a pattern like Flux and Redux
  * Encapsulates mutations as objects, client code responsible for interpreting those into local state
