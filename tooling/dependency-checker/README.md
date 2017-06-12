# Dependency Checkers for the Automated Pipeline

## What is it?
* A dependency checker is a tool that attempts to detect when updates are
  available for third party dependencies (libraries, frameworks, etc) used in
  your application due to publicly disclosed security vulnerabilities.

## Why is it needed?
* Up to 90% of many applications are comprised of third party components.
* Applications often inadvertently introduce vulnerabilities by failing to
  update components in a timely manner or by pulling in outdated components with
  vulnerabilities.

## When should I use this?
* If you leverage technologies that use third party components and that have a
  dependency checker available.

## How should I use the tools?
The team should evaluate these tools and choose one that is right for their
needs.

The tool should be configured to email the development team when updates are
found due to security vulnerabilities. The team can then investigate the
vulnerable component and apply an upgrade if it is found to be a risk.

There are two scenarios to regularly run the tool:

* Per check-in for applications in active development. The team can choose
  whether to break the build when a new vulnerable component is identified.
* On a schedule for deployed versions of the application. This way the team will
  still be alerted in case the current development branch has already been
  updated but the deployed version has not, or when the application is no longer
  being actively maintained.

**Acceptance criteria:**

* When a check-in is made to the revision control system, then the tool should
  be run against the dependency manifest for the branch the check-in was made
  into.
* When a regular interval of time elapses, then the tool should be run against
  the dependency manifest for any deployed versions of the application.
* When a vulnerable component is identified, then it should send an email to
  inform the team.
* When an error occurs running the dependency checking tool, then it should send
  an email to inform the team.

It is recommended that the scheduled job be run at least daily.

## Tasks
Below are tasks organized by technical stack to introduce dependency checkers
into your automated CI Pipeline.

* Java, .NET: [OWASP Dependency-Check](owasp-dependency-check.md)
* JavaScript (npm, Node.js): [npm dependency checkers](npm-dependency-checkers.md)
* Ruby: [ruby dependency checkers](ruby-dependency-checkers.md)
