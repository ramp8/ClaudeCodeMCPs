# 🤖 Claude Code MCP Installation Guide

<div align="center">
  
  [![Claude Code](https://img.shields.io/badge/Claude%20Code-MCP%20Servers-5f1478?style=for-the-badge&logo=anthropic&logoColor=white)](https://www.anthropic.com)
  [![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)](LICENSE)
  [![Status](https://img.shields.io/badge/Status-Active-success?style=for-the-badge)](https://github.com)
  
  <p align="center">
    <strong>Extend Claude Code's capabilities with Model Context Protocol (MCP) servers</strong>
  </p>
  
  [📚 Documentation](#documentation) • [🚀 Quick Start](#quick-start) • [🔧 Installation](#installation) • [💡 Examples](#examples)
  
</div>

---

## 📋 Table of Contents

- [Overview](#overview)
- [Prerequisites](#prerequisites)
- [Available MCP Servers](#available-mcp-servers)
  - [Supabase MCP](#-supabase-mcp)
- [Troubleshooting](#troubleshooting)

## Overview

MCP (Model Context Protocol) servers enable Claude Code to interact with external services and tools directly from your terminal. This guide provides easy-to-follow installation instructions for various MCP servers.

## Prerequisites

Before installing any MCP server, ensure you have:

- ✅ Claude Code CLI installed and configured
- ✅ Node.js (v16 or higher) and npm/npx
- ✅ Active account for the service you want to connect

---

## Available MCP Servers

<details>  <summary><strong>🟢 Supabase MCP</strong></summary>

The Supabase MCP server allows Claude Code to interact with your Supabase database, execute queries, and manage your project data.

#### 🔑 Prerequisites

1. **Access Token**: Create a new token at [Supabase Dashboard](https://supabase.com/dashboard/account/tokens)
   - Navigate to Account → Access Tokens
   - Click "Generate New Token"
   - Name it descriptively (e.g., `ClaudeCodeMCP`)
   - Copy and save the token securely

2. **Project Reference** (Optional but recommended): 
   - Go to Project Settings → General
   - Copy your Project ID

#### 📦 Installation Options

##### **Basic Installation**
```bash
claude mcp add supabase -- npx -y @supabase/mcp-server-supabase@latest \
  --access-token YOUR_TOKEN
```

##### **Project-Scoped Installation** *(Recommended for security)*
```bash
claude mcp add supabase -s project -- npx -y @supabase/mcp-server-supabase@latest \
  --access-token YOUR_TOKEN \
  --project-ref YOUR_PROJECT_REF
```

##### **Read-Only Mode** *(For safety)*
```bash
claude mcp add supabase -- npx -y @supabase/mcp-server-supabase@latest \
  --access-token YOUR_TOKEN \
  --read-only
```

#### 🔧 Configuration Options

| Option | Description | Required | Example |
|--------|-------------|----------|---------|
| `--access-token` | Your Supabase access token | ✅ Yes | `sbp_1234567890abcdef` |
| `--project-ref` | Project reference ID | ❌ No | `xyzcompanyproj` |
| `--read-only` | Enable read-only mode | ❌ No | *(flag only)* |

#### 💡 Usage Examples

Once installed, you can use Claude Code to:

```bash
# Query your database
claude "Show me all users in my Supabase database"

# Analyze data
claude "What's the average order value in the last 30 days?"

# Generate reports
claude "Create a summary of user activity this week"
```

#### 🛡️ Security Best Practices

1. **Always use project-scoped installations** when working with specific projects
2. **Enable read-only mode** for data analysis tasks that don't require writes
3. **Rotate your access tokens** regularly
4. **Never commit tokens** to version control

</details>

---

## 🔍 Troubleshooting

<details>
<summary><strong>Common Issues and Solutions</strong></summary>

### Installation Fails

```bash
# Clear npm cache
npm cache clean --force

# Try installation with verbose logging
claude mcp add supabase -- npx -y @supabase/mcp-server-supabase@latest \
  --access-token YOUR_TOKEN --verbose
```

### Token Authentication Errors

- Verify your token hasn't expired
- Ensure you're using the correct token format
- Check if the token has necessary permissions

### Connection Issues

- Verify your internet connection
- Check if Supabase services are operational
- Ensure no firewall is blocking the connection

</details>

---

## 📚 Documentation

- [Claude Code Documentation](https://docs.anthropic.com)
- [MCP Protocol Specification](https://modelcontextprotocol.io)
- [Supabase MCP Server](https://github.com/supabase/mcp-server-supabase)

---

<div align="center">
  
  **Need help?** Check out the [Claude Support](https://support.anthropic.com) or open an issue
  
  <sub>Made with ❤️ for the Claude Code community</sub>
  
</div>
