# Static Analysis Tools
## What is it?
* These tools analyze your source code to look for language/framework specific security bugs. 
* They alert you to "failures" and often direct you to resources to learn about relevant vulnerabilities, and how to fix them.
* Typically, they are pretty configurable

## Why is it needed?
* Sometimes the easiest or most obvious way to do something is also not secure. These tools will remember these rules for you. 
* Continuous, fast checking for potentially critical vulnerabilities saves developers time and stress. 

## When should I use this?
* In your pipeline: you can configure a "lightweight" scan to run in your pipeline, along with your other automated tests. If a security test fails, so will your build.
* During manual testing: more in-depth scans can be run and verified along with the other necessary manual tests. Testers can also start to do some exploratory security testing after familiarizing themselves with typical weaknesses. 

## Tasks
Below are tasks organized by technical stack to introduce static analysis tools.

* Python: [Bandit](bandit.md)
* JavaScript: [eslint](eslint.md)
* Ruby (Rails & Other Frameworks): [Brakeman](brakeman.md) [Dawnscanner](dawnscanner.md)

## Additional Information

* TODO: Add sample config file for bandit; more details on CI pipeline integration
