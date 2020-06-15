# Contributor's Guide

The start of your involvement with the [Cloud Native Buildpacks](https://buildpacks.io/).

## Contributors

```text
+-------------------------+       +-----------------------+       +--------------+
|                         |       |                       |       |              |
|  Community Contributor  | +---> |  Project Contributor  | +---> |  Maintainer  |
|                         |       |                       |       |              |
+-------------------------+       +-----------------------+       +--------------+
```

Contributors can be broken down into the following tiers.

1. [Community Contributor](#community-contributor)
2. [Project Contributor](#project-contributor)
3. [Maintainer](#maintainer)

#### Community Contributor

This is anyone that interacts with this project, creates an issue, opens a PR, adds a comment, etc. You are all in one way
contributing to a better project.

#### Project Contributor

This group of contributors are recognized as providing sizeable contributions to the project.

Additional Responsibilities:
* Maintain active participation in project.

Additional Capabilities:
* Added to GitHub organization team.
* Ability to edit, label, assign issues.
* Write access to branches on project repos.
* Access to infrastructure.

#### Maintainer

Maintainers are responsible for objectives and outcomes of the [sub-team][sub-team] they are inducted into.

Additional Responsibilities:
* Maintain [sub-team][sub-teams] associated contributions.
* Recruit [Project Contributors](#project-contributor)
* Review relevant [RFCs][rfcs]

Additional Capabilities:
* Publish releases.
* Ability to configure repositories.
* Invitation to leadership events.

## Contributions

Contribution to this project goes beyond the notion of code contributions. We value any help that you may be able to provide.

#### Code

Code contributions to any project repo are always welcomed.

The following repositories  are good starting points for code contributions:

* [libcnb][libcnb-gfi]
* [lifecycle][lifecycle-gfi]
* [pack][pack-gfi]

Other repositories that are specialized:
* [tekton][tekton]
* [pack-orb][pack-orb]

#### Docs

This involves documenting any aspect of the project. A good starting point to contribute to documentation would revolve around your comprehension or desired area of expertise.

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
    
    The process for becoming a [project contributor](#project-contributor) simply requires that you actively [contribute](#contributions) to the project. There is no set amount of contributions that are expected, but the more involved you are in the project the more votes that would be tipped in your favor. 
    
    Once you've got a decent amount of contributions, you may self-nominate, or be nominated by another team member. The maintainers of said relevant sub-teams will then vote for your election into becoming a project maintainer.

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
[tekton]: https://github.com/tektoncd/catalog/tree/v1beta1/buildpacks
[triage]: triage.md
[working-group]: ../#working-groups
