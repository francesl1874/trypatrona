# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Patrona is a geriatric care management application. The entire app is delivered as a single self-contained `index.html` file (~230KB) that can be opened directly in a browser with no server required.

## Architecture

The `index.html` is a bundled single-file app with this structure:

- **Bootstrapper script** — A vanilla JS loader that runs on DOMContentLoaded. It reads embedded manifest data, decodes base64 assets (with optional gzip decompression via DecompressionStream), creates blob URLs, and injects them into the template HTML.
- **`__bundler/manifest`** script tag — JSON manifest of all assets (fonts, etc.) with their MIME types and base64-encoded data.
- **`__bundler/template`** script tag — JSON-encoded string containing the full app HTML/CSS/JS, with UUID placeholders that get replaced with blob URLs at runtime.
- **`__bundler/ext_resources`** script tag — Maps resource IDs to UUIDs for use via `window.__resources`.

The app uses **React** with **Babel standalone** (`text/babel` script tags) for client-side JSX transformation. Scripts are re-created via `createElement` after document replacement to ensure execution, with `Babel.transformScriptTags()` called manually.

## Development

- **No build step** — Open `index.html` directly in a browser (`file://` protocol works).
- **No package manager or dependencies** — Everything is self-contained in the single HTML file.
- **No test framework** is currently configured.
