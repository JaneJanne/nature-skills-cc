# nature-skills-cc

[Yuan1z0825/nature-skills](https://github.com/Yuan1z0825/nature-skills) 的 **Claude Code 插件重打包**。

> 背景：上游仓库已将分发重心转向 Codex，并移除了 Claude Code 插件所需的
> `.claude-plugin/` 清单。本仓库补回该清单，并通过 GitHub Actions
> [每日自动同步](.github/workflows/sync-upstream.yml)上游的 `skills/`，
> 使 Claude Code 用户可以继续以插件形式一键安装和更新。
> 规则与内容版权归上游作者（Yuan1z0825），MIT 许可。

## 安装（Claude Code）

```bash
# 添加本仓库为插件市场（一次性）
claude plugin marketplace add https://github.com/JaneJanne/nature-skills-cc

# 安装插件
claude plugin install nature-skills
```

或在会话中用 `/plugin` 面板操作。

## 更新

本仓库每日自动同步上游；你本地只需：

```bash
claude plugin marketplace update nature-skills
claude plugin update nature-skills
```

## 启用 / 停用

```bash
claude plugin disable nature-skills   # 停用（skill 描述不再占用上下文）
claude plugin enable nature-skills    # 重新启用
```

## 注意事项

- `nature-academic-search` 依赖本地 MCP 服务，安装后需运行
  `skills/nature-academic-search/install.sh <你的邮箱>` 并重启 Claude Code，
  详见该 skill 目录内的 README。
- 其余 skill 开箱即用。skill 数量以上游最新为准（本仓库会自动跟随）。
- 插件会以 agent 权限运行，安装前请自行审查 `skills/` 下的内容。
