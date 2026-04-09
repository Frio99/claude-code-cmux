# claude-code-cmux

在 [cmux](https://cmux.com/) 中一键启动 [Claude Code](https://claude.ai/claude-code)。

点一下 → cmux 新建工作区 → Claude Code 自动启动，并跳过权限确认。

## 安装

1. 下载或克隆本仓库
2. 将 `OpenInCmux.app` 复制到 `/Applications/`
3. 按住 `Cmd` 键，将 `OpenInCmux.app` 拖到 **Finder 工具栏**

或通过命令行安装：

```bash
git clone https://github.com/Frio99/claude-code-cmux.git
cp -R claude-code-cmux/OpenInCmux.app /Applications/
```

## 使用方法

1. 打开 Finder，进入任意项目文件夹
2. 点击 Finder 工具栏上的 **OpenInCmux** 图标
3. cmux 自动激活，新建工作区，启动 Claude Code

## 环境要求

- macOS
- 已安装 [cmux](https://cmux.com/)
- 已安装 [Claude Code CLI](https://claude.ai/claude-code)
- 需要为 OpenInCmux 开启**辅助功能权限**（系统设置 → 隐私与安全性 → 辅助功能）

## 工作原理

这个 App 本质上是一个包装成 macOS `.app` 的 Shell 脚本：

1. 通过 AppleScript 获取 Finder 当前目录
2. 在 PATH 中查找 `claude` 可执行文件
3. 激活 cmux 并新建工作区（`Cmd+N`）
4. 粘贴并执行 `cd <目录> && claude --dangerously-skip-permissions`

## 许可证

MIT
