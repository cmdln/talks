# Visualizing process evolution

Dann Toliver

http://2015.jsconf.us/speakers.html#toliver

## Quote
* TK find Abelman, Sussman, Sussman quote on computer processes 
* Strong comparison to DNA
  * DNA is static
  * What it governs, how cell processes, is what is interesting
  * Processes couldn't happen without DNA
  * "There's a party going on in there, and we weren't inited. I wanted to go to that party.

## Data Structures
* Of increasing sophistication
* Especially in dealing with async
* Introducing concurrency concerns when sharing multiple state between processes
* Same problems as have arisen with other languages, tools
* Mutable state === spooky action at a distance
* Immutability helps us reason about our program
  * ImmutableJs
  * Mory (?)
* HAMT - hash array mapped trie
  * Values at the bottom
  * Pieces of keys to walk down to them
  * Hashing, consistent and unlimited, for efficiency and avoiding collisions
  * 5-bit hash, 32 element array at any depth
  * Better to have shallow, wide trees
  * Deep trees increases space, time complexity
* Used underscore to peer into data structures from these two libraries
* Visualized coordinates into stacked graph
  * Use color/pixel density to help reveals patterns over time
  * Triangular overall shape representing constant additions over time
  * Random banding, fixed elements over time
  * Some shading related to nurseries
* Labeled one blue, one red in visualizations
* Start taking elements out
  * Blue remains constant, as you'd expect
  * Nurseries shift to different axis
  * Red library did something completely different
  * Triangle continues
  * Matches strategy of hanging on to pointers
* Another demo around maps, keying
  * Blue grows much deeper, almost double
  * Brought up alternate view to help expose what we think is happening internally
  * Re-ran same with sequential inputs rather than random
  * Can see density/distribution of hashing algorithms 
  * Blue seems to have made a poor choice, with many collisions
  * Red shows compactness, very even distribution

## Can make observations without looking at code

## Granularity
* Spatial - line of code to entire codebase
* Temporal - single operation to real time behavior
* Really good support for this first two
* Memory
  * A single datum to entire heap
  * Another scale I didn't catch
* Good high level tools, especially for first two
  * Not so much for full coverage

## Design constraints
* 8-bit instructions
* 256 ? of memory
* Random programs
  * Fuzz the compiler
  * No run-time errors
  * No compile time errors
  * Want the program to terminate

## Live demo!
* (Notetaker's note: can't do this justice, look for link to code)
* Image as input
* Random program
* Run the program, see is some kind of image blurring
* Can zoom in, step-by-step
* Lose the real time, in that debugger mode
* Alternate representation
  * Homoiconicity (?)
  * Numeric codes for instructions, data
  * Isomorphisms between code, data, process
* Can see visually operation of program, read head, as well as step-by-step output
* Want random programs
  * Wire program for itself
  * Output is new program
  * Interested in deterministic transforms
* Showed this in JS
  * Tiny language
  * Tiny interpreter
  * With visualization of the state of the VM
  * Point isn't profiling, rather is to understand process unfolding from our code
  * Can play with time scale, explore temporal dimension interactively
  * From real time to tick at a time
* Then looked at actual library, with which he is unfamiliar
  * AgilityJS
  * Interacted with live app
  * Re-purposed some debugger tooling to visualize what was happening under the hood
  * For each file, revealed heat maps of functions and flow of functions, as they are called
  * Want to tease out, highlight data pathways, see inputs as they trickle through, where things pool
  * See where data interfaces with other data as they flow through

## Why?
  * Reading code is slow
  * Require us to have an interpreter in our head
  * Wants this programs he is writing, for ones he is reading
* Get this into dev tools for everything we are doing
* Let's get the computer to do the hard work
  * Of understanding what we are doing
