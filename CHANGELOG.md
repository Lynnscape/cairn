# Changelog

Notable changes to Cairn, newest first. The format follows
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and versions follow
[Semantic Versioning](https://semver.org/spec/v2.0.0.html). How a release is cut:
`docs/deployment.md` → "Releases".

## [Unreleased]

## [1.0.2] - 2026-11-23

### Security

- Caddy, which serves the app and routes every request, is upgraded from 2.9.1
  to 2.11.9. This brings nearly two years of fixes to Caddy and to the Go
  runtime it is built with.

## [1.0.1] - 2026-11-23

### Changed

- The source code moved to <https://github.com/Lynnscape/cairn>, and the
  licence page links there. The old address redirects.
- The About screen's footer links "Lynnscape" to <https://www.lynnscape.eu>.

### Security

- All three images (web build, auth proxy, avatar sidecar) now build on Node 26
  LTS instead of Node 20, which reached end of life in April 2026 and no longer
  receives security fixes.
- Every dependency is updated to its latest release, including major upgrades of
  Express (4 to 5), Multer (1 to 2), Nodemailer, jose, Vitest and Vite. Only
  TypeScript (held at 6) and SvelteKit (held at 2) stay behind, for the reasons
  recorded in the commit message.

## [1.0.0] - 2026-10-20

First release, live at <https://cairn.lynnscape.eu>.

### Added

- Shared lists for small groups: items with optional notes, and per-member
  votes from −3 to +3 summed into a score. Lists and items sort alphabetically.
- Sharing by username, with a per-person invite policy, circles and blocking.
- Public, read-only links to a list.
- Sign-in with a username and password. An optional e-mail address is used
  only for password recovery.
- A bin with undo for deleted items and lists.
- Profile pictures.
- Data export (a ZIP of JSON and HTML) and account deletion.
- Light, dark and system themes, and five text sizes.
- An installable Progressive Web App; lists already opened stay readable
  offline.
- An About hub: privacy policy, terms, imprint, contact, open-source
  attributions and the AGPL licence.
- A Home button in the top bar when there is no Cairn page to go back to.
- For the operator: a self-hosted production stack (Postgres, PostgREST,
  GoTrue, Caddy with automatic TLS) and the `cairn-admin` CLI.

[Unreleased]: https://github.com/Lynnscape/cairn/compare/v1.0.2...HEAD
[1.0.2]: https://github.com/Lynnscape/cairn/compare/v1.0.1...v1.0.2
[1.0.1]: https://github.com/Lynnscape/cairn/compare/v1.0.0...v1.0.1
[1.0.0]: https://github.com/Lynnscape/cairn/releases/tag/v1.0.0
