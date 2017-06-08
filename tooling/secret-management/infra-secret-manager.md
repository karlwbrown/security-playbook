# Task: Choose and set up an infrastructure secret management tool
**Description:**

A tool to manage infrastructure secrets such as access tokens, certificates,
database credentials, and other secrets should be used on any project that uses
infrastructure secrets. These secrets are sometimes found in source code or
configuration, or are never rotated, which increases the risk of them being
exposed to unauthorized parties.

There are various types of tools available to manage infrastructure secrets
ranging from tools that encrypt secrets for storage in source control to network
services that securely manage their entire lifecycle. These include:

* Source control-based: Encrypts secrets for storage in source control.
* Orchestration-based: Integrated with orchestration tools such as Ansible,
  Chef, Puppet, Docker Swarm, and Kubernetes.
* Secret services: Network endpoints that provide secrets over a secure channel.

Choosing what type of tool to use may require a number of considerations. One of
the most important considerations is the overhead required to set up and
maintain the tool and whether the needs of the project justify the overhead. In
general secret services provide the greatest flexibility and control, but they
may require more effort to maintain. A small team with few secrets may not need
as a sophisticated a tool.

Here are five key considerations when choosing an infrastructure secret manager:

* Do we need an audit log of secret lifecycle and access?  
* Does the tool need to integrate with external identity management systems such
  as Active Directory and LDAP?
* Does the tool support the creation of access control policies with the level
  of granularity needed?
* Is the tool easy to use for project needs? For example, does it support easy
  access to secrets from the CI pipeline, and do libraries to use it exist for
  the languages or frameworks used by the project?
* Are any infrastructure secret management tools already in use within the
  organization?

Some other possible considerations:

* Is it possible to rotate secrets easily?
* Does the organization have an existing PKI system the tool must integrate
  with?
* Does it support granting temporary access credentials for services that
  support it, for example AWS or certain SQL servers?

Some risks to watch out for:

* Storing data in cleartext
* Transmitting data across the network in cleartext
* Providing access to plaintext secrets to operators
* Lacking mutual authentication (the client should be able to verify the
  identity of the server and vice versa)
* A project that is no longer actively maintained
* Poor documentation

_Resources:_

* [Infrastructure Secret Management Software Overview, by @maxvt](https://gist.github.com/maxvt/bb49a6c7243163b8120625fc8ae3f3cd)
* [Secrets and LIE-abilities: The State of Modern Secret Management (2017), by Jeff Nickoloff](https://medium.com/on-docker/secrets-and-lie-abilities-the-state-of-modern-secret-management-2017-c82ec9136a3d)
* [Turtles All The Way Down: Storing Secrets in the Cloud and in the Data Center, by Daniel Somerfield](https://danielsomerfield.github.io/turtles/)

**Acceptance criteria:**

* Test deploying, configuring, and using an infrastructure secret management
  tool to verify it meets the needs of the project.
