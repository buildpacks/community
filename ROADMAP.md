# 2023H1 Roadmap

This roadmap is the first of two roadmaps for 2023 leading up to KubeCon EU (2023-04-18). For more context on all the changes to roadmaps, see this [RFC](https://github.com/buildpacks/rfcs/blob/main/text/0118-2023H1-roadmap.md).

## Release Base Image Extension
* Owner: @natalieparellano 
* Links: [RFC](https://github.com/buildpacks/rfcs/blob/main/text/0105-dockerfiles.md), [tracking issue](https://github.com/buildpacks/rfcs/issues/224)

This started out as [Stack Buildpacks](https://github.com/buildpacks/rfcs/blob/main/text/0069-stack-buildpacks.md) and is now Dockerfile Extensions. Significant work has already been done on this feature over the last year. This roadmap item is about seeing this work through with releasing phase 3 in both `lifecycle` and `pack`.

## Remove Stacks & Mixins
* Owner: @jkutner
* Links: [RFC](https://github.com/buildpacks/rfcs/blob/main/text/0096-remove-stacks-mixins.md), [tracking issue](https://github.com/buildpacks/rfcs/issues/219)

This RFC was merged in 2021 and is a dependency on Base Image Extensions. In order to get us to 1.0, we'll need to take on some of these painful backwards breaking changes in the best way possible. This work will include the Buildpack & Platform spec changes with support in `lifecycle` and `pack`.

## Execution Environments RFC
* Owner: @hone
* Links: [RFC](https://github.com/buildpacks/rfcs/pull/274)

There has long been a desire for a "Test" support, but it's never been prioritized even though it's made the roadmap before. Not to be over ambitious, the first step is to get a RFC written and accepted.

## Project Health
* Owner: @samj1912
* Links: [Buildpacks Community Organization RFC](https://github.com/buildpacks/rfcs/pull/273)

Like other [CNCF projects](https://github.com/cncf/toc/issues?q=is%3Aissue+sort%3Aupdated-desc+%22health+of%22+-label%3A%22project+onboarding%22+-label%3A%22sandbox%22+), the project has been impacted by the VMware + Broadcom acquisition. The goal of this item is to improve the general health of the project and grow contributors back to our 2020 numbers. This includes every team having a set of active set of maintainers and contributors, thus removing the TOC needing to step in for platform.

As for concrete items to be accomplished:

* Establish a buildpacks-community to be used as a labs/staging area to help hype up experiments that we would be otherwise wary of investing in and, if they succeed, adopt them in the main buildpacks org.
* Participate in mentorship programs to grow contributors like [GSoC](https://summerofcode.withgoogle.com/) and [LFX Mentorship](https://lfx.linuxfoundation.org/tools/mentorship/).

## Pack Test Cleaning/Optimizations
* Owner: @dfreilich
* Links: [Pack Pull Request](https://github.com/buildpacks/pack/pull/1498)

Currently, the pack acceptance tests are very complex for newcomers. In order to help with contributions, we can relax some of these tests.

