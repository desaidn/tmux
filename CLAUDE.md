# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a personal tmux configuration repository containing a single `tmux.conf` file with customizations for the tmux terminal multiplexer.

## Configuration Purpose

The `tmux.conf` file provides:
- Window and pane indexing starting from 1 (instead of default 0)
- Directory preservation when creating new windows and panes
- Consistent working directory context across tmux operations

## Common Operations

### Testing Configuration Changes
```bash
# Reload tmux configuration in existing session
tmux source-file ~/.config/tmux/tmux.conf

# Or restart tmux completely
tmux kill-server
```

### Verifying Configuration
```bash
# Check tmux configuration syntax
tmux -f ~/.config/tmux/tmux.conf new-session -d -s test \; kill-session -t test
```

## Architecture

**File Structure**: Single configuration file approach
**Target Location**: `~/.config/tmux/tmux.conf` (XDG Base Directory specification)
**Scope**: Terminal multiplexer behavior customization
**Dependencies**: None - pure tmux configuration

## Key Configuration Features

- **Index Customization**: Windows and panes start from 1
- **Directory Preservation**: New windows/panes inherit current directory
- **Key Bindings**: Enhanced `C-b c`, `C-b "`, and `C-b %` commands

## Modification Guidelines

- Keep configuration minimal and focused
- Test changes before committing
- Maintain compatibility with standard tmux installations
- Preserve directory context philosophy for new additions