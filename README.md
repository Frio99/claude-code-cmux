# Claude Code Cmux

[中文文档](README.zh.md)

One-click launcher for [Claude Code](https://claude.ai/claude-code) inside [cmux](https://cmux.com/) — the terminal built for AI coding agents.

Click the app in Finder → cmux opens a new workspace → Claude Code starts automatically.

## Download

**[Download v1.0.0 for macOS](https://github.com/Frio99/claude-code-cmux/releases/download/v1.0.0/Claude.Code.Cmux.v1.0.0.macOS.zip)**

## Install

1. Download and unzip
2. Drag `Claude Code Cmux.app` to `/Applications/`
3. Hold `Cmd` and drag the app to your **Finder toolbar**

Or via command line:

```bash
git clone https://github.com/Frio99/claude-code-cmux.git
cp -R "claude-code-cmux/Claude Code Cmux.app" /Applications/
```

## Usage

1. Open Finder and navigate to any project folder
2. Click **Claude Code Cmux** in the Finder toolbar
3. cmux activates, creates a new workspace, and Claude Code starts with `--dangerously-skip-permissions`

## Requirements

- macOS
- [cmux](https://cmux.com/) installed
- [Claude Code CLI](https://claude.ai/claude-code) installed
- **Accessibility permission** — on first launch, allow in System Settings → Privacy & Security → Accessibility

## How it works

A lightweight shell script wrapped as a macOS `.app`:

1. Gets the current Finder directory via AppleScript
2. Locates the `claude` binary in your PATH
3. Activates cmux and creates a new workspace (`Cmd+N`)
4. Runs `cd <dir> && claude --dangerously-skip-permissions`

## Acknowledgements

This project is inspired by [Claude Code Now](https://github.com/orange2ai/claude-code-now) by [@orange2ai](https://github.com/orange2ai) — a great one-click launcher for Claude Code. Claude Code Cmux adapts the same idea for [cmux](https://cmux.com/) users who want to run Claude Code in a terminal built for AI agents.

## License

MIT
