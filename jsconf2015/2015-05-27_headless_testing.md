* Using Xvfb - X Virtual Frame Buffer
* mdb on github
* The problem - what if your tech doesn't run headless?
  * Flash
  * NW.js
    * Distributed desktop apps across multiple OSes using web tech, Node.js
    * Assumes presence of a GUI/visible interface
  * Google Polymer web-component-tester - also assumes visible UI
* Basically, Xvfb allows GUI apps to render out without having to have an actual display
  * Could we use this for local Selenium testing on Jenkins/Bamboo box?
* github/mdb/polymer-testing-box
  * Configures a vagrant Ubuntu box with Ansible
  * Vagrant built on Virtual Box
  * Tool to spn up lightweight, headless VMs - complement to Docker?
  * Has a project for NW.js on github, too
