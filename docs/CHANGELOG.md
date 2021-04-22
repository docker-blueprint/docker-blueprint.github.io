# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.6.1-beta] - 22-04-2021

### Added
- Added `upgrade` command to update used blueprint version
- Guided installation

### Updated
- Fix module add/remove commands not updating containers
- Silence helper scripts by default
- Sync after up scripts

### Fixed
- Sync after scripts have been run after `up` command finishes
- Always refresh containers after building them

## [0.6.0-beta] - 18-04-2021

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
