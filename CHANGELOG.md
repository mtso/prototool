# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/)
and this project adheres to [Semantic Versioning](http://semver.org/spec/v2.0.0.html).

## [Unreleased]
### Added
- A new command `prototool create` to auto-generate Protobuf files from a
  template. The generated files have the Protobuf package, go_package,
  java_multiple_files, java_outer_classname, and java_package values set
  depending on the location of your file and config settings. Make sure to
  update your Vim plugin setup as well if using the Vim integration.


## [0.3.0] - 2018-06-14
### Added
- Linters to verify that `java_multiple_files` and `java_outer_classname` are
  unset.
### Fixed
- The formatting order now reflects
  https://cloud.google.com/apis/design/file_structure by moving the location
  of imports to be below syntax, package, and file options.
- Temporary files used for `FileDescriptorSets` are now properly cleaned up.
- Packages that begin with a keyword no longer produce an error when using
  `prototool format` or `prototool lint`.


## [0.2.0] - 2018-05-29
### Added
- A default lint rule to verify that a package is always declared.
- A lint group `all` that contains all the lint rules, not just the default
  lint rules.
- A flag `--harbormaster` that will print failures in JSON that is compatible
  with the Harbormaster API.

### Fixed
- `prototool init` will return an error if there is an existing prototool.yaml
  file instead of overwriting it.
- Nested options are now properly printed out from `prototool format`.
- Repeated options are now properly printed out from `prototool format`.
- Weak and public imports are now properly printed out from `prototool format`.
- Option keys with empty values are no longer printed out
  from `prototool format`.


## 0.1.0 - 2018-04-11
### Added
- Initial release.

[Unreleased]: https://github.com/uber/prototool/compare/v0.3.0...HEAD
[0.3.0]: https://github.com/uber/prototool/compare/v0.2.0...v0.3.0
[0.2.0]: https://github.com/uber/prototool/compare/v0.1.0...v0.2.0
