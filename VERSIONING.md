# Versioning in the CNB project
For context on how the CNB project thinks about versioning, see [RFC#10](https://github.com/buildpacks/rfcs/blob/master/text/0010-api-versions.md) and [RFC#11](https://github.com/buildpacks/rfcs/blob/master/text/0011-lifecycle-descriptor.md). The CNB project versions our [spec components](#spec) and [implementations](#implementations) following separate schemas, detailed below:


### Spec component versioning
[spec]: #spec
The spec describes two components that are [separately versioned](https://github.com/buildpacks/spec#api-versions). These APIs are versioned as follows:

The APIs are denoted by two numbers "`<major>`.`<minor>`".

#### Platform API Version
Given by CNB platforms to the lifecycle, this version indicates which platform API versions that platform currently support. In review, in [PR#67](https://github.com/buildpacks/spec/pull/67/files), this version indicates the compatibility between a CNB platform and a given lifecycle according to the following rules:
- For Platform API versions `0.1` - `0.2`, the platform is only compatible with lifecycles implementing that exact Platform API.
- For Platform API versions greater than or equal to `0.3`, the platform is guaranteed to be compatible with any lifecycle which supports a platform API greater than or equal to that requested by the platform. The platform must set `CNB_PLATFORM_API` in the lifecycle’s environment to configure this behavior.

#### Buildpack API Version
Documented in the [buildpack spec](https://github.com/buildpacks/spec/blob/master/buildpack.md#buildpacktoml-toml) this field indicate compatibility with a given lifecycle according to the following rules:
- For Buildpack API version `0.1`, the buildpack is only compatible with lifecycles implementing that exact Buildpack API.
- For Buildpack API versions greater than or equal to `0.2`, the platform is guaranteed to be compatible with any lifecycle which supports a Buildpack API greater than or equal to that requested by the platform. The buildpack must set `api` in `buildpack.toml` to configure this behavior.

### Implementation versioning
[implementations]: #implementations

We aim to release the core implementations of the project at a time-based cadence, per https://github.com/buildpacks/rfcs/pull/33. These implementations are versioned as follows:

- __Pack__: Pack is released via Github releases and its versions follow semver conventions.
- __Lifecycle__: Pack is released via Github releases and its versions follow semver conventions.
- __libbuildpack__: libbuildpack is released via Github releases and its versions follow semver conventions.
