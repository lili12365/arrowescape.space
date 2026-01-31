# Cloudflare Pages 部署配置说明

## 问题解决

如果遇到 "Missing entry-point to Worker script" 错误，请按以下步骤操作：

### 方案 1：使用 Cloudflare Pages（推荐）

1. 登录 Cloudflare Dashboard
2. 进入 **Pages** 项目设置
3. 在 **Build settings** 中：
   - **Build command**: 留空或删除 `npx wrangler deploy`
   - **Build output directory**: 留空或设置为 `.`（当前目录）
   - **Root directory**: 留空或设置为 `/`

4. 保存设置并重新部署

### 方案 2：使用 Workers（如果必须）

如果必须使用 Workers 部署，确保 `wrangler.toml` 文件存在且配置正确。

当前配置已设置为静态站点模式。

## 文件说明

- `wrangler.toml`: Cloudflare Workers/Pages 配置文件
- `package.json`: 项目配置文件
- `index.html`: 主页面文件

## 部署检查清单

- [ ] `wrangler.toml` 文件已创建
- [ ] Cloudflare Pages 构建命令已正确配置
- [ ] 所有文件已提交到 Git 仓库
- [ ] 域名已正确绑定

