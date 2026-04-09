# Claude Code Cmux

[English](README.md)

作者：[@0xEcho99](https://x.com/0xEcho99)

在 [cmux](https://cmux.com/) 中一键启动 [Claude Code](https://claude.ai/claude-code) —— 专为 AI 编程 Agent 打造的终端。

在 Finder 中点一下 → cmux 新建工作区 → Claude Code 自动启动。

## 下载

**[下载 v1.0.0 macOS 版](https://github.com/Frio99/claude-code-cmux/releases/download/v1.0.0/Claude.Code.Cmux.v1.0.0.macOS.zip)**

## 安装

1. 下载并解压
2. 将 `Claude Code Cmux.app` 拖入 `/Applications/`
3. 按住 `Cmd` 键，将 App 拖到 **Finder 工具栏**

或通过命令行安装：

```bash
git clone https://github.com/Frio99/claude-code-cmux.git
cp -R "claude-code-cmux/Claude Code Cmux.app" /Applications/
```

## 使用方法

1. 打开 Finder，进入任意项目文件夹
2. 点击 Finder 工具栏上的 **Claude Code Cmux**
3. cmux 自动激活，新建工作区，以 `--dangerously-skip-permissions` 启动 Claude Code

## 环境要求

- macOS
- 已安装 [cmux](https://cmux.com/)
- 已安装 [Claude Code CLI](https://claude.ai/claude-code)
- 首次使用需开启**辅助功能权限**（系统设置 → 隐私与安全性 → 辅助功能）

## 工作原理

一个轻量的 Shell 脚本，包装成 macOS `.app`：

1. 通过 AppleScript 获取 Finder 当前目录
2. 在 PATH 中定位 `claude` 可执行文件
3. 激活 cmux 并新建工作区（`Cmd+N`）
4. 执行 `cd <目录> && claude --dangerously-skip-permissions`

## 致谢

本项目灵感来自 [@orange2ai](https://github.com/orange2ai) 的 [Claude Code Now](https://github.com/orange2ai/claude-code-now) —— 一个优秀的 Claude Code 一键启动器。Claude Code Cmux 将同样的理念适配给 [cmux](https://cmux.com/) 用户，让你在专为 AI Agent 设计的终端中运行 Claude Code。

## 许可证

MIT
