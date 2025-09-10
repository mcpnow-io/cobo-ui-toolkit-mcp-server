# cobo-ui-toolkit-mcp-server
A Model Context Protocol (MCP) server for Cobo UI Toolkit components, providing AI assistants with access to component usage.


> **🚀 将 Cobo UI Toolkit 组件集成到你的 AI 工作流**

Model Context Protocol（MCP）服务器为 AI Agent 提供对 Cobo UI Toolkit 组件的理解。

## 快速上手

```bash
npx @cobo/cobo-ui-toolkit-mcp-server
```


### MCP-Now

接入中...

### Cursor

- 打开设置: `Preferences` -> `Cursor Settings` -> `Tools & Integrations`
- 点击 `New MCP Tools` 新增配置：

```json
{
  "mcpServers": {
    "cobo-ui-toolkit-mcp-server": {
      "command": "npx",
      "args": [
        "@cobo/cobo-ui-toolkit-mcp-server"
      ]
    },
    "mcp-now": {
      "transportType": "sse",
      "url": "http://localhost:8040/cursor/sse"
    }
  }
}
```

重启 Cursor 生效。

### Claude Code

添加配置到 Claude Code

```json
{
  "mcpServers": {
    "cobo-ui-toolkit-mcp-server": {
      "command": "npx",
      "args": [
        "@cobo/cobo-ui-toolkit-mcp-server"
      ]
    }
  }
}
```

### Claude Desktop

终端输入：

```bash
vim ~/Library/Application\ Support/Claude/claude_desktop_config.json
```

新增配置：

```json
{
  "mcpServers": {
    "cobo-ui-toolkit-mcp-server": {
      "command": "npx",
      "args": [
        "@cobo/cobo-ui-toolkit-mcp-server"
      ]
    },
    "mcp-now": {
      "transportType": "stdio",
      "command": "/Users/shu/Desktop/MCP Now.app/Contents/Resources/assets/sse-to-stdio",
      "args": [
        "-u",
        "http://localhost:8040/claude/sse"
      ]
    }
  }
}
```

重启生效。

### VSCode

#### 方法 1: 使用 Continue 插件

1. **安装 Continue Extension**:
   - 打开 VSCode Extensions (Ctrl+Shift+X)
   - 搜索 "Continue" 并安装

2. **配置 MCP Server**:
   - 打开 Command 面板 (Ctrl+Shift+P)
   - 输入 "Continue: Configure" 并选择
   - 添加如下配置：
    ```json
    {
      "continue.server": {
        "mcpServers": {
          "cobo-ui-toolkit-mcp-server": {
            "command": "npx",
            "args": [
              "@cobo/cobo-ui-toolkit-mcp-server"
            ]
          }
        }
      }
    }
    ```

#### 方法 2: 使用 Claude 插件

1. **安装 Claude Extension**:
   - 打开 VSCode Extensions (Ctrl+Shift+X)
   - 搜索 "Claude" 并安装

2. **配置 MCP Server**:
   - 添加如下配置:
    ```json
    {
      "claude.mcpServers": {
        "cobo-ui-toolkit-mcp-server": {
          "command": "npx",
          "args": [
            "@cobo/cobo-ui-toolkit-mcp-server"
          ]
        }
      }
    }
    ```

## 使用示例

### 和 AI 对话

1. **打开 Cursor Chat** (Cmd/Ctrl + L)
2. **询问组件**:
   ```
   "Show me the usage of Cobo UI Toolkit button"
   "List all available components"
   ```

### 代码生成

1. **使用 Cursor Agent**:
   ```
   "Generate a login form using Cobo UI Toolkit components"
   ```

## 功能列表

### Tools

| name                  | description                                 |
|-----------------------|---------------------------------------------|
| get_quick_start_guide | Get quick-start guide for Cobo UI Toolkit   |
| get_components        | Get all available Cobo UI Toolkit components |
| get_component_usage   | Get demo code illustrating how a Cobo UI Toolkit component should be used |
| get_icons             | Get all available Cobo UI Toolkit icons     |
| get_icon_usage        | Get demo code illustrating how a Cobo UI Toolkit icon should be used |


### Resources

| name                  | description                                 |
|-----------------------|---------------------------------------------|
| list_components       | List of available Cobo UI Toolkit components that can be used in the project |
| list_icons            | List of available Cobo UI Toolkit icons that can be used in the project |
| get_installation_guide| Get the installation guide for Cobo UI Toolkit based on build tool and package manager |


### Prompts

| name                  | description                                 |
|-----------------------|---------------------------------------------|
| build_page            | Generate a complete page using Cobo UI Toolkit components |

