# Claude Code Cmux

[English](README.md)

作者：[@0xEcho99](https://x.com/0xEcho99)

## 这是什么？

如果你在用 [Claude Code](https://claude.ai/claude-code)（Anthropic 的 AI 编程助手）和 [cmux](https://cmux.com/)（专为 AI Agent 设计的 Mac 终端），这个小工具能帮你每天省下不少时间。

**没有这个工具之前**，每次你想在某个项目里启动 Claude Code，你需要：
1. 打开 cmux
2. 新建一个工作区
3. 输入 `cd /你的项目路径`
4. 输入 `claude --dangerously-skip-permissions`

**有了这个工具之后**，你只需要：
1. 在 Finder 里点一下

就这么简单。一键搞定，Claude Code 直接在你的项目文件夹里跑起来。

## 为什么用 cmux？

[cmux](https://cmux.com/) 是一款专为 AI 编程 Agent 设计的 Mac 终端。相比普通终端，它的优势在于：

- **垂直标签页** —— 同时跑多个 Claude Code，左侧标签栏一目了然，随时切换
- **通知提醒** —— Claude Code 完成任务会通知你，不用一直盯着屏幕
- **内置浏览器** —— 预览效果不用切窗口
- **为 AI 工作流设计** —— 一切都为 AI Agent 协作优化

## 下载

**[下载 v1.0.0 macOS 版](https://github.com/Frio99/claude-code-cmux/releases/download/v1.0.0/Claude.Code.Cmux.v1.0.0.macOS.zip)**

## 安装（3 步搞定）

1. **下载解压** —— 点击上面的下载链接
2. **拖入应用程序** —— 把 `Claude Code Cmux.app` 拖到 `/Applications/` 文件夹
3. **添加到 Finder 工具栏** —— 按住 `Cmd` 键，把 App 拖到 Finder 顶部工具栏上

> 首次使用时，macOS 会弹出辅助功能权限请求。前往 **系统设置 → 隐私与安全性 → 辅助功能**，允许即可。

## 使用方法

1. 打开 Finder，进入任意项目文件夹
2. 点击 Finder 工具栏上的 **Claude Code Cmux**
3. 搞定！cmux 自动新建工作区，Claude Code 直接启动

## 环境要求

- macOS
- 已安装 [cmux](https://cmux.com/)
- 已安装 [Claude Code CLI](https://claude.ai/claude-code)

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
