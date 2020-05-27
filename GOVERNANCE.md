# Cloud Native Buildpacks Governance
This document defines the governance structure for Cloud Native Buildpacks. This project is committed to building an open, inclusive, productive and self-governing open source community that maintains a specification and high-quality tools for translating source code into OCI images. The guidelines herein describe how the Cloud Native Buildpacks community should work together to achieve this goal.

## Repositories
The following code repositories are governed by the Cloud Native Buildpacks community and maintained under the [buildpacks](https://github.com/buildpacks) organization.

* [spec](https://github.com/buildpacks/spec)
* [lifecycle](https://github.com/buildpacks/lifecycle)
* [pack](https://github.com/buildpacks/pack)
* [imgutil](https://github.com/buildpacks/imgutil)
* [docs](https://github.com/buildpacks/docs)
* [rfcs](https://github.com/buildpacks/rfcs)
* [resources](https://github.com/buildpacks/resources)
* [community](https://github.com/buildpacks/community)
* [samples](https://github.com/buildpacks/samples)

## [Core Team](TEAMS.md#Core-Team)
The Core team is responsible for the direction of the project (roadmap), subteam leadership, the spec, and cross-cutting concerns. This includes:

* [spec](https://github.com/buildpacks/spec)
* [rfcs](https://github.com/buildpacks/rfcs)

Core team members are responsible for voting on RFCs, specification updates, and other changes to the project such as changes in leadership or community roles. A simple majority is required in each case. No company will have a combined voting block of larger than 50%.

## Sub-teams
Sub-teams are responsible for narrower sets of concerns related to specific aspects of the project. Each sub-team will include at least one core team member to help align with the broader roadmap.

### Roles

#### Maintainers
Maintainers are in charge of the day to day maintenance of the team's projects. They review, approve, and merge PRs, ensuring contributions align with project goals and meet the project's quality standards.

New maintainers must already be contributors, must be nominated by an existing maintainer or core team member, and must be elected by a [supermajority](#supermajority) of the core team. Likewise, maintainers can be removed by a supermajority of the core team or can resign by notifying one of the maintainers.

#### Contributors
Contributors are those who make regular contributions to the project (documentation, code reviews, responding to issues, participation in proposal discussions, contributing code, etc.). New contributors may be self-nominated or be nominated by existing contributors, and must be elected by a supermajority of the project’s maintainers. Contributors may merge approved PRs.

### [Implementation Team](TEAMS.md#Implementation-Team)
The Implementation team is responsible for maintaining the components that constitute the Cloud Native Buildpacks reference implementation of the specification. This includes:

* [lifecycle](https://github.com/buildpacks/lifecycle)
* [libbuildpack](https://github.com/buildpacks/libbuildpack)
* [imgutil](https://github.com/buildpacks/imgutil)

### [Platform Team](TEAMS.md#Platform-Team)
The Platform team is responsible for maintaining pack and any other platforms or platform components. This includes:

* [pack](https://github.com/buildpacks/pack)
* [Tekton Template](https://github.com/tektoncd/catalog/tree/master/buildpacks)

### [Learning Team](TEAMS.md#Learning-Team)
The Learning team is responsible for maintaining the project’s documentation, website, and resources. This includes:

* [docs](https://github.com/buildpacks/docs)
* [resources](https://github.com/buildpacks/resources)
* [samples](https://github.com/buildpacks/samples)

## Emeritus Team
Serving as a member of an open source project requires a huge amount of work that cannot be sustained indefinitely. The emeritus team includes members of the project to whom we will always be grateful, but who no longer actively participate in the project.

Project members will graduate to the emeritus team with a supermajority vote from the core team, and after giving notice that they no longer intend to consistently participate in the project.

## RFC Process
Each major decision in Cloud Native Buildpacks starts as a Request for Comments (RFC). Everyone is invited to discuss the proposal, to work toward a shared understanding of the tradeoffs.

RFCs record potential changes with the context and information at the given time. This provides a defined process for anyone wishing to propose a substantial changes to the Cloud Native Buildpacks project as well as collect a diverse set of inputs and give opportunity for engagement. Anyone who chooses not to actively participate in any RFC is presumed to trust their colleagues on the matter. Once an RFC is accepted, they can be referenced as read-only documents in this repository until replaced or amended by another RFC when context has significantly changed.

RFCs are not regarded as documentation. The official specification and implementations may differ or lag behind a finalized or historical RFC. For more information, see the [RFC RFC](https://github.com/buildpacks/rfcs/blob/master/text/0004-rfc-process.md).

In order to ensure RFCs receive proper attention and don't stagnate, we've adopted a practice of the "RFC Roundup" during one weekly working group meeting - we go through currently open RFCs, check up on their status, and make sure discussion is still active and discuss how to move them forward.

## Roadmap
The Cloud Native Buildpacks Core Team is responsible for establishing a yearly roadmap laying out our aspirations for that year. This shared vision is essential for keeping the development process focused.

## Updating Governance
All substantive changes in Governance require a supermajority agreement by the Core Team.

---
#### Foototes:

##### Supermajority:
[supermajority]: #supermajority
Throughout these documents, "supermajority" means 66%+. In the case of a team with one maintainer, their single vote is sufficient.
