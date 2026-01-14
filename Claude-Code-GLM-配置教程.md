# Claude Code 配置 GLM API 使用教程

Claude Code 是一个智能编码工具，可以在终端中通过自然语言命令交互，帮助开发者快速完成代码生成、调试、重构等任务。

## 前提条件

- 安装 Node.js 18 或更新版本环境
- Windows 用户还需安装 Git for Windows

## 安装 Claude Code

### 方式一：npm 安装

```bash
npm install -g @anthropic-ai/claude-code
```

验证安装是否成功：

```bash
claude --version
```

若显示版本号（如 `2.0.14`）则表示安装成功。

### 方式二：Cursor 引导安装

若不熟悉 Node.js 且有 Cursor，可在 Cursor 中输入命令，Cursor 会引导完成安装。

## 配置 GLM Coding Plan

1. 进入代码工作目录
2. 在终端执行 `claude` 命令
3. 按提示配置 API key
4. 若遇到「Do you want to use this API key」选择 Yes

## 运行 Coding Tool Helper

进入命令行界面，执行如下命令运行 Coding Tool Helper：

```bash
npx @z_ai/coding-helper
```

## 开始使用

启动后选择信任 Claude Code 访问文件夹里的文件，即可正常使用。

## 切换模型

手动修改配置文件 `~/.claude/settings.json`，添加或替换环境变量参数：

```json
{
  "env": {
    "ANTHROPIC_DEFAULT_HAIKU_MODEL": "glm-4.5-air",
    "ANTHROPIC_DEFAULT_SONNET_MODEL": "glm-4.7",
    "ANTHROPIC_DEFAULT_OPUS_MODEL": "glm-4.7"
  }
}
```

修改后，启动新的命令行窗口，运行 `claude` 启动 Claude Code，在 Claude Code 中输入 `/status` 确认模型状态。

## 升级 Claude Code

```bash
# 检查当前版本
claude --version

# 升级到最新版本
claude update
```

推荐使用最新版本，已在 Claude Code 2.0.14 等版本验证通过。

## 常见问题

### 手工修改配置不生效

1. 关闭所有 Claude Code 窗口，重新打开新的命令行窗口，再次运行 `claude` 启动
2. 若问题仍存在，删除 `~/.claude/settings.json` 文件，重新配置环境变量，Claude Code 会自动生成新配置文件
3. 确认配置文件的 JSON 格式是否正确，检查变量名称和逗号是否正确

## 扩展功能

配置完成后，可使用以下 MCP 服务器：
- 视觉 MCP 服务器
- 搜索 MCP 服务器
- 网页读取 MCP 服务器
