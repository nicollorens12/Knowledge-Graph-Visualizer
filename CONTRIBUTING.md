# Contributing to Agent Context Graph Visualizer

Thanks for your interest in contributing! This project is open source and welcomes contributions from the community.

## Getting Started

1. **Fork** the repository
2. **Clone** your fork:
   ```bash
   git clone https://github.com/<your-username>/Knowledge-Graph-Visualizer.git
   cd Knowledge-Graph-Visualizer
   ```
3. **Install dependencies**:
   ```bash
   npm install
   ```
4. **Compile**:
   ```bash
   npm run compile
   ```
5. **Test locally** — press `F5` in VS Code to launch the Extension Development Host

## Making Changes

1. Create a feature branch from `main`:
   ```bash
   git checkout -b feat/your-feature-name
   ```
2. Make your changes
3. Make sure it compiles without errors:
   ```bash
   npm run compile
   ```
4. Bump the version in `package.json` (see [Versioning](#versioning))
5. Commit your changes with a descriptive message
6. Push to your fork and open a Pull Request against `main`

## Pull Request Requirements

All PRs to `main` must pass these automated checks before they can be merged:

- **Compile** — TypeScript compilation must succeed
- **Version bump** — the `version` in `package.json` must be strictly greater than the current version on `main` (semver)
- **Review** — a maintainer must approve the PR

If you push new commits after receiving approval, the review resets and re-approval is needed.

## Versioning

This project follows [Semantic Versioning](https://semver.org/):

- **Patch** (`0.2.0` → `0.2.1`) — bug fixes, minor tweaks
- **Minor** (`0.2.0` → `0.3.0`) — new features, non-breaking changes
- **Major** (`0.2.0` → `1.0.0`) — breaking changes

Every PR must include a version bump. If multiple PRs are in flight, you may need to rebase and adjust your version after another PR merges first.

## Project Structure

```
src/
  extension.ts        — Extension entry point, command registration
  graphDataParser.ts   — Markdown file discovery and link parsing
  analyzer.ts          — Post-parse analysis (health, broken links, similarity)
  exporter.ts          — Export to markdown index or JSON
  types.ts             — All TypeScript interfaces
  fileWatcher.ts       — Live file change detection
  webviewProvider.ts   — Webview panel creation and HTML template
  webview/
    graph.js           — D3.js force-directed graph visualization
    styles.css         — Webview styles
```

## Code Style

- TypeScript strict mode is enabled
- Keep changes focused — don't bundle unrelated fixes
- Avoid adding dependencies unless strictly necessary (the extension currently has zero runtime dependencies)
- The webview (`graph.js`) is vanilla JavaScript with D3.js loaded from CDN

## Reporting Issues

Open an issue at [GitHub Issues](https://github.com/nicollorens12/Knowledge-Graph-Visualizer/issues) with:

- What you expected to happen
- What actually happened
- Steps to reproduce
- VS Code version and OS

## License

By contributing, you agree that your contributions will be licensed under the [MIT License](LICENSE).
