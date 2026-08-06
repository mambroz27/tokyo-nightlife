# Change Log

All notable changes to the "Tokyo Nightlife" theme will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.0.5] - 2026-08-05

### Changed

- Transferred repository ownership to the "tokyo-nightlife" organization on GitHub for better project management and collaboration.
- Updated links as necessary to reflect the new repository location and ownership, ensuring that all references point to the correct GitHub organization and repository.
- Fixed default-library method/function calls rendering in a single color. Now `method.defaultLibrary` and `function.defaultLibrary` now use the theme's function color (
  #7AA2F7) instead of silently falling through to the `*.defaultLibrary` wildcard, which was set to the same cyan (
  #2AC3DE) as `variable.defaultLibrary`.

## [0.0.4] - 2026-08-03

### Changed

- Changed `variable.declaration` to the same color as `variable` (#C0CAF5) to maintain consistency in variable representation.
- Updated `README.md` with new screenshot and color palette to reflect the latest theme changes and improvements.

## [0.0.3] - 2026-07-29

### Added

- Theme Icon
- Bug reporting link in package.json for easier access to the GitHub issues page.
- Gallery banner configuration in package.json to enhance the theme's presentation in the Visual Studio Code marketplace.

## [0.0.2] - 2026-07-27

### Added

- Readme link to vscode.dev

### Changed

- Improved screenshots for better presentation of the theme's features and aesthetics.

## [0.0.1] - 2026-07-26

### Added

- Initial theme version
