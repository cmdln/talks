# Chrome Developer Tools Deep Dive

* Use full array of tools to narrow DOM sub-graph in inspector
  * Can pin to some arbitrary node
  * Search/filter matches strings but also xpath and css selectors
  * Otherwise have to scroll around manually rather a lot
  * How to leverage these features not always obvious
  * Worth experimenting and just trying things to see what happens
  * "When you see a box, click it!"
  * For instance a color swatch, will open up a picker
* Special states, like hover
  * Cannot necessarily work with directly
  * Usually some alternate way to manually trigger and pin special states
* For source view, can also search instead of opening file tree and scrolling
* When debugging, can right-click and black box scripts to ignore them
* Can use console groups to make logging for specific things easier to find
  * Adds a disclosure trying in console
  * Can then open and collapse related log lines
* Can set content editable to true to test changes to page content
  * Complements ability to live change styles, scripts
  * Can help reveal layout problems that emerge from different amounts of text, content
* Network tab can throttle to emulate particular kinds of access networks
