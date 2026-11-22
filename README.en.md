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

**[Download v1.0.3 for macOS](https://github.com/Frio99/claude-code-cmux/releases/download/v1.0.3/Claude.Code.Cmux.v1.0.3.macOS.zip)**

## Install (3 steps)

1. **Download & unzip** — click the download link above
2. **Drag to Applications** — move `Claude Code Cmux.app` into your `/Applications/` folder
3. **Add to Finder toolbar** — hold `Cmd` key and drag the app onto the Finder toolbar

Or via command line:

```bash
git clone https://github.com/Frio99/claude-code-cmux.git
cp -R "claude-code-cmux/Claude Code Cmux.app" /Applications/
```

### First run

1. In cmux, press `⌘,` to open Settings, go to **Automation**, and set **Socket Control Mode** to **Automation mode**. You only do this once. It applies immediately, with no restart.
2. On the first click, macOS asks whether the app may control Finder. Allow it so the app can read the current folder.

### Security notes

- **Claude skips all permission prompts.** The app starts Claude Code with `--dangerously-skip-permissions`, so it edits files and runs commands without asking. Only use it in projects you trust.
- **Automation mode loosens cmux access control.** Other programs running under your macOS account can control cmux terminals. The app never changes this setting for you.
- **v1.0.1 and v1.0.2 switched cmux to `allowAll` automatically.** That mode lets any local user or process control cmux. If you used those versions, switch back to Automation mode manually.

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

1. Receives the current folder from the Finder toolbar click
2. Locates the `claude` binary (official installer, Homebrew, npm, nvm and other common paths, falling back to your login shell)
3. Calls the cmux CLI to create a new workspace with the target folder as cwd
4. The workspace auto-runs `claude --dangerously-skip-permissions` on startup

## Acknowledgements

This project is inspired by [Claude Code Now](https://github.com/orange2ai/claude-code-now) by [@orange2ai](https://github.com/orange2ai) — a great one-click launcher for Claude Code. Claude Code Cmux adapts the same idea for [cmux](https://cmux.com/) users who want to run Claude Code in a terminal built for AI agents.

## License

MIT
