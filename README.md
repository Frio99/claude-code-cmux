# claude-code-cmux

Launch [Claude Code](https://claude.ai/claude-code) instantly in [cmux](https://cmux.com/) from Finder.

One click → cmux opens a new workspace → Claude Code starts in that folder with `--dangerously-skip-permissions`.

## Install

1. Download or clone this repo
2. Copy `OpenInCmux.app` to `/Applications/`
3. Drag `OpenInCmux.app` to your **Finder toolbar** (hold `Cmd` while dragging)

Or via command line:

```bash
git clone https://github.com/frio/claude-code-cmux.git
cp -R claude-code-cmux/OpenInCmux.app /Applications/
```

## Usage

1. Open Finder and navigate to any project folder
2. Click the **OpenInCmux** icon in the Finder toolbar
3. cmux activates, creates a new workspace, and runs Claude Code

## Requirements

- macOS
- [cmux](https://cmux.com/) installed
- [Claude Code CLI](https://claude.ai/claude-code) installed
- **Accessibility permission** for OpenInCmux (System Settings → Privacy & Security → Accessibility)

## How it works

The app is a simple shell script wrapped as a macOS `.app`:

1. Gets the current Finder directory via AppleScript
2. Finds the `claude` binary in your PATH
3. Activates cmux and creates a new workspace (`Cmd+N`)
4. Pastes and runs `cd <dir> && claude --dangerously-skip-permissions`

## License

MIT
