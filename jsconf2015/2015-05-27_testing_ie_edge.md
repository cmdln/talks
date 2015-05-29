* Speaker is an Ms evangelist
  * Left MS and came back
  * Uses a Macbook, tries to help bridge from MS to where devs are
* Links for supporting test
  * dev.modern.ie - edge dev portal, including roadmap, status dashboard
  * bit.ly/iedevguides
  * bit.ly/iecomaptcookbook
  * bit.ly/f12devtools
* Remote IE - under tools on dev.modern.ie
  * Azure hosted VM for IE
  * Need a live ID, MS remote desktop app (any RDP client like krdc?)
  * ngrok - secure tunnel so remote IE can access localhost, available under homebrew
* Screenshot service - multiple OS, browser combinations
* Site scanning report - feedback on compatibility issues
* Browser Stack
  * Paid service
  * Not browser or OS specific
  * Within the browser
  * Supports tunneling to localhost, as well, automatically
  * A browser extension, for Chrome
* WebDriver for IE11 is available
* insider.windows.com - ISO for Edge
* Vorlon.js
  * Supports remove communication
  * Open source
  * Similar to weinre
  * Node and socket.io
  * Has a plugin architecture
  * npm package
  * Runs a server on port 1337
  * Add a script tag to your page under test, instruments to work with Vorlon
  * Doesn't support script debugging--yet
* bit.ly/goweinre
  * WEb INspector REmote
  * Via a bookmarklet
  * More mature, featureful than Vorlon
* bit.ly/goghostlab - another paid service
* Headless version of IE - in development
