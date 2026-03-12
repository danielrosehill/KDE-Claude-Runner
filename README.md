# KDE Plasma Runner for Claude Code CLI

**Status: WIP / Idea**

A KDE Plasma Runner plugin that lets you quickly search for and open local repositories in [Claude Code](https://claude.com/claude-code) directly from KRunner.

## What is a KDE Plasma Runner?

In KDE Plasma (currently at version 6.x, shipping with Plasma 6.3 as of early 2026), **KRunner** is the universal search-and-launch bar activated by `Alt+Space` or `Alt+F2`. It supports plugins called **Runners** that extend its search capabilities — you can search for applications, files, browser tabs, system settings, and more. Custom runners let developers add their own search sources and actions to this interface.

## Concept

This runner would let you type a keyword into KRunner, search across your local repositories, and launch the selected repo in Claude Code inside a Konsole terminal session — all without leaving the desktop.

### Planned Features

- **Configurable base folder path** — Point the runner at your local repositories root (e.g. `~/repos/github/`)
- **Keyword search with ranked results** — Fuzzy or keyword matching against repository names, surfaced as KRunner results
- **One-action launch into Claude Code** — Opens a match in Claude Code CLI by constructing and executing: `konsole -e claude {repo-path}`

## Tech Context

KDE Plasma 6 runners are typically written as C++ plugins using the KRunner framework (`KRunner::AbstractRunner`), though Python-based runners using D-Bus are also possible. The plugin would register a keyword trigger, scan the configured directory for repositories, and return ranked matches to KRunner's result list.
