# Cloudflare Pages 部署配置说明

## ✅ 已完成的配置

已创建 `wrangler.jsonc` 配置文件，使用正确的 JSON 格式：

```json
{
  "name": "arrowescape-game",
  "compatibility_date": "2026-02-01",
  "assets": {
    "directory": "."
  }
}
```

## 问题解决

如果遇到 "Missing entry-point to Worker script" 错误，已通过创建 `wrangler.jsonc` 解决。

### 当前配置说明

- ✅ `wrangler.jsonc`: 使用 JSON 格式的 Cloudflare Workers 配置文件
- ✅ `assets.directory`: 设置为 `"."`（当前目录），因为 `index.html` 在根目录
- ✅ `compatibility_date`: 设置为最新日期

### 方案 1：使用 Cloudflare Pages（推荐，如果 Workers 仍有问题）

1. 登录 Cloudflare Dashboard
2. 进入 **Pages** 项目设置
3. 在 **Build settings** 中：
   - **Build command**: 留空或删除 `npx wrangler deploy`
   - **Build output directory**: 留空或设置为 `.`（当前目录）
   - **Root directory**: 留空或设置为 `/`

4. 保存设置并重新部署

### 方案 2：使用 Workers（当前配置）

当前已配置为使用 Workers 部署静态网站：
- `wrangler.jsonc` 文件已创建
- 配置指向当前目录的静态文件

## 文件说明

- `wrangler.jsonc`: Cloudflare Workers 配置文件（JSON 格式）
- `package.json`: 项目配置文件
- `index.html`: 主页面文件

## 部署检查清单

- [x] `wrangler.jsonc` 文件已创建
- [ ] 所有文件已提交到 Git 仓库
- [ ] 推送到 GitHub 后等待 Cloudflare 自动部署
- [ ] 检查部署日志确认成功

## 下一步操作

1. 提交所有文件到 Git：
```bash
git add wrangler.jsonc
git commit -m "fix: 添加 wrangler.jsonc 配置文件用于 Cloudflare 部署"
git push origin main
```

2. 等待 Cloudflare 自动检测并部署（1-2 分钟）

3. 检查部署状态和日志



