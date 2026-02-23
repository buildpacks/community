# Cloud Native Buildpacks: Security Due Diligence

## Metadata

A table for quick reference and indexing:

| Category | Information |
| --- | --- |
| **Software** | <br>**All available code:** [https://github.com/buildpacks](https://github.com/buildpacks) 

<br>

<br>**Core implementation Specification:** [https://github.com/buildpacks/spec](https://github.com/buildpacks/spec) 

<br>

<br>[https://github.com/buildpacks/lifecycle](https://github.com/buildpacks/lifecycle) 

 |
| **Security Provider** | No. A primary function of the Cloud Native Buildpacks tooling is to build container images that are secure, compliant, and up-to-date. However, security is one of many goals for the project.

 |
| **SBOM** | <br>**Until SPDX SBOM is available:** [https://github.com/buildpacks/pack/blob/main/go.mod](https://github.com/buildpacks/pack/blob/main/go.mod) 

<br>

<br>[https://github.com/buildpacks/lifecycle/blob/main/go.mod](https://github.com/buildpacks/lifecycle/blob/main/go.mod) 

<br>

<br>[https://github.com/buildpacks/libcnb/blob/main/go.mod](https://www.google.com/search?q=https://github.com/buildpacks/libcnb/blob/main/go.mod) 

<br>

<br>[https://github.com/buildpacks/imgutil/blob/main/go.mod](https://github.com/buildpacks/imgutil/blob/main/go.mod) 

<br>

<br>[https://github.com/buildpacks/registry-api/blob/main/Gemfile](https://github.com/buildpacks/registry-api/blob/main/Gemfile) 

 |

---

## Security Links

Existing security documentation for the project:

| Doc | URL |
| --- | --- |
| **Buildpack API Security Considerations** | <br>[https://github.com/buildpacks/spec/blob/main/buildpack.md#security-considerations](https://www.google.com/search?q=https://github.com/buildpacks/spec/blob/main/buildpack.md%23security-considerations) 

 |
| **Platform API Security Considerations** | <br>[https://github.com/buildpacks/spec/blob/master/platform.md#security-considerations](https://www.google.com/search?q=https://github.com/buildpacks/spec/blob/master/platform.md%23security-considerations) 

 |
| **Default and optional configs** | The default guidance for platform maintainers, including security trade-offs, is covered by the specification: [https://github.com/buildpacks/spec](https://github.com/buildpacks/spec) 

 |
| **Architectural Diagrams** | <br>[Link to Presentation](https://docs.google.com/presentation/d/1G6sIFtpHPjlx-JHzRXAjJcWnQx6a5mRgW6QO_3XqeQo/edit#slide=id.g6e655be570_3_2356) 

 |

---

## Overview

The Cloud Native Buildpacks project provides tooling to transform source code into container images using modular, reusable build functions called buildpacks. To accomplish this, the project takes advantage of advanced features in the OCI image standard that are underutilized by the Dockerfile model.

### Background

* The buildpack concept was conceived by Heroku in 2011.


* Cloud Native Buildpacks (CNB) was initiated by Pivotal and Heroku in January 2018 and joined the Cloud Native Sandbox in October 2018.


* The project aims to unify buildpack ecosystems with a well-defined platform-to-buildpack contract.


* It utilizes content-addressable image layers and cross-repo blob mounting for scalability and security outcomes difficult to achieve with Dockerfiles.



### Goals and Security Guarantees

The goal is to focus on developer productivity, container security, and day-2 operations at scale. Security guarantees include:

1. 
**Minimum security standards** for generated images:


* All processes must use a non-root UID/GID.


* Build-time and runtime base images are specified separately to exclude build-time dependencies (like compilers) from the final image.


* Build-time and runtime environment variables are specified separately to protect sensitive configuration.




2. 
**Bit-for-bit reproducibility** (when supported by buildpacks).


3. 
**Rebasable images** for ABI-compatible OS security patches without rebuilding application layers.


4. 
**Metadata inclusion** for auditing purposes.


5. 
**Secure build process** for untrusted code:


* Containers run without capabilities or privileges.


* Containers executing buildpack/app code run as non-root.


* Infrastructure credentials (VCS/registry) are absent from code-executing containers.


* Support for builds without egress network traffic.





### Non-goals

* The project does **not** provide language-specific buildpacks; these are provided by vendors like Paketo, Heroku, or Google.


* The project only provides the specification and tooling for platforms to implement image building.



---

## Intended Use

### Target Users and Use Cases

* 
**Platform Maintainers:** Use tooling to build images in cloud environments supporting OCI/Docker v2.


* 
**Buildpack Maintainers:** Use tooling to develop and deploy buildpack builder images.


* 
**Application Developers:** Use builder images to create application container images.



### Operation

The CNB lifecycle executes in a series of containers. Platforms are encouraged to run these without host privileges and to isolate registry/VCS access to containers that do not run application code. Containers executing untrusted code always run with a non-zero UID/GID.

---

## Project Design

The system design involves the **Platform**, **Lifecycle**, and **Buildpacks** interacting via the **Platform API** and **Buildpack API**.

### Ideal Application Build Process

1. 
**Detection:** Runs in a user-provided image with non-zero UID/GID; produces a TOML list of buildpacks.


2. 
**Analysis:** Runs in a platform image (UID 0) with registry credentials to restore metadata; no user code executes.


3. 
**Restore:** Runs in a platform image (UID 0) to restore layers; no user code executes.


4. 
**Build:** Runs in a user-provided image with non-zero UID/GID; produces layer directories and sets file timestamps to 1980 for reproducibility.


5. 
**Export:** Runs in a platform image (UID 0) with credentials to push to a registry; sets image creation date to 1980.



### Security Patching (Rebase)

* A new base runtime image with security patches is uploaded.


* 
**Rebase** modifies application image manifests to point to the new base image.


* Modified images are deployed using new digests; only the new base runtime layer is transferred.



---

## Configuration and Set-Up

* 
**Default:** Covered by the specification ([https://github.com/buildpacks/spec](https://github.com/buildpacks/spec)). Recommendations assume all code is untrusted, sacrificing performance for isolation.


* 
**Secure:** Detailed considerations are addressed in the Buildpack and Platform API security docs.



---

## Project Compliance

While not documented for specific standards (like PCI-DSS), CNB facilitates compliance by allowing enforcement of certified base images (e.g., DISA STIG) and providing dependency metadata (e.g., NVD identifiers).

---

## Security Analysis

### Attacker Motivations

1. 
**Supply-chain compromise:** Malicious buildpacks or compromised tooling.


2. 
**System intrusion (Infrastructure):** Exploiting isolation flaws to compromise build systems.


3. 
**System intrusion (Applications):** Exploiting deficiencies in built application images.



### Predisposing Conditions

* Failure to isolate untrusted code from registry credentials.


* Use of privileged containers or unnecessary capabilities.


* Lax egress networking policies.


* Vulnerable dependencies provided by buildpack maintainers.


* Modified lifecycles in third-party builders.



### Expected Attacker Capabilities

* 
**Properly configured:** Attackers might compromise an application via malicious artifacts but cannot attain registry credentials.


* 
**Improperly configured:** Attackers may compromise the registry, build infrastructure, and supply chains.



### Attack Risks and Effects

* 
**Supply-chain attacks:** Extremely high risk, potentially "company-ending".


* 
**Application vulnerabilities:** Risk quantified by CVSS scales.


* 
**Build system vulnerabilities:** Range from DoS to supply-chain attacks.



---

## Compensating Mechanisms

* 
**Credential Isolation:** Complete isolation of registry/VCS credentials from untrusted code.


* 
**Unprivileged Execution:** Runs in containers with zero capabilities.


* 
**Non-root UID/GID:** Prevents modification of OS-level files.



---

## Secure Development Practices

* 
**Automated testing:** Extensive use, enforced via GitHub Actions.


* 
**Reviews:** PRs require subteam maintainer approval; spec changes require core team supermajority.


* 
**Static Analysis:** Use of `gosec`, `codeql`, and `dependabot`.



---

## Communication and Ecosystem

* 
**Communication:** Slack, GitHub, and twice-weekly open working group meetings.


* 
**Ecosystem:** Adopted by kpack, Tanzu Build Service, Azure Container Registry, Google Cloud Run, Heroku, GitLab, and more.



---

## Security Issue Resolution

* 
**Disclosure:** Documented in [SECURITY.md](https://github.com/buildpacks/.github/blob/master/SECURITY.md).


* 
**Incident Response:** Core team decrypts and responds within 24 hours. Vulnerabilities are patched and announced via responsible disclosure.



---

## Roadmap and Next Steps

* 
**General Roadmaps:** Links for [2020](https://medium.com/buildpacks/cloud-native-buildpacks-2020-roadmap-b7e43876473a) and [2021](https://medium.com/buildpacks/cloud-native-buildpacks-2021-roadmap-e5ece588fc0) roadmaps.


* **Security Next Steps:**
* Recommend separate build-time and run-time user IDs.


* Git-based index for registry.


* Further work on image reproducibility.




* 
**CNCF Requests:** Third-party security review.



---

## Appendix

### Related Projects

* 
**Jib/Ko:** Construct OCI images directly for Java/Go without Dockerfiles.


* 
**Kaniko/Buildah/Podman:** Dockerfile-based workflows that don't require Docker.


* 
**Comparison:** Unlike Dockerfiles, CNB allows at-scale security patching for pre-built images and declarative definitions.
