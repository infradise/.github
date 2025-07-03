# CHANGELOG.md Guideline & Template

> **Company:** Infradise Inc.  
> **Owner:** Core Platform Team / Tech Writing Team  
> **Created:** 2025-07-04  
> **Last Updated:** 2025-07-04  

This document defines the official template and contribution rules for the `CHANGELOG.md` file of our product. All team members must adhere to this guideline for every release.

### 1\. Basic Principles

  - The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).
  - All entries are listed in reverse chronological order (newest first).
  - All upcoming changes for the next release must be documented under the top-level `[Unreleased]` section.

### 2\. Version & Build

  - **Version**: Follows a `Y.M.D` scheme. (e.g., `5.7.4` refers to a release on July 4th, 2025).
  - **Build**: A unique, monotonically increasing integer for every release. (e.g., `2600`, `2601`).

### 3\. Header Format

Every release must use the following two-line header format:

```markdown
## [Version]
*Build BuildNumber / PlatformTag*
```

**Example:**

```markdown
## [5.7.4]
*Build 2605 / Common*
```

### 4\. Platform Tags (for the header)

The platform tag in the `*Build ...*` line must be chosen according to the following rules:

| Situation | Tag | Example |
| :--- | :--- | :--- |
| Release to **all platforms** | `Common` | `*Build 2605 / Common*` |
| Release to the **Mobile group** (iOS, Android) | `Mobile` | `*Build 2602 / Mobile*` |
| Release to the **Desktop group** (Win, macOS, Linux) | `Desktop`| `*Build 2603 / Desktop*` |
| Release to the **Watch group** (watchOS, Wear OS) | `Watch` | `*Build 2606 / Watch*` |
| Release to a **single platform** | `iOS`, `watchOS`, etc. | `*Build 2600 / watchOS*` |
| Release to a **specific combination across groups** | List them, comma-separated | `*Build 2604 / iOS, Android, macOS*`|

### 5\. Change Types

All changes for a release must be grouped under the following standard categories:

  - `### Added`: For new features.
  - `### Changed`: For changes in existing functionality.
  - `### Deprecated`: For features that will be removed in a future release.
  - `### Removed`: For features removed in the current version.
  - `### Fixed`: For any bug fixes.
  - `### Security`: For vulnerabilities.
  - `### Miscellaneous`: For minor changes that don't fit other categories, like typo fixes or minor text updates.

### 6\. Line Item Prefix Rules

Every individual change log line **must** be prefixed according to the following format:

> `- [Platform/Scope] [Functional Area] Description`

  - **Platform/Scope Prefix** (Required): Indicates the audience or platform affected by the change.

      - **Groups:** `[Common]`, `[Mobile]`, `[Desktop]`, `[Watch]`, `[Web]`
      - **Mobile OS:** `[iOS]`, `[Android]`
      - **Smartwatch OS:** `[watchOS]`, `[WearOS]`
      - **Desktop OS:** `[macOS]`, `[Windows]`, `[Linux]`
      - **Linux Distributions:** `[Ubuntu]`, `[Debian]`, `[Fedora]`, `[RHEL]`, `[CentOS]`, `[SUSE]`, `[RockyLinux]`, `[AlmaLinux]`, etc.
          - **Note:** Use `[Linux]` for general changes affecting all distributions. Use specific distribution tags only for issues exclusive to that distribution (e.g., packaging, specific kernel compatibility).

  - **Functional Area Prefix** (Recommended): Indicates the functional part of the system that was changed. Multiple tags can be used.

      - Examples: `[Auth]`, `[API]`, `[UI]`, `[i18n]`, `[Infra]`, `[Performance]`, `[Payment]`, or other terms as defined by the team.

### 7\. Linking

  - The version number (e.g., `[5.7.4]`) must always be enclosed in square brackets `[]`.
  - At the bottom of the file, add the corresponding repository link for each version.
  - Git tags used in links must be based on the unique build number (e.g., `build-2605`) to ensure uniqueness.

### 8\. Language & Style

  - All entries must be written in **English**.
  - Descriptions should focus on the **impact and result** of the change, not just the action taken.

-----

-----

# **Comprehensive Example**

## [Unreleased][Unreleased]

## [5.7.4][5.7.4]

*Build 2605 / Common*

### Changed

  - [Common] [API] Improved overall API latency by replacing the internal request processing library.

### Fixed

  - [Web] [UI] Fixed an issue where the main navigation bar was not displaying correctly on Safari.

## [5.7.3][5.7.3]

*Build 2604 / iOS, Android, macOS*

### Added

  - [Common] [Auth] Users can now sign in with their Apple ID on all supported platforms.

### Fixed

  - [macOS] [UI] Resolved a visual glitch in the settings window when using Stage Manager.

## [5.7.2][5.7.2]

*Build 2603 / Desktop*

### Added

  - [Desktop] Added a new feature to export user data as a CSV file.

### Changed

  - [Windows] The app now uses a native Windows notification style.

### Fixed

  - [Linux] [UI] Fixed a font rendering issue on Wayland display servers.
  - [Ubuntu] Fixed a packaging issue specific to the DEB package.

## [5.7.1][5.7.1]

*Build 2602 / Mobile*

### Changed

  - [Mobile] [UI] Redesigned the main dashboard screen for a more intuitive user experience.

### Fixed

  - [iOS] Fixed a crash that occurred when accessing the camera on iOS 18.
  - [Android] Resolved an issue where push notifications were sometimes duplicated.

## [5.6.30][5.6.30]

*Build 2601 / Watch*

### Added

  - [watchOS] Added a new watch face complication for daily progress.

### Changed

  - [WearOS] Improved battery life by optimizing background health checks.

## [5.6.29][5.6.29]

*Build 2600 / Common*

### Added

  - [Common] [Auth] [API] Added a `rememberMe` parameter to the `/login` endpoint.

### Changed

  - [Web] [UI] Changed the primary button color from blue to green for better accessibility.

### Security

  - [Common] [Infra] Upgraded the web server to patch a critical denial-of-service (DoS) vulnerability.

### Deprecated

  - [Common] [API] The `/api/v1` endpoints are now deprecated and will be removed in a future release. Please migrate to `/api/v2`.

### Removed

  - [Common] Removed the legacy "Classic" theme.

### Fixed

  - [Common] [Auth] Fixed a critical bug where users could not log in with their email address.

### Miscellaneous

  - [Web] [UI] Fixed a typo on the welcome screen.

-----

[Unreleased]: https://github.com/infradise/visualkube/compare/build-2605...HEAD
[5.7.4]: https://github.com/infradise/visualkube/compare/build-2604...build-2605
[5.7.3]: https://github.com/infradise/visualkube/compare/build-2603...build-2604
[5.7.2]: https://github.com/infradise/visualkube/compare/build-2602...build-2603
[5.7.1]: https://github.com/infradise/visualkube/compare/build-2601...build-2602
[5.6.30]: https://github.com/infradise/visualkube/compare/build-2600...build-2601
[5.6.29]: https://github.com/infradise/visualkube/releases/tag/build-2600
