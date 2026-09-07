# GitHub Pages 部署 + 自定义域名 + CDN 配置指南

本站点为 **GitHub Pages 文档站**，源码在仓库 `docs/` 目录，使用 Jekyll + Cayman 主题渲染。

---

## 一、启用 GitHub Pages

1. 打开仓库 <https://github.com/SeeLifezy/renxingmie-mcserver>
2. **Settings** → 左侧 **Pages**
3. **Branch**：选择 `main`，目录选择 **`/docs`**
4. 点击 **Save**
5. 稍等 1~2 分钟，顶部会出现站点地址：`https://SeeLifezy.github.io/renxingmie-mcserver/`

> 首次部署后立即访问可能显示 404，等待 Jekyll 构建完成即可。

---

## 二、配置自定义域名

> 前提：你拥有一个域名，并已做好 DNS 解析（建议使用 CDN 的 DNS，见下文）。

### 2.1 添加 CNAME 文件

在仓库 `docs/` 目录下创建名为 **`CNAME`** 的文件（无扩展名），内容为你的域名：

```text
www.example.com
```

> 也可以访问域名，以裸域名如 `example.com`，按需填写。推送到 main 后 Pages 会自动重新构建。

### 2.2 DNS 记录

在**域名 DNS（即 CDN 的 DNS 处）**添加解析记录：

| 记录类型 | 主机记录 | 记录值 | 说明 |
|---------|---------|--------|------|
| CNAME | `www` | `SeeLifezy.github.io` | 使用 www 子域名时 |
| A | `@` | `185.199.108.153` 等 4 条 | 使用裸域名时 GoDaddy/阿里等要求 A 记录 |

裸域名（`@`）需配置 4 条 A 记录指向 GitHub Pages：
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

### 2.3 在 GitHub Pages 设置中确认域名

Settings → Pages → **Custom domain** 填入域名，点击 Save。GitHub 会自动在 `docs/CNAME` 写入，并为其申请 HTTPS 证书（SSL 由 GitHub 免费提供）。

---

## 三、接入 CDN（如 Cloudflare）

> 你希望用 CDN 加速 + 自定义域名，推荐免费且最主流的 **Cloudflare**。

### 3.1 一个域名的小坑：GitHub 的 `CNAME` 与 Cloudflare 的 CNAME 冲突

GitHub Pages 要求域名解析到 `SeeLifezy.github.io`，而 CDN 需要域名解析到 CDN 节点。**两者不能同时成立**。常用两套方案：

**方案 A：CDN 作为 DNS + 代理（推荐，一处管理）**
- 把域名 DNS 托管到 **Cloudflare**
- Cloudflare 中为该域名加一条 CNAME：`www → SeeLifezy.github.io`，开启 **灰色云朵（仅 DNS，proxy 关闭）**
- 但这样 Cloudflare 只做 DNS，**不缓存/不加速**（GitHub 不允许对自有证书做 CNAME 代理加速，且 Pages 已自带 CDN）
- 结论：用 Cloudflare 主要图的是**免费 HTTPS + DNS 托管**，加速效果有限（GitHub Pages 本身已在多区域有 CDN 节点）

**方案 B：独立静态 CDN（真正加速静态文件）**
- GitHub Pages 站点经 `WebFetch`、脚本等，再被套一层如 `jsDelivr`、腾讯云 CDN、阿里云 CDN 等，回源到 GitHub Pages URL
- 需在 CDN 控制台配置：源站 = `https://SeeLifezy.github.io/renxingmie-mcserver/`，域名绑定你的自定义域名，开启缓存

> 提示：若你的主要诉求是**让国内/海外玩家稳定下载 ZIP 与浏览文档**，腾讯云/阿里云对象存储 + CDN 会比 GitHub Pages 更稳定。若只是想要一个自定义域名 + 简单 HTTPS，`GitHub Pages 自带域名 + 自定义 CNAME` 就已足够。

---

## 四、日常更新

改 `docs/` 下内容后 push，Pages 自动重建，无需手动操作：

```powershell
git add docs
git commit -m "更新文档"
git push origin main
```

---

*详见仓库根目录 README。*