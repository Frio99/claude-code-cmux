# Claude Code Cmux

[English](README.en.md)

作者：[@0xEcho99](https://x.com/0xEcho99)

> 一键在 cmux 中启动 Claude Code 的 macOS 小工具。在 Finder 里点一下，cmux 自动新建工作区，Claude Code 直接跑起来。

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

**[下载 v1.0.3 macOS 版](https://github.com/Frio99/claude-code-cmux/releases/download/v1.0.3/Claude.Code.Cmux.v1.0.3.macOS.zip)**

## 安装（3 步搞定）

1. **下载解压** —— 点击上面的下载链接
2. **拖入应用程序** —— 把 `Claude Code Cmux.app` 拖到 `/Applications/` 文件夹
3. **添加到 Finder 工具栏** —— 按住 `Cmd` 键，把 App 拖到 Finder 顶部工具栏上

也可以通过命令行安装：

```bash
git clone https://github.com/Frio99/claude-code-cmux.git
cp -R "claude-code-cmux/Claude Code Cmux.app" /Applications/
```

### 打开时被 macOS 拦截

App 没有购买 Apple 签名，通过浏览器下载后第一次打开会被拦截，这是正常现象。放行一次即可：

**macOS 15 及以上**

1. 在「应用程序」里双击一次 App，被拦时点 **完成**，不要点「移到废纸篓」
2. 打开 **系统设置 → 隐私与安全性**，拉到「安全性」
3. 在 Claude Code Cmux 旁边点 **仍要打开**，按提示输入开机密码

「仍要打开」只在被拦后约 1 小时内出现。没看到的话，再双击一次 App。

**macOS 14 及以下**

右键点击 App，选择 **打开**，在弹窗中再点一次 **打开**。

**也可以用命令放行**（看不到「仍要打开」或提示「已损坏」时）

```bash
xattr -dr com.apple.quarantine "/Applications/Claude Code Cmux.app"
```

这条命令只移除这个 App 的下载隔离标记，不会关闭系统的 Gatekeeper。

### 首次使用

1. 在 cmux 中按 `⌘,` 打开设置，进入 **自动化**，把 **套接字控制模式** 改为 **自动化模式**。只需一次，立即生效，不用重启 cmux。
2. 第一次点击本工具时，macOS 会询问是否允许它控制「访达」，请选择允许。它需要用这个权限读取当前文件夹。

### 安全说明

- **Claude 会跳过所有权限确认**：本工具用 `--dangerously-skip-permissions` 启动 Claude Code，它改文件、执行命令都不会再问你。请只在你信任的项目里使用。
- **自动化模式会放宽 cmux 的访问限制**：你这个 macOS 账号下的其他程序也能控制 cmux 终端。本工具不会替你修改这项设置。
- **v1.0.1 和 v1.0.2 会自动改成「完全开放访问」（`allowAll`）**：该模式允许本机任何用户和程序控制 cmux。用过这两版的话，建议手动改回「自动化模式」。

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

1. 从 Finder 工具栏点击时，自动获取当前目录
2. 定位 `claude` 可执行文件（官方安装、Homebrew、npm、nvm 等常见路径，找不到时用登录 shell 兜底查找）
3. 调用 cmux 内置 CLI 创建新工作区并以目标目录为 cwd
4. 工作区启动时直接执行 `claude --dangerously-skip-permissions`

## 致谢

本项目灵感来自 [@orange2ai](https://github.com/orange2ai) 的 [Claude Code Now](https://github.com/orange2ai/claude-code-now) —— 一个优秀的 Claude Code 一键启动器。Claude Code Cmux 将同样的理念适配给 [cmux](https://cmux.com/) 用户，让你在专为 AI Agent 设计的终端中运行 Claude Code。

## 许可证

MIT
