# Cloud Native Buildpacks Governance
This document defines the governance structure for Cloud Native Buildpacks. This project is committed to building an open, inclusive, productive and self-governing open source community that maintains a specification and high-quality tools for translating source code into OCI images. The guidelines herein describe how the Cloud Native Buildpacks (CNB) community should work together to achieve this goal.

## Repositories
All repositories under the [buildpacks](https://github.com/buildpacks) organization are maintained and governed by the buildpacks project.

## [Technical Oversight Committee](TEAMS.md#Technical-Oversight-Committee)

The CNB Technical Oversight Committee (TOC) is modeled on the [CNCF TOC](https://github.com/cncf/toc) as a technical governing body. It oversees all aspects of the project and has a mandate to drive consensus for:

* defining and maintaining the technical vision for the CNB project.
* fostering a healthy and welcoming community, including by defining and enforcing our [Code of Conduct](https://github.com/buildpacks/.github/blob/main/CODE_OF_CONDUCT.md).
* ensuring the project is [vendor-neutral](](https://contribute.cncf.io/maintainers/community/vendor-neutrality/)).
* defining the governance structure of the CNB project.
* creating new teams, reorganizing teams, and removing existing teams.
* delegating responsibilities to teams and re-allocating responsibilities amongst teams.
* appointing Team Leads.
* defining the [RFC process](https://github.com/buildpacks/rfcs#rfc-process) through which cross-cutting changes are proposed and approved.
* defining the annual roadmap.
* anything else that falls through the cracks.

New TOC members must be nominated by an existing TOC member and elected by a super-majority of the TOC. TOC members may graduate to emeritus status by request or, in exceptional circumstances, by a super-majority vote of the TOC. The TOC consists of up to 5 seats with no more than 2 seats from any one organization.

## Teams
CNB Teams are responsible for narrower sets of concerns related to specific aspects of the project.

### Roles

#### Team Leads

Each team has a Team Lead. The Team Lead is a maintainer who has special responsibilites for representing team concerns at the project level. Team Leads are appointed by the TOC.

These additional responsibilities include:
* casting binding votes on RFCs as described in the RFC process.
* stewarding project RFCs owned by the team as described in the RFC process.
* representing the work of the team to the TOC.
* acting as the **Release Manager** for the team's components, including making final release decisions and ensuring compliance with the project's release processes.
* delegating another maintainer from the same Team to temporarily fulfill these responsibilities.

#### Maintainers
Maintainers are in charge of the day to day maintenance of the team's projects including:
* ensuring contributions align with project goals and meet the project's quality standards.
* reviewing, approving, and merging PRs.
* planning release milestones, and releasing components under the team's area of responsibility.
* representing the work of the team to the community.
* supporting contributors.
* growing the team by mentoring aspiring contributors and maintainers.

New maintainers must already be contributors, must be nominated by an existing maintainer, and must be elected by a [supermajority](#supermajority) of CNB Team Leads and the TOC. Likewise, maintainers may resign or be removed by a super-majority of Team Leads and the TOC.

#### Component Maintainers

Component maintainers are in charge of the day to day maintenance of the specific code repositories of a software-component inside a CNB team. They will take under their responsibility a well defined software component in a CNB team and for each repository will be allow to:

- reviewing, approving, and merging pull requests.
- planning release milestones, and releasing components versions
- edit, label, assign issues

##### Guidelines nominate component maintainer

Follow this guideline to nominate a **component maintainer** for a software component inside a team

- The software component must be defined under the [GOVERNANCE](https://github.com/buildpacks/community/blob/main/GOVERNANCE.md) team section, for example: Platform Team -> kpack
- New **component maintainers** must already be contributors of the team
- New **component maintainers** must be nominate by a **team lead** or a **maintainer** of the team under the following scenarios:  
  - A software component developed outside CNB project was [accepted](https://github.com/buildpacks/community/blob/main/contributors/guide.md#component) under their team and they do not have the know-how or experience to handle it.
  - A community **contributor** has explicitly manifest the desire to become a **component maintainer** and the **team lead** or **maintainer** consider he/she has the skills and knowledge to take the responsibility and accountability of the component.
- New **component maintainers** must be elected by [super-majority](https://github.com/buildpacks/community/blob/main/GOVERNANCE.md#supermajority) of the team’s maintainers

For more information, see the [RFC Repo](https://github.com/buildpacks/rfcs/blob/main/text/0108-governance-component-maintainer-role.md#how-it-works)

#### Contributors
Contributors are those who make regular contributions to a team (documentation, code reviews, responding to issues, participation in proposal discussions, contributing code, etc.) and are actively participating in the community (e.g., through Slack or community meetings). They are granted additional permissions (triaging issues, merging approved PRs, pushing to non-protected branches) that support those activities.

New contributors may be self-nominated or be nominated by existing contributors, and must be elected by a super-majority of the team’s maintainers. Likewise, contributors may resign or can be removed by a super-majority of team maintainers.

### [Implementation Team](TEAMS.md#Implementation-Team)
The Implementation team is responsible for maintaining the components that constitute the Cloud Native Buildpacks reference implementation of the specification. This includes:

* [lifecycle](https://github.com/buildpacks/lifecycle)
* [imgutil](https://github.com/buildpacks/imgutil)

### [Platform Team](TEAMS.md#Platform-Team)
The Platform team is responsible for maintaining pack and any other platforms or platform components, as well as tools and services that support the distribution and discovery of buildpacks. This includes:

* [pack](https://github.com/buildpacks/pack)
* [Tekton Tasks + Pipelines](https://github.com/buildpacks/tekton-integration)
* [CircleCI Pack Orb](https://github.com/buildpacks/pack-orb)
* [Buildpack Registry API](https://github.com/buildpacks/registry-api)
* [Buildpack Registry Index](https://github.com/buildpacks/registry-index)
* [Buildpack Registry Namespace Owners](https://github.com/buildpacks/registry-namespaces)
* [Github Actions](https://github.com/buildpacks/github-actions)

### [Learning Team](TEAMS.md#Learning-Team)
The Learning team is responsible for maintaining the project’s documentation, website, and resources. This includes:

* [docs](https://github.com/buildpacks/docs)
* [resources](https://github.com/buildpacks/resources)
* [samples](https://github.com/buildpacks/samples)

### [Buildpack Authors' Tooling Team](TEAMS.md#Buildpack-Authors-Tooling-Team)
The Buildpack Authors' Tooling team is responsible for helping buildpack authors create buildpacks. This includes:

* [libcnb](https://github.com/buildpacks/libcnb)

### Emeritus
Serving as a member of an open source project requires a huge amount of work that cannot be sustained indefinitely. Our teams recognize emeritus members to whom we will always be grateful, but who no longer actively participate in the project.

Project members should graduate to emeritus status through self-nomination, when they no longer intend to actively fulfill an assigned role in the project. Members holding multiple roles may choose emeritus status for one role while retaining other roles.

When members have not been [active contributors][contributions] for longer than 3 months they will be moved to emeritus. Out of courtesy, a notice for nomination should be given to members that fall under this category prior to being nominated.

If emeritus members in a leadership position in the project (maintainer, team-lead, TOC member) wish to regain an active role, they may skip the normal nomination process and can do so by renewing their contributions for at least two weeks and self-nominating themselves. Active members should welcome such a move.

[contributions]: https://github.com/buildpacks/community/blob/main/contributors/guide.md#contributions

## Voting Rules

All voting in the CNB project will adhere to a [lazy consensus](https://openoffice.apache.org/docs/governance/lazyConsensus.html) model. In order for an RFC, proposal, or other motion to pass, the following must hold true:

* There are no votes against the motion
* There is at least one vote in favor of the motion

The absence of a vote from a party with a binding vote in the process is considered to be a vote in the affirmative. Non-binding votes are welcomed and encouraged.

## RFC Process
Each major decision in Cloud Native Buildpacks starts as a Request for Comments (RFC). Everyone is invited to discuss the proposal, to work toward a shared understanding of the tradeoffs.

RFCs record potential changes with the context and information at the given time. This provides a defined process for anyone wishing to propose a substantial changes to the Cloud Native Buildpacks project as well as collect a diverse set of inputs and give opportunity for engagement. Anyone who chooses not to actively participate in any RFC is presumed to trust their colleagues on the matter. Once an RFC is accepted, they can be referenced as read-only documents in this repository until replaced or amended by another RFC when context has significantly changed.

RFCs are not regarded as documentation. The official specification and implementations may differ or lag behind a finalized or historical RFC. For more information, see the [RFC Repo](https://github.com/buildpacks/rfcs).

## Roadmap
The Cloud Native Buildpacks TOC is responsible for establishing a yearly roadmap laying out our aspirations for that year. This shared vision is essential for keeping the development process focused.

## Vendor Neutrality
The Cloud Native Buildpacks TOC is committed to ensuring the vendor neutrality of the project in accordance with the [CNCF guidelines on what it means for a project to be vendor-neutral](https://contribute.cncf.io/maintainers/community/vendor-neutrality/).

No company may hold a majority (more than fifty percent) of the total TOC seats through any combination of seats. If the outcome of an election results in greater than two employees of the same organization, the individual receiving the fewest votes from any particular employer will be removed until representation on the committee is down to two from that organization.

If employers change because of job changes, acquisitions, or other events, in a way that would violate the company representation rules above, sufficient members of the committee must resign until the composition rules are met. If it is impossible to find sufficient members to resign, all employees of that organization will be removed and new special elections held. In the event of a question of company membership (for example evaluating independence of corporate subsidiaries) a majority of all non-involved TOC members will decide.

The above limits shall be relaxed in event of a TOC members voluntarity leaving the project or stepping down from their roles, with the limitation that the so-constituted committee may not pass any governance changes except by the abstention of TOC members such that composition of the remaining voting members adheres to the guidelines defined above.

## Security

### Authentication
All members of the Cloud Native Buildpacks GitHub organization with elevated permissions (Project Contributors and above) are required to have [two-factor authentication (2FA)](https://docs.github.com/en/organizations/keeping-your-organization-secure/managing-two-factor-authentication-for-your-organization/requiring-two-factor-authentication-in-your-organization) enabled on their GitHub accounts.

### Security Response Team
The Security Response Team is responsible for handling security vulnerabilities and CVEs. This team is composed of all members of the **Technical Oversight Committee** and all **Team Leads**. They are responsible for following the project's security policy and coordinating with relevant maintainers for fixes and disclosures.

## Updating Governance
All substantive changes in Governance require a supermajority agreement by the TOC.

---

#### Foototes:

##### Supermajority:
[supermajority]: #supermajority
Throughout these documents, "supermajority" means 66%+. In the case of a team with one maintainer, their single vote is sufficient.
