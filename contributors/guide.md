# Contributor's Guide

The start of your involvement with the [Cloud Native Buildpacks](https://buildpacks.io/).

## Contributors

### Contributor Ladder

```text
+-----------+       +-------------+       +------------+       +-----------+       +-------+
|           |       |             |       |            |       |           |       |       |
| Community | +---> |   Project   | +---> | Maintainer | +---> | Team Lead | +---> |  TOC  |
|           |       | Contributor |       |            |       |           |       |       |
+-----------+       +-------------+       +------------+       +-----------+       +-------+
```

### Role Summary

The table below summarizes the progression path for the project. For detailed legal and voting definitions, please refer to the [Governance](/GOVERNANCE.md) document.

| Role                    | Eligibility                | Selection                                      | Lifecycle                     |
| :---------------------- | :------------------------- | :--------------------------------------------- | :---------------------------- |
| **Project Contributor** | Active community member    | Nominated by contributor, Team Maintainer vote | Emeritus after 3mo inactivity |
| **Component Maintainer**| Team Project Contributor   | Nominated by team lead/maintainer, Team vote   | Emeritus after 3mo inactivity |
| **Maintainer**          | Proven Project Contributor | Nominated by maintainer, Team Lead/TOC vote    | Emeritus after 3mo inactivity |
| **Team Lead**           | Established Maintainer     | Appointed by TOC                               | Reviewed annually by TOC      |
| **TOC Member**          | Project Leader             | Nominated by TOC, TOC supermajority vote       | Emeritus by request or vote   |

Contributors can be broken down into the following tiers.

1. [Community Contributor](#community-contributor)
2. [Project Contributor](#project-contributor)
3. [Maintainer](#maintainer)

#### Community Contributor

This is anyone that interacts with this project, whether it be by creating an issue, opening a PR, adding a comment, etc. You are all, in some way,
contributing to a better project.

#### Project Contributor

These contributors are recognized as providing sizable contributions to the project.

Additional Responsibilities:
* Maintain active participation in project.

Additional Capabilities:
* Added to GitHub organization team.
* Ability to edit, label, assign issues.
* Write access to branches on project repos.
* Access to infrastructure.

#### Maintainer

Maintainers are responsible for advancing the objectives and outcomes of the [team](/GOVERNANCE.md#Teams) they are inducted into. For detailed information, see the [Maintainer's Guide](maintainer_guide.md).

Additional Responsibilities:
* Maintain [team](/GOVERNANCE.md#Teams) associated contributions.
* Recruit [Project Contributors](#project-contributor)
* Review relevant [RFCs][rfcs]

Additional Capabilities:
* Publish releases.
* Ability to configure repositories.
* Invitation to leadership events.

## Contributions

Contribution to this project goes beyond the notion of code contributions. We value any help that you may be able to provide.

#### Component

Components developed outside of the Cloud Native Buildpacks project can be accepted following the process defined in [this RFC](https://github.com/buildpacks/rfcs/blob/main/text/0086-component-level-contrib.md#what-it-is).

- Component-level contributions must be proposed as project-wide RFCs
- Proposed contributions must primarily support the goals and use cases of the project and may not contain unrelated functionality that would not otherwise be accepted via the [RFC process](https://github.com/buildpacks/rfcs).
  - Qualifying examples:
    1. A Github Action that performs buildpack builds
    1. A Concourse resource that creates builder images
    1. A v2 buildpack that runs Cloud Native Buildpacks (v3) builds on platforms that only support older v2 buildpacks.
  - Non-qualifying examples:
    1. A generic CI/CD tool that includes functionality to run buildpack builds, but primarily supports use cases outside of the project (e.g., Tekton)
- If a proposed contribution provides functionality that is already provided by the project, such functionality must be provided for use in a non-overlapping context, or the proposal should include a plan for consolidation.
  - Qualifying examples:
    1. Buildpack language bindings for a language other than those already supported by the project (such as Go)
    1. An alternative implementation of the buildpack lifecycle launcher in Rust, with a documented plan to deprecate the original Go version
  - Non-qualifying examples:
    1. An alternative implementation of the lifecycle in Rust that would exist concurrently with the Go version in perpetuity
- If a proposed contribution is an adapter or integration with another service or technology, that technology must be notable and/or widely used (at the TOC’s discretion).
- If a component is proposed for donation by one or more TOC members individually, those TOC members must abstain from voting over its acceptance.
- If a component is proposed for donation by one or more TOC members’ employer or employers, those TOC members must abstain from voting over its acceptance. Supermajority consensus of non-abstaining TOC members is still required.
- Component-level contributions are subject legal review by the Cloud Native Computing Foundation / Linux Foundation. Adherance to these guidances does not guarantee acceptance. The investigation of this is to be done by the TOC before acceptance.

#### Code

Code contributions to any project repo are always welcomed.

The following repositories  are good starting points for code contributions:

* [libcnb][libcnb-gfi]
* [lifecycle][lifecycle-gfi]
* [pack][pack-gfi]

Other, more specialized, repositories include:
* [tekton-integration][tekton-integration]
* [pack-orb][pack-orb]

#### Docs

This involves documenting any aspect of the project. A good starting point for contributions to documentation would revolve around your comprehension or desired area of expertise.

A few examples of places where documentation would be valuable:

* Providing additional tutorials/guides to our docs site.
    * [buildpacks.io][buildpacks.io]
    * [Issues][docs-issues]
* Adding GoDocs to codebases:
    * [libcnb][libcnb]
    * [lifecycle][lifecycle]
    * [pack][pack]
* Additional information or examples in our [samples][samples] repo.
    * [Issues][samples-issues]
* Creating [blog][blog] posts.
    * Discuss blog proposals with the [#learning-team][learning-team-slack]

#### RFCs

RFCs, or Request For Comments, is the process we employ to review project-wide changes. By proposing changes via RFCs, it allows for the entire community to partake in the brainstorming process of applying changes, considering alternatives, impact, and limitations.

Contributions to the RFC process can take any or all of the following forms:

* Reviewing and commenting on [RFC Pull Requests][rfcs-prs].
* Partaking in discussions in [Working Group][working-group] meetings.
* Proposing changes via [RFCs][rfcs].

#### Triage

Triaging issues is the process of looking at newly created issues (or following up on issues). There are many benefits our community gain from our current triage process, to name a few:

1. The community receives reasonable response times.
2. Minimize the number of open "stale" issues.
3. Ongoing efforts aren't disrupted.

To learn more about how you can help triage issues, check out our dedicated [triage][triage] page.

## FAQs

- How do I become a project contributor?

    The process for becoming a [Project Contributor](#project-contributor) simply requires that you actively [contribute](#contributions) to the project. There is no set amount of contributions that are expected, but the more involved you are in the project the more votes that would be tipped in your favor.

    Once you've got a decent amount of contributions, you may self-nominate, or be nominated by another team member to become a Project Contributor. The maintainers of said relevant sub-teams will then vote for your election into becoming a Project Contributor.

<!-- links -->
[blog]: https://medium.com/buildpacks
[buildpacks.io]: https://buildpacks.io/
[docs-issues]: https://github.com/buildpacks/docs/issues
[learning-team-slack]: https://buildpacks.slack.com/archives/CST4A3ECV
[libcnb]: https://github.com/buildpacks/libcnb
[libcnb-gfi]: https://github.com/buildpacks/libcnb/issues?q=is%3Aissue+is%3Aopen+label%3A%22good+first+issue%22
[lifecycle]: https://github.com/buildpacks/lifecycle
[lifecycle-gfi]: https://github.com/buildpacks/lifecycle/issues?q=is%3Aissue+is%3Aopen+label%3A%22good+first+issue%22
[rfcs]: https://github.com/buildpacks/rfcs
[rfcs-prs]: https://github.com/buildpacks/rfcs/pulls
[pack]: https://github.com/buildpacks/pack
[pack-gfi]: https://github.com/buildpacks/pack/issues?q=is%3Aissue+is%3Aopen+label%3A%22good+first+issue%22
[pack-orb]: https://github.com/buildpacks/pack-orb/issues
[samples]: https://github.com/buildpacks/samples
[samples-issues]: https://github.com/buildpacks/samples/issues
[sub-teams]: https://github.com/buildpacks/community/blob/contributors-guide/GOVERNANCE.md#sub-teams
[tekton-integration]: https://github.com/buildpacks/tekton-integration
[triage]: triage.md
[working-group]: ../README.md#working-group
