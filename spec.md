# Specification

## Overview

A KDE Plasma Runner plugin that enables users to search local repositories and open them in the Claude Code CLI via Konsole.

## Requirements

### 1. Configurable Base Folder Path

The user must be able to configure a root directory that the runner scans for repositories (e.g. `~/repos/github/`). This should be exposed through KRunner's standard plugin configuration interface.

### 2. Keyword Search and Result Ranking

When the user types a query, the runner should match it against repository names within the configured base folder. Results should be ranked by relevance and presented in KRunner's result list.

### 3. Launch in Claude Code CLI

Selecting a result should open the matched repository in Claude Code inside a new Konsole terminal session. The runner constructs and executes:

```
konsole -e claude {repo-path}
```
