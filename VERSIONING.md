#### Versioning in the CNB project
The CNB project has a variety of versioning schemes that contribute to overall stability and communicates the compatibility of different components.

#### Lifecycle
As the heart of the build process, the lifecycle coordinates two crucial API version contracts:

### Platform API Version
Given by CNB platforms to the lifecycle, this version indicates which platform API versions that platform currently support. In review, in [PR#67](https://github.com/buildpacks/spec/pull/67/files), this version indicates the compatibility between a CNB platform and a given lifecycle according to the following rules:
    - When `<major>` is `0`, the platform is only compatible with lifecycles implementing that exact Platform API.
    - When `<major>` is greater than `0`, the platforms is only compatible with lifecycles implementing platform API
    `<major>.<minor>`, where `<major>` of the lifecycle equals

### Buildpack API Version
Documented in the [buildpack spec](https://github.com/buildpacks/spec/blob/master/buildpack.md#buildpacktoml-toml) this field indicate compatibility with a given lifecycle according to the following rules:
- When <major> is 0, the buildpack is only compatible with lifecycles implementing that exact buildpack API.
- When <major> is greater than 0, the buildpack is only compatible with lifecycles implementing buildpack API <major>.<minor>, where <major> of the lifecycle equals <major> of the buildpack and <minor> of the lifecycle is greater than or equal to <minor> of the buildpack.

#### Releases
- Release cadence: We aim to release the core components of the project on a time based schedule cadence, per https://github.com/buildpacks/rfcs/pull/33
- Pack: Pack is released via Github releases and its versions follow semver conventions.
- Lifecycle: Pack is released via Github releases and its versions follow semver conventions.
