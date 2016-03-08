# Scaling node.js

* Developer set up instructions
  * https://github.com/v0lkan/talks/tree/master/fluentconf#development-setup
* Slide deck, volkan.io
  * Audience deck
  * Twice as many slides as the presentation version
* Strengths of node
  * IO heavy
  * Data intensive real time
  * Streams
  * Micro-services
* Weakenesses
  * Serving static files
  * CPI-bound applications -- sensitive to blocking
  * Creating a monolithic infrastructure
* Not a swiss army knife, complements other tools
  * Load balancing - haproxy, nginx, elb
  * SSL termination - stud
  * gzip compressoin - haproxy, nginx
  * serving static assets - nginx, cdn, varnish
* Tweaking at the OS level
  * Based on Ubuntu system
  * Number of open file handles - a socket connection consumes a file handle
    * /etc/security/limits.comf
    * pam session limits
    * ulimit
    * Make sure any load balancer's connection limit matches limits for node instances
  * sysctl -w net.core.somaxconn=1204 (defaults to 128)
    * Take care, setting too high can introduce latency
  * More sysctl options in particular can be tuned
  * Don't alter anything you don't understand
* Benchmark of 1st three examples
  * Plain TCP fastest due to less overhead
  * Trade off is you have to code more when eliminating frameworks, layers
* Data driven tuning
  * There is a pretty typical throughput vs. concurrency curve
  * Test and utilize settings that yield peak intersection between these too
* Load testing
  * More than just jMeter
  * Gatling
  * The Grinder
  * Locust
  * And as a service options
* Need to consider latency, as well
  * Useful to plot latency against throughput to refine understanding of best options
* Things to watch out for
  * Always keep an eye on event loop
  * Look for CPU-bound code and memory leaks
* vantage
  * Tool for managing, instrumenting
  * Can take a memory dump
  * Can cleanly shut down service
  * Expose remote port, need to take care to secure
  * Can remotely inspect, interrogate
* Author wrote kiraz to provide dtrace-like ability for node
* node supports Linux perf events, for instrumenting and visualizing
* Ultimately may need to re-design to address CPU-bound tasks
  * Common recommendation is to split api service from compute service
  * Can introduce own event loop, message bus to separate concerns
  * Message queue, versus other options, allow differential/distributed scaling
  * Trade off is complexity
  * For instance, what happens when a distributed service crashes?
  * At a minimum some sort of tool to continually run--pm2, forever, etc.
  * With service tool, use node's --abort_on_uncaught_exception to produce an mdb compatible dump
* Debugging
  * Myths
    * Debugging, profiling is not hard
    * Tools are increasingly mature
    * Can debug, profile production applications
  * Live, using repl
  * Post-mortem, with mdb
  * Remote with node inspector or IDE
