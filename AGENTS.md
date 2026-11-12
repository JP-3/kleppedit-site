# Agent guidance for kleppedit-site

## Scope

This repository is the public Klypp product website. It is a static HTML/CSS site with images, SVG badges, screenshots, and the custom domain file `CNAME`. There is no application build pipeline or package manager in this repository.

## Working rules

- Agents may edit files as requested, but must not commit, push, open pull requests, or deploy unless the user explicitly asks.
- Treat the existing HTML, CSS, images, and page structure as the source of truth. Keep changes focused and do not introduce a framework or dependency for a small site edit.
- Preserve `CNAME`, relative asset paths, page URLs, metadata, canonical links, privacy/delete-account content, and the existing navigation/footer structure unless the task explicitly changes them.
- Use semantic HTML, descriptive image `alt` text, keyboard-accessible links and controls, and responsive styles. Keep public copy consistent with the product and avoid inventing unsupported capabilities.
- Do not add secrets, private URLs, generated build output, `.DS_Store` files, or unrelated formatting changes.
- Check every page touched at desktop and narrow viewport sizes. Check that navigation, images, badges, and external links still resolve.
- When updating release history or documenting a new product capability, inspect the related sibling projects under `/Users/johnprout/git/Code` (especially `KlyppServer`, `Klypp`, and `KlyppRelayServer`) for recent user-facing changes. Identify any matching website pages that also need updates, but keep unrelated project changes out of the site.

## Updating history

Treat “update history” as a request to research and edit `history/index.html` on the current website branch. Do not stop at a proposed list or request permission to make the requested edits. If the user only asks what is new or what belongs in history, report findings without editing the page.

Review all four sibling repositories under `/Users/johnprout/git/Code`:

| Repository | Changes to look for |
| --- | --- |
| `Klypp` | Android and iOS features, browsing, uploads, reminders, settings, permissions, and platform-specific fixes. |
| `KlyppServer` | Self-hosted server, WebUI, media processing, scanner, storage, Plex integration, updates, and connection recovery. |
| `KlyppRelayServer` | Relay connectivity, routing, transfer reliability, and protocol support for user-facing features. |
| `MediaMover` | Account API, authentication, registration, billing/subscriptions, password resets, and download/distribution changes. |

1. Read the existing history entries and the site's Git history to establish the last substantive update and what it already covers. Use that as the comparison baseline; do not use an arbitrary recent time window or duplicate an already documented feature.
2. Check each sibling repository's branch, working-tree status, and commit history since that baseline. Review relevant diffs and current implementation rather than relying only on commit messages. Distinguish merged changes from development-only or uncommitted work; do not present unfinished work as released. Keep sibling repositories unchanged.
3. Select user-visible features, fixes, and meaningful security or reliability improvements. Group related changes into concise entries describing their effect on users. Omit routine refactoring, test-only work, build warnings, and debug-symbol changes unless they materially affect users.
4. Verify Android and iOS versions separately in the app project. Verify server release/build information where available. Source versions and merge dates do not prove publication or deployment; do not invent a release version or release date. Use a clearly dated milestone when appropriate and report any publication uncertainty.
5. Prepend new entries using the existing card markup, platform categories, filters, and newest-first ordering. Preserve older entries unless correcting a verified error. Identify related setup, settings, FAQ, support, or privacy documentation that needs alignment; make directly necessary text corrections and report any missing screenshots or other follow-up work.
6. Check the changed pages at desktop and narrow widths, verify filters and local links/assets, and run `git diff --check`. Report any verification that could not be completed. Stop any preview server started for this task when finished; do not stop a server that was already running.
7. Summarize the entries added, files changed, checks performed, and any unresolved release information. Leave changes uncommitted unless the user explicitly requests a commit, merge, push, or deployment.

## Local verification

From the repository root, serve the site with:

```bash
python3 -m http.server 8080
```

Open `http://localhost:8080/` and manually inspect the changed page plus the shared navigation and footer. There is no automated test suite currently documented for this repository.

## Documentation

Update `README.md` when the local serving workflow changes. Keep product-history, privacy, support, and setup pages aligned when a product claim or installation flow changes.
