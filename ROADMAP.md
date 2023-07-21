# 2023H2 Roadmap

This roadmap is the second roadmap for 2023 leading up to KubeCon NA (2023-11-06). For more context on all the changes to roadmaps, see these two RFCs: [RFC 0118](https://github.com/buildpacks/rfcs/blob/main/text/0118-2023H1-roadmap.md) and [RFC 0121](https://github.com/buildpacks/rfcs/blob/main/text/0122-2023H2-roadmap.md).

## Items Continuing from [2023H1](./roadmaps/2023H1.md)

### Release Base Image Extension
* Owner: @natalieparellano 
* Links: [RFC](https://github.com/buildpacks/rfcs/blob/main/text/0105-dockerfiles.md), [tracking issue](https://github.com/buildpacks/rfcs/issues/224)

This started out as [Stack Buildpacks](https://github.com/buildpacks/rfcs/blob/main/text/0069-stack-buildpacks.md) and is now Dockerfile Extensions. Significant work has already been done on this feature over the last year. This roadmap item is about seeing this work through with releasing phase 3 in both `lifecycle` and `pack`.

### Remove Stacks & Mixins
* Owner: @jkutner
* Links: [RFC](https://github.com/buildpacks/rfcs/blob/main/text/0096-remove-stacks-mixins.md), [tracking issue](https://github.com/buildpacks/rfcs/issues/219)

This RFC was merged in 2021 and is a dependency on Base Image Extensions. In order to get us to 1.0, we'll need to take on some of these painful backwards breaking changes in the best way possible. This work will include the Buildpack & Platform spec changes with support in `lifecycle` and `pack`.

### Execution Environments RFC
* Owner: @hone
* Links: [RFC](https://github.com/buildpacks/rfcs/pull/274)

There has long been a desire for a "Test" support, but it's never been prioritized even though it's made the roadmap before. Not to be over ambitious, the first step is to get a RFC written and accepted.

## New Items

### Community Engagement Health Checks
* @microwavables (Team Lead sponsor @jkutner)
* Links: [VMware Tanzu Community Engagement Health Checks](https://github.com/vmware-tanzu/community-engagement/blob/main/HEALTHCHECKS.md)

The project is lucky to have a Community Manager! This is one of the projects proposed by @microwavables to set a base line to measure how we're doing as a community.

### RFC for Buildpack Author Observability
* Owner: @joshwlewis (Team Lead sponsor @hone)
* Links: TBD

Currently, Buildpack Authors have little to no tools around visibility with their buildpacks as they run on a platform, including `pack`. In some of the Heroku v2 buildpacks, they implemented logging that could be handed off to the platform by running `bin/report`. This work stream is about standardizing output for both successful AND failed builds that Buildpack Authors can use to instrument their buildpack.

### Private Registry Mirrors
* Owner: @jabrown85
* Links: [RFC](https://github.com/buildpacks/rfcs/pull/285)

A platform operator can configure registry mirrors that lifecycle could use without needing for the manifest to have to point to it. This will allow a platform to reduce the risk of service operations from external registry sources and reduce public network bandwidth usage. The resulting image when taken off platform will also function without needing access to the registry mirror.

### kpack Donation
* Owner: @jjbustamante (Team Lead sponsor @samj1912)
* Links: [RFC](https://github.com/buildpacks/rfcs/pull/235)

`kpack` is being proposed to be donated as an open source project in the Cloud Native Buildpacks' new Community Organization as a vendor neutral staging ground. This will give the project space to grow the project contributor base from multiple vendors. While work has started on this in H1, this item represents our commitment as a project to see this through and set this project up for success under the CNB governance umbrella.

### Cosign Integration / OCI Image Manifest v1.1
* Owner: @natalieparellano
* Links: [Cosign Integration RFC](https://github.com/buildpacks/rfcs/pull/195), [SBOM layer RFC](https://github.com/buildpacks/rfcs/pull/278),

While CNBs support SBOMs today, they were designed a few years ago and tooling around them have been evolving. This work stream is about making CNBs integrate better with tools like [cosign's SBOM spec](https://github.com/sigstore/cosign/blob/main/specs/SBOM_SPEC.md) and the upcoming [OCI References](https://github.com/opencontainers/image-spec/issues/827) feature in OCI Image Manifest 1.1.

### Pack OCI Manifest Support
* Owner: @jjbustamante (Team Lead sponsor @hone)
* Links: [RFC](https://github.com/buildpacks/rfcs/pull/283)

Multi-arch support has been a highly request feature with the growing popularity of the ARM architecture. In order to better support this with Buildpacks, the first step will be to able to use manifest lists to provide a single URI for Buildpacks that support multiple architectures.

### Export to OCI Layout
* Owner: @jjbustamante (Team Lead sponsor @natalieparellano)
* Links: [RFC](https://github.com/buildpacks/rfcs/blob/main/text/0119-export-to-oci.md)

The RFC has been merged and the implementation is expected to be released in experimental mode on pack *v0.30.0*.
