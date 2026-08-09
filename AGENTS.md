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

## Local verification

From the repository root, serve the site with:

```bash
python3 -m http.server 8080
```

Open `http://localhost:8080/` and manually inspect the changed page plus the shared navigation and footer. There is no automated test suite currently documented for this repository.

## Documentation

Update `README.md` when the local serving workflow changes. Keep product-history, privacy, support, and setup pages aligned when a product claim or installation flow changes.
