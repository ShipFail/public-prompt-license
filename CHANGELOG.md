# Changelog

All notable changes to the Public Prompt License (PPL) project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.2.0] - 2025-12-19

### Changed
- **Architecture:** Shifted to a "Wrapper" approach. PPL v0.2 licenses now incorporate standard licenses (MIT, Apache 2.0, AGPL v3) by reference and extend their scope, rather than rewriting the license text.
- **Definitions:**
    - Renamed `DEFINITIONS.md` to `DEFINITIONS-0.1.md` for archival.
    - Created `DEFINITIONS-0.2.md` for the new version.
    - Added explicit definition of "Source Code" to include TypeScript, Python, etc.
- **Scope:** PPL-S v0.2 now explicitly includes application source code in its reciprocal obligation, while maintaining the infrastructure exclusion.

## [0.1.0] - 2025-12-13

### Added
- **Initial Draft Release (Request for Comment)**
- **Definitions:** Established `DEFINITIONS.md` to define "Prompt Source" and "Agent Service".
- **Licenses:**
    - `PPL-M` (MIT-style): Permissive, minimal friction.
    - `PPL-A` (Apache-style): Permissive, with patent grants and attribution.
    - `PPL-S` (Service-style): Reciprocal for Agent Services, with infrastructure exclusion.
- **Documentation:**
    - `RATIONALE.md`: Gap analysis vs MIT/AGPL/SSPL.
    - `HOW-TO-APPLY.md`: Usage guide.
    - `FAQ.md`: Common questions on scope and secrets.
    - `COMPATIBILITY.md`: License interaction matrix.
- **Templates:** Added headers and NOTICE templates.
