* Someone put a synthesizer in your web browser
  * Based on web Audio API
* Uses a context, like Canvas
* Destination
  * Output, like an amp if you play guitar
  * A settable property on the context object
* Can also add effects in
* Source
  * Media file
  * Microphone
  * Or can generate own tones
* Last is the oscillator
  * See modem in JS talk
  * API object for working with tone generation - frequency and amplitude
  * Factory method on context to create this object
* Gotcha
  * Cannot stop oscillator, need to destroy/GC
  * Make sure to disconnect first
  * Destroying/creating is relatively efficient
* Speaker recommends re-using
  * Can just create gain node
  * Gain to zero effectively stops oscillator
* Live demo
  * Able to set frequency
  * Able to set wave shape - sine, box, sawtooth, triangle
* Talked through some basic info need to go from basic tones to musical notes, scales
  * A4 - 440Hz
  * A5 - 880Hz
  * And so on but only in one key
  * Math for deriving multiple keys is apparently hard
  * But there are existing heuristics, hacks
  * Reasonably good in every key though not perfect in any key
* github/stevekinney/octavian
  * Lets you request a note, get frequencies
  * Also intervals - root, thirds, fourths, fifths, etc.
* audiophonic - instrument built on this work
* Someone put a web browser in your synthesizer
  * Can combine other APIs with Web Audio
  * Demo - face theremin
    * Combining media capture API
    * Tracking face as input to tone
  * Demo - web sockets
    * Step sequencer
    * Socket to node server, accepts sequences
    * Sends those back out to other connected clients
    * Each client combines all the shared sequences and play
  * Demo - hardware hack, make input more flexible using arduino
  * So much more still possible!
