# I have to do WHAT to run this code?

Gord Tanner, bithound.io, Co-founder/CTO

http://2015.jsconf.us/speakers.html#tanner

## What is bitHound?
* Code analysis
* To help determine what is good code, objectively, subjectively
* Talk emerged from experience of helping new hires get started
* In particular, took half a day or less
  * To go from a brand new laptop
  * To comfort with code and even submitting a pull request
* bitHound writes closed source but ideas here apply to open source
* Open source incurs more of an up front costs
  * Becuase of distributed nature, lack of face-to-face knowledge transfer

## Nothing you don't already know
* Not necessarily about JavaScript specifically
* Invited audience to reflect on own experinces on day one of job or project
* Shared one of his own
  * Given a wiki, which was very stale
  * Only ever gets updated by someone with 2-4 hours experience with code base
  * Used to guide people with 0-2 hours experience
  * Put that way, despite best intentions, failure is likely
* First impressions matter
  * Sets tone, context for working relationship
  * Cannot do that over again
  * Likely to affect judgments of code, quality, whether fair, true or not
* Set up for success
  * People joined for positive reasons
  * Want to foster initial enthusiasm

## Documentation
* Important new social norm, README.md
* Previously, any documentation was likely hidden
* Newer project hosting makes it front and center
* Can be a good ToC or map
* e.g. link to contributing.txt
* White board sessions
  * The diagramming done with new contibutors to give an overview
  * Recommends doing this live, otherwise risks being stale
  * (I think there is also a good social value here, too, cementing conversation and rapport)
  * More challenging with open source
* Command line tooling 
  * For tool chain, take advantage of internal help, usage
  * Don't necessarily need to include in other docs
  * Should be close to where contributors use tools
* Code comments
  * *Why* not *what*
  * Code covers the what
  * Assuming good styles, conventions
  * Good example, a real world incident that lead to some unusual code or fix

## Configuration management
* (Notetaker's note: synthesized this part of the talk heavily, was presented more as a sequence of vignettes)
* VMs for environments
* Talked a lot about Vagrant
* Generally applies with things like Docker, Ansible
* Speaker recommends hiding use of tools like Vagrant
  * Which implies investing heavily in set up, config
  * Especially to flush out implicit assumptions that different hosts, environments might expose
* Capture as many rough edges, gotchas as you can in common config management tool
  * Override problem defaults, like services that only listen on loopback
  * File handles and other resource limits from the OS or tools
  * Time synchronization

## Tests
* Extension of a white board session
* Share tips, tricks on how to test
* Need to support more than just running existing tests
* Tooling to help debug test failures, progress
* How to simulate edge cases, submit reasonable test data
