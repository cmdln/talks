# High Performance in the Critical Rendering Path

* @nzgb, ponyfoo.com
* Based on speaker's experience writing and supporting own blogging platform
* Start with measurement
  * Dev tool audits
  * PageSpeed Insights
  * WebPageTest.org - shows first load as well as after cache is primed
  * psi module in npm registry
  * api module for webpagetest
  * yslow module
* Defining a performance budget
  * Milestone timings
  * SpeedIndex
  * Quantity based metrics
  * Rule based metrics
  * grunt-perfbudget - enforces budget
* What can be done to improve
  * Consider the whole stack, tcp and up
  * "High Performance Browser Networking" book from O'Reilly
  * tcp - cwnd size, disable slow start
  * http - compression, keep-alive, cdn, expires and ETag headers
  * http/2 - non-blocking multi-plexing over one connection per origin, header compression, proactive server push
  * html - server side rendering
  * css - inline critical css, remove unused styles, responsive not separate m. site, concat and minify, style guides to keep it DRY
  * fonts - load async, fallback while fonts load, load only once and cache, prevent GOIT using JS, use fewer fonts, avoid repaints
  * images - minify and shrink, defer images below the fold, create spritesheets, try inlining tuny dynamic images, use css for simple icons
  * js - should be able to live without, defer some or all of it, use small modules, asset hashing, cache vendor scripts separately due to lower frequency of changes
* FOIT - flash of invisible text, bug related to font loading, rendering
* Tools
  * nginx for reverse caching proxy
  * shared/server rendering - rendr for some things, other frameworks support natively, like React
  * penthouse can inline css and determine what is actually in viewport
  * fontfaceonload supports async loading, fires an event when loaded
  * imagemin
  * base64 to data url images, careful is slow on mobile
  * perfschool - npm module, self guided workshop
