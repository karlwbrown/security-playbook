# Task: Choose a tool to verify secrets were not checked into source control
**Description:**

Even with a proactive tool to [help keep secrets out of source control](secrets-source-control.md),
accidents still happen. Proactive tools won't always identify sensitive
information, and people make mistakes. For that reason, it is a good idea to
periodically use a tool to search for sensitive information inside repositories.

Some tools for this purpose include:

* Gitrob: https://github.com/michenriksen/gitrob
* Truffle Hog: https://github.com/dxa4481/truffleHog
* BlueFlower: https://github.com/veorq/blueflower

It is helpful to have an incident response plan for if sensitive information is
found to have been checked in.
