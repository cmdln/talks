* Delineated difference between concurrency and parallelism
* Showed perfmon to demonstrate inability to fully saturate multicore
* Workers may be enough
  * Heavier than threads but workable
  * Coordination is the obstacle to core saturation
    * Essentially sending data back and forth between workers
    * To start, stop, accumulate work
* parallel.js
  * To bring map-reduce to js
  * High implementation costs
* postMessage
  * Performance is not there
  * No shared state, heavy weight to transfer state
  * Dependent on event loop
* Buffer transfers
  * Solvers problems but still cannot work on the same data at the same time
* What does native suggest, since it is a solved problem there?
* Leads us to design criteria as follows
  * Not dependent on main event loop
  * Implementation versatility
  * Support for threads, pthreads
  * Not sacrifice Extensible Web philosophy
    * Of course there is a manifesto
    * TL;DR--provide low level primitives, let app developers build up from there
* Example - incrementing worker
  * First with postMessage - 54K msg/sec
  * Then using some of the ideas emerging from the ideal design criteria dervied from native
    * shared memory array, synchronic int - 6.3M ms/sec
    * Improvement at the cost of more exposed complexity--locking
    * channel/receiver model - > 200K msg/sec
      * Looks more similar to postMessage version, easier to reason about
      * No locks exposed, not waitable object
      * Huge tradeoff but that's the point, choice of the programmer rather than constraints from the tool maker
  * Both of these pass muster on the design criteria, above
  * 3.5 out of 5
* Demos!
  * Mandelbrot
  * Unity WebGL benchmark
