# Debugging Node.js in Production

* (Heard this talk before, maybe via ConFreaks)
* Apply scientific method
* Production crises
  * Runtime performance
  * Runtime crashes
  * Memory leaks
* Runtime performance
  * restify
    * Observable framework
    * Latency and metrics for each request
    * Timings for each handler for each request
    * Especially help identify cpu-bound
  * How to make timings to code?
    * Statistically sample stack traces
    * How to do from running process?
    * How to do that without affecting process?
    * Using perf events
    * Missing JS frames out of the box, V8 places symbols just in time
    * --perf_basic_prof_only_functions - outputs in format that tools can consume
    * Sampling to address high volume of data
  * Flame graphs
    * Wider a frame is, more time spent on cpu
    * Top down shows ancestry
  * Technique
    * Sample with perf
    * Visualize with flame graphs
    * Identify problem code
    * Repeat
* Production crash
  * Post-mortem debugging
  * Take a core dump
  * --about_on_uncaught_exception
  * Linux tools not quite feature complete, llnode, etc.
  * mdb_v8 - Solaris only, virtualize to use it to read Linux core dumps
  * Methodology
    * Where - stack trace
    * Why - stack, heap state
  * Always name functions in node, no reason not to and makes debugging easier
* Memory leaks
  * Generate core dump whenever you like
  * With a tool called gcore
  * Use that to example stack, heap
  * findjsobjects command to find JS objects on heap
  * Looks for suspicious objects
  * Take successive dumps to find object counts that are growing
  * Walk reverse references to find root objects
