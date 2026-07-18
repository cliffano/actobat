# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## Unreleased

### Fixed
- Fix dotfiles update to include files under .github/
- Fix incorrect docs target being called from ci
- Fix doc report generation OS error

## 1.0.0 - 2026-07-18
### Added
- Add DEVELOPERS_GUIDE and BUILD_REPORTS markers
- Add build reports publishing to CI workflow
- Add doc target using Action Docs

### Changed
- Shift dependency management to pip-tools

## 0.11.0 - 2026-07-17
### Changed
- Shift version setting to action.yml as custom property
- Shift test verifications to test workflow

### Fixed
- Fix example CI workflow to simply call ci target
- Fix failing message outputs verification

## 0.10.0 - 2026-07-16
### Added
- Initial version
