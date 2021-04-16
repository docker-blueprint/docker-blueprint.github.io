# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.6.0-alpha] - TBD

### Added
- Added support for local branches when pulling blueprints (useful during local development)
- Added support for multiple docker and docker-compose files both in blueprint and in modules
- Added file preprocessor
  - Added dockerfile blueprint variable substitution
  - Added dockerfile directives
- Added proxy for common docker-compose commands: `start`, `stop`, `restart` and `down`
- Added dependency resolver for nested module dependencies
- Added project configuration (name and context)
- Added JIT blueprint "compilation" from `docker-blueprint.yml`
- Added `--dry-run` flag to the new, build & up commands
- Added an option for the modules to disable other modules

### Updated
- Changed branch & tag naming to be in line with the semantic versioning
- Upgraded yq to version 4 (removed undocumented dependency on jq)
- Updated run command to be more sophisticated
- Updated module format: now they are always directories that contain their own
  blueprint files that get merged together
- Updated `docker-blueprint.yml` file format to store minimal required information
- Moved examples from help into their own command
