# Changelog

## [0.0.8, unreleased] - 2023-xx-xx
### Added
- image package
  - Support image comparison; EqualFromFile()
### Changed
- Refactoring
  - Refactoring for internal code. For example, introduce network struct.

## [0.0.5 - 0.0.7] - 2023-10-12
### Added
- GitHub Actions workflow for [gosec](https://github.com/securego/gosec).
  - Fix gosec issue
- Show image in the report if Content-Type is image MIME

## [0.0.4] - 2023-10-10
### Added
- Generate code coverage report with `make coverage`. 
  - The coverage report name is `coverage.html`.
- Support more http mock methods; HEAD, OPTIONS, CONNECT, TRACE

### Changed
- Dependabot update go.mod in example codes.
- Introduce `Interval` struct for caluculating interval time.

### Removed
- `SpecTest.RecorderHook` is deprecated since apitest package era.

## [0.0.3] - 2023-10-09
### Added
- Support more http methods; HEAD, OPTIONS, CONNECT, TRACE

### Fixed
- Broken example codes. However, some examples are still broken (iris, qraphql).
- Broken unit test; `TestRealNetworking()` had a case where API calls could be made before the server was started.

### Changed
- Refactoring
  - The processing was heavily written in one file, so I split the file into multiple parts.
  - Rename public struct name; APITest to SpecTest

## [0.0.2] - 2023-10-08

### Added
- GitHub Actions
  - Unit Test for Linux/macOS/windows, reviewdog, golangci-lint
- Dependabot and patch/minor version auto update.
- Import side project; jsonpath, jsonschema, plantuml, css-selector
  - aws package is not imported. It's broken.
- `APITest.CustomReportName()`
  - Output sequence diagram with custom name instead of hash.
- Add help target to Makefile.

### Fixed
- Refactoring
  - Refactoring for internal code. For example, meta information is now stored in a struct instead of a map.

### Changed
- Rename 'Http' to 'HTTP'. So, some function names are changed.
  - `Http` -> `HTTP`
  - `HttpHandler` -> `HTTPHandler`
- deprecated method in io/ioutil.

- Export difflib. 
  - I exported difflib as an external package (diff) because it is an independent package. Additionally, I made the diff package compatible with Windows. Specifically, it now displays differences in color even when indicating diffs in a Windows environment.

### Removed
- `APITest.Meta()` method.
  - The precise information of the meta (map[string]interface{}) was not being exposed to users. Consequently, users found it challenging to effectively utilize APITest.Meta(). Instead of providing an alternative method, APITest.Meta() was removed.
