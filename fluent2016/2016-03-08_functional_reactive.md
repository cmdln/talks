# Functional Reactive Programming

* Client
  * https://github.com/moredip/fluent-frp
  * Observable can wrap events and produce a stream
  * Example uses Marbelous to visualize streams
  * Can then accept a function expression to subscribe
  * Example from talk uses subscribe to set values from stream to text label
  * Calling map produces new stream, for instance value coercion
  * Convention in naming streams, ending variable name with $
* Server-side
  * https://github.com/moredip/related-artists
  * With promise, need to wait for entire result
  * With observable, can work with first value as it arrives
  * Does that require an API to support streams or observables?
  * Node streams provides take(n) method that just picks n first elements
  * Chaining stream requests from an original stream produces a stream of streams
  * Using flatMap merges stream of streams into one simpler stream
* Working with more than most recent value
  * For example, reduce or fold, which operate over a whole collection
  * Observable provides scan
  * Operates a reduce/fold as new values come in, with running total/accumulator
  * Generates a stream as output, to reflect changes as new values come in
  * Doesn't reduce to a single value once, continues to to reduce, over all, emitting new outputs for new values
  * Distinct until changed allows for filtering where output stream may be duplicative
* Key to streams is that typical fp operations produce streams themselves
  * To reflect that inputs are infinite and associated outputs likewise need to be infinite
