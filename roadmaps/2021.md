# Roadmap

The Cloud Native Buildpacks project is rallying around the theme *Sustainable Growth* in 2021. 
Our roadmap will emphasize projects that help grow our community, contributors, and adopters. 
We'll prioritize projects that make Buildpacks more accessible to a wider audience and we'll try to solve problems that have prevented some users from adopting Buildpacks.
### Documentation Rework
- **Outcomes**:
  - Revisit our documentation so it's easier to find the content needed, includes a reference section, and backfill missing topics.
- **Personas**:
  - Application Developers
  - Buildpack Authors
  - Platform Authors
  - Contributors
- **Status**: Not started

### Test API
- **Outcomes**: 
  - A specification defining an API for setting up and running tests in a buildpacks-based environment.
- **Personas**:
  - Application Developers
  - Buildpack Authors
- **Status**: Not started

### Spec Refactor
- **Outcomes**: 
  - A restructured specification for Cloud Native Buildpacks that is more approachable, and easier to ammend.
- **Personas**:
  - Platform Authors
  - Buildpack Authors
  - Contributors
- **Status**: Not started

### Configurability
- **Outcomes**: 
  - Better escape hatches, flexibility, and ways of configuring buildpack builds. 
  - Extending project descriptor to support process types, labels, and runtime env vars.
  - Support for Inline Buildpacks.
- **Personas**:
  - Application Developers
  - Buildpack Authors
- **Status**: Not started
- **RFCs**:
  - [RFC-0048](https://github.com/buildpacks/rfcs/blob/main/text/0048-inline-buildpack.md)

### Stack Buildpacks
- **Outcomes**: 
  - Better support for adding mixins to stacks.
  - Ability for platform authors and stack authors to allow stacks to be customized.
- **Personas**:
  - Platform Authors
  - Application Developers
  - Buildpack Authors
- **Status**: In progress
- **RFCs**:
    - [RFC-0069](https://github.com/buildpacks/rfcs/blob/main/text/0069-stack-buildpacks.md)

### Develop API
- **Outcomes**:
  - A specification defining an API for inner-loop development iterations in a buildpacks-based environment.
- **Personas**:
  - Application Developers
  - Buildpack Authors
- **Status**: Not started

### Integration with the Cloud Native Ecosystem
- **Outcomes**: 
  - A better out-of-the box Kubernetes and Docker integration story
- **Personas**:
  - Platform Authors
  - Application Developers
- **Status**: Not started
