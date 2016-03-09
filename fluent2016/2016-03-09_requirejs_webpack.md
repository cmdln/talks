# Moving from requirejs to webpack

* requirejs introduces a brittle, hard to read way of adding dependencies
* Wanted to use commonjs on the client
* browserify almost perfect, broke on edge cases, where a lot of complexity emerges
  * Didn't make sense to re-write app just for module system
* webpack just worked
  * Moved build system over in a matter of hours
  * Supported AMD syntax out of the box, no change
  * Shims and aliases ported without any headache
  * Build time was significantly shorter
