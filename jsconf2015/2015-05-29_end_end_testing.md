# Zombies and Soup: Why End-to-End testing sucks (and why it doesn't have to)

Dave Cadwallader, @WalmartLabs

http://2015.jsconf.us/speakers.html#cadwallader

## Problem with tooling
* So much of it has too sparse instructions
* Example, how to draw a horse
* Covered testing pyramid
  * Challenges with UI tests/end-to-end
  * And benefits
  * Namely covering any gaps between, within unit tests
  * Also usually first or only place to test in all browsers
  * Best value for that last when automated, rather than manual
* Leads to staleness of test input
* Example, if last cross browser test is three months ago
  * Need to search three months of commits for regression
* Hence, Selenium
  * Open source, well supported
  * Tools like Sauce Labs, Browser Stack that work with it
* However, in practice
  * Big Rube Goldberg machine
  * So many points of failure it is hard to keep track of them all
* test flake - tests fail for no good reason, causing false positives
* One weird trick that wastes everyone's time
* TTL podcast - about front end ops, emerging discipline
* Google test blog article on no end-to-end testing

## Automation goals
* For dev and qa both
* Fast enough to run in CI
* No flake! Zero tolerance for false positive

## How it went
* Nightwatch, node package for talking to Selenium
  * Good success early on
  * But still admitted flake
  * Couldn't exceed 80-20 rule
* Soup - can of soup is like a test result
  * Unit test is like getting the can from your own cupboard
  * End-to-end tests require getting in your car, driving through zombie apocalypse, and so on
* Lurking zombies
  * Buggy webdrivers
  * Flakey networks

## How do we fix this problem?
* Soup metaphor is an axiom - pass/fail
* Breaking the axiom elimnates trust in the tool
* Making it true was more important than how made it true
* Led to horrible quality in test code
* Retries, waits, etc. based solely on trying to support the axiom
* Bulletproof but expensive and overkill
* Fixed the reliability problem

## The open source question
* Thought it was not suitable to release
* This was the antithesis of lightweight, clear, readable code
* How many other people felt the same pain but gave up?
* What if contribution could be harnessed from others whose time is saved?
* For example historical data and analysis
* Forked test swarm project for jQuery
* Run tests hourly rather than on-deman
* Massively parallel test runner
* That allowed for bringing test back into commit phase

### What about the flake?
* Started looking at data from test swarm
* Counts of retries, collated by agents, over time
* When smoothing over the speed bumps, don't ignore that
  * Capturing where the tooling has to work harder
  * Can lead to insights to improve tooling or know where truly external problems exist

# Code name: Magellan
* Still running through review
* End to end test runner that hooks into other tools
* A test runner, runner
* Smooths over flake but captures data on flake
* Massively parallel

## SSaSS
* As a service to fellow developers
* Momentum better than perfection
* Smooting over better than giving up
* Useful is better than precise
* Open source is better than closed source
