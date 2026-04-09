# Claude Code Cmux

[中文文档](README.md)

By [@0xEcho99](https://x.com/0xEcho99)

> A one-click macOS tool to launch Claude Code inside cmux. Click in Finder, cmux creates a new workspace, Claude Code starts automatically.

## What is this?

If you use [Claude Code](https://claude.ai/claude-code) (Anthropic's AI coding assistant) and [cmux](https://cmux.com/) (a Mac terminal designed for AI agents), this app saves you time every single day.

**Without this app**, every time you want to start Claude Code in a project folder, you need to:
1. Open cmux
2. Create a new workspace
3. Type `cd /path/to/your/project`
4. Type `claude --dangerously-skip-permissions`

**With this app**, you just:
1. Click one button in Finder

That's it. One click, and Claude Code is ready to go in your project folder.

## Why cmux?

[cmux](https://cmux.com/) is a Mac terminal built specifically for AI coding agents. Compared to a regular terminal:

- **Vertical tabs** — run multiple Claude Code sessions side by side, easy to switch
- **Notifications** — get notified when Claude Code finishes a task, no need to keep watching
- **Built-in browser** — preview your app without switching windows
- **Designed for AI workflows** — everything is optimized for working with AI agents

## Download

**[Download v1.0.0 for macOS](https://github.com/Frio99/claude-code-cmux/releases/download/v1.0.0/Claude.Code.Cmux.v1.0.0.macOS.zip)**

## Install (3 steps)

1. **Download & unzip** — click the download link above
2. **Drag to Applications** — move `Claude Code Cmux.app` into your `/Applications/` folder
3. **Add to Finder toolbar** — hold `Cmd` key and drag the app onto the Finder toolbar

Or via command line:

```bash
git clone https://github.com/Frio99/claude-code-cmux.git
cp -R "claude-code-cmux/Claude Code Cmux.app" /Applications/
```

> On first launch, macOS will ask for Accessibility permission. Go to **System Settings → Privacy & Security → Accessibility** and allow it.

## Usage

1. Open Finder, navigate to any project folder
2. Click **Claude Code Cmux** in the Finder toolbar
3. Done! cmux opens a new workspace and Claude Code starts automatically

## Requirements

- macOS
- [cmux](https://cmux.com/) installed
- [Claude Code CLI](https://claude.ai/claude-code) installed

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
