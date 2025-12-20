# 2025 Roadmap

2025 is a year about focus. We've started a few things from previous years and we're going to close the loop on them like our graduation application as well as some older RFC drafts and already approved ones. For more context, see this RFC: [RFC 0315](https://github.com/buildpacks/rfcs/blob/main/text/0315-2025H1-roadmap.md).

## Graduation
* Owner: @jkutner
* Target: H2/KubeCon NA

Our biggest focus for 2025 will be working on our path to CNCF graduation. We finished our [security audit last year](https://medium.com/buildpacks/announcing-findings-from-security-audit-b4701f4e8b4b). Now it's time to finish all the remaining pieces, submit an issue to the TOC, and get a formal review.

## Execution Environments
* Owner: @hone
* Target: H1/KubeCon EU
* RFC Issue: [#274](https://github.com/buildpacks/rfcs/pull/274)

This is an RFC that was opened two years ago. A recurring question over the years is "how do you do testing or CI with CNB?". While CNB provides a great path for production, users are left to their own means for building test environments. Shipping this feature will enable us to lay the groundwork for Buildpack Authors to support multiple execution environments.

## System Buildpacks
* Owner: @jabrown85
* Target: H1/KubeCon EU
* RFC: [#101](https://github.com/buildpacks/rfcs/blob/main/text/0101-system-buildpacks-in-builder.md)

This RFC was merged back in 2021, but was never implemented. With this feature, it provides Builders to have more control on what the buildpack experience looks like by dictating which buildpacks are always executed.

## OCI Artifacts
* Owner: @hone
* Target: H2/KubeCon NA
* RFC: [#113](https://github.com/buildpacks/rfcs/blob/main/text/0113-additonal-oci-artifacts.md)

With the [OCI Image and Distribution 1.1 spec](https://opencontainers.org/posts/blog/2024-03-13-image-and-distribution-1-1/) there is formal support for OCI Artifacts. Supporting this feature will allow Buildpacks to ship OCI Artifacts alongside images to support varying use cases like SBOMs, assets, and WASM modules/components.

While we had an existing RFC from before that supported uploading artifacts in addition of images, we may need to revisit what this feature looks like as we see more use cases. In the last few months we've seen interest from the WASM community in how buildpacks can be used with WASM modules.
