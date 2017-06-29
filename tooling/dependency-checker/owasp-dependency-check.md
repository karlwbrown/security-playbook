## Task: Add OWASP Dependency-Check into the CI pipeline
**Description:**

[OWASP Dependency-Check](https://www.owasp.org/index.php/OWASP_Dependency_Check)
is a tool that attempts to detect when updates are available for third party
dependencies (libraries, frameworks, etc) used in your application due to
publicly disclosed security vulnerabilities. This tool is applicable for
projects or major components that are written in Java or .NET.

**How to use it:**

The tool can be configured to email the development team or even break the build
when updates are found due to security vulnerabilities. The team can then
investigate the vulnerable component and apply an upgrade if it is found to be a
risk. Not all vulnerabilities in third party dependencies impact a project.

There are two scenarios to regularly run the tool:

* Per check-in for applications in active development. The team can choose
  whether to break the build when a new vulnerable component is identified.
* On a schedule for deployed versions of the application. This way the team will
  still be alerted in case the current development branch has already been
  updated but the deployed version has not, or when the application is no longer
  actively maintained.

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
