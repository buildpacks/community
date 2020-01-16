# Versioning in the CNB project
For context on how the CNB project thinks about versioning, see [RFC#10](https://github.com/buildpacks/rfcs/blob/master/text/0010-api-versions.md) and [RFC#11](https://github.com/buildpacks/rfcs/blob/master/text/0011-lifecycle-descriptor.md). The CNB project versions our [spec components](#spec) and [implementations](#implementations) following separate schemas, detailed below:


### Spec component versioning
[spec]: #spec
The spec describes two components that are [separately versioned](https://github.com/buildpacks/spec#api-versions). These APIs are versioned as follows:

#### Platform API Version
Given by CNB platforms to the lifecycle, this version indicates which platform API versions that platform currently support. In review, in [PR#67](https://github.com/buildpacks/spec/pull/67/files), this version indicates the compatibility between a CNB platform and a given lifecycle according to the following rules:
- When `<major>` is `0`, the platform is only compatible with lifecycles implementing that exact Platform API.
- When `<major>` is greater than `0`, the platforms is only compatible with lifecycles implementing platform API
`<major>.<minor>`, where `<major>` of the lifecycle equals

#### Buildpack API Version
Documented in the [buildpack spec](https://github.com/buildpacks/spec/blob/master/buildpack.md#buildpacktoml-toml) this field indicate compatibility with a given lifecycle according to the following rules:
- When <major> is 0, the buildpack is only compatible with lifecycles implementing that exact buildpack API.
- When <major> is greater than 0, the buildpack is only compatible with lifecycles implementing buildpack API <major>.<minor>, where <major> of the lifecycle equals  <major> of the buildpack and <minor> of the lifecycle is greater than or equal to <minor> of the buildpack.

### Implementation versioning
[implementations]: #implementations

We aim to release the core implementations of the project at a time-based cadence, per https://github.com/buildpacks/rfcs/pull/33. These implementations are versioned as follows:

- __Pack__: Pack is released via Github releases and its versions follow semver conventions.
- __Lifecycle__: Pack is released via Github releases and its versions follow semver conventions.
- __libbuildpack__: libbuildpack is released via Github releases and its versions follow semver conventions.
