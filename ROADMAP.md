# Roadmap

The Cloud Native Buildpacks project is rallying around the theme *Coming of Age* in 2020. Our roadmap will emphasize features and fixes that bring Cloud Native Buildpacks toward a 1.0 release, signaling that the project is mature enough for anyone to use it in production.

The roadmap is subdivided into three categories that represent the different goals we want to achieve. They are *Maturation*, *Beyond Pack*, and *Path to Production*. Below are outcomes and features we we will be working on for each of these categories. This roadmap will continue to be updated as our priorities evolve.

## Maturation

This part of our roadmap will ensure we’re delivering the best tools we can to our users. We want to finish work we've already started, increase the quality of the things we release, and improve our documentation.

### Buildpackages
- Outcomes: A container-native distribution mechanism (using registries) and developer friendly ergonomics for complex buildpack configurations.
- Status: Close to done.
- RFC: https://github.com/buildpacks/rfcs/blob/master/text/0007-spec-distribution.md
- Spec: https://github.com/buildpacks/spec/blob/master/distribution.md#buildpackage
- Issue(s): https://git.io/JvJGt

### Reproducibility
- Outcomes: Builds are verifiable. Build output can be replicated.
- Status: In progress
- Issue(s): https://git.io/JvJsN

### Codifications to our release process
- Outcomes: Our technology is easier to predictably consume and build on top of
- RFC: https://github.com/buildpacks/rfcs/pull/33

### Project descriptor
- Outcomes: Improvements to the UX for buildpack consumers (application developers)
- Status: In progress
- RFCs:
    - https://github.com/buildpacks/rfcs/blob/master/text/0019-project-descriptor.md
    - https://github.com/buildpacks/rfcs/pull/32
- Issue(s): https://git.io/JvJGW

### Service Bindings
- Outcomes: Apps can easily run on a variety of platforms
- RFC: https://github.com/buildpacks/rfcs/blob/master/text/0012-service-binding.md
- Spec: https://github.com/buildpacks/spec/blob/master/extensions/bindings.md

### End User onboarding
- Outcomes: Getting started with the project is simple and documented
- Issue(s): https://git.io/JvJcH

## Beyond Pack

The goal of this category is to bring the experience delivered by the `pack` CLI to more platforms. This will allow our community to use buildpacks in different kinds of environments and in new ways. We'll achieve this by adding support for new build pipelines, enabling the distribution of buildpacks, and extending constructs like the [stack](https://buildpacks.io/docs/concepts/components/stack/) so that they work in more scenarios.

### CI/CD Adapters
- Outcomes: Developers can move beyond workstation builds to production
- RFCs:
    - https://github.com/buildpacks/rfcs/pull/39
- Issue(s): https://git.io/JvJcA

### OS packages
- Outcomes: Developers have the flexibility they need to run code that depends on native OS packages
- RFC: https://github.com/buildpacks/rfcs/pull/23

### Buildpack registry
- Outcomes: Distribution, hosting, and discovery of buildpacks supports a growing CNB ecosystem.
- RFC: https://github.com/buildpacks/rfcs/pull/35
- Issue(s):

## Path to Production

The last part of our roadmap brings Cloud Native Buildpacks to state where they are ready for anyone to use in production. This requires a level of stability in the API and interfaces that ensure breaking changes are uncommon in the future. It also requires us to be as transparent as possible with our community. Above all it is dependent on delivering the outcomes described in *Maturation* and *Beyond Pack*.

### Version 1.0
- Outcomes: Buildpacks are ready for production
- RFC: TBD

### Governance
- Outcomes: Our community knows how we make decisions and how to contribute
- Docs: https://github.com/buildpacks/community/blob/master/GOVERNANCE.md
