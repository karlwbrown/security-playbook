## Task: Add OWASP Dependency-Check into the CI pipeline
**Description:**

OWASP Dependency-Check is a tool that attempts to detect when updates are
available for third party dependencies (libraries, frameworks, etc) used in
your application due to publicly disclosed security vulnerabilities. This
tool is applicable for projects or major components that are written in Java or
.NET.

The tool should be configured to email the development team when updates are
found due to security vulnerabilities. The team can then investigate the
vulnerable component and apply an upgrade if it is found to be a risk.

https://www.owasp.org/index.php/OWASP_Dependency_Check
