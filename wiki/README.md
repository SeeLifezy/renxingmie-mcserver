# GitHub Wiki 部署说明

> 本文件用于说明如何将 `wiki/` 目录下的页面推送到 GitHub Wiki。

## Wiki 页面清单

| 文件 | Wiki 页面 | 说明 |
|------|----------|------|
| `Home.md` | 首页 | Wiki 主页与导航 |
| `服务端列表.md` | 服务端列表 | 全部服务端索引 |
| `启动指南.md` | 启动指南 | 环境要求与启动步骤 |
| `自建Forge服务端.md` | 自建Forge服务端 | 不用自带 Forge，改用自己安装的 Forge |
| `常见问题.md` | 常见问题 | FAQ 与故障排查 |
| `模组清单.md` | 模组清单 | 集成模组列表 |
| `指令参考.md` | 指令参考 | 服务端内可用指令 |
| `脚下随机生成幸运方块.md` | 脚下随机生成幸运方块 | `/luckywalk` 专属指令说明 |

## 首次部署步骤

### 1. 在 GitHub 上启用 Wiki

1. 打开 <https://github.com/SeeLifezy/renxingmie-mcserver/settings>
2. 滚动到 "Features" 区域
3. 勾选 "Wikis"
4. 保存

### 2. 克隆 Wiki 仓库

GitHub Wiki 是独立仓库，地址为：

```
https://github.com/SeeLifezy/renxingmie-mcserver.wiki.git
```

克隆：

```powershell
cd D:\ServerPackCreator\server-packs
git clone https://SeeLifezy@github.com/SeeLifezy/renxingmie-mcserver.wiki.git renxingmie-mcserver.wiki
```

### 3. 复制页面文件

```powershell
# 复制 wiki/ 目录下所有 .md 到 wiki 仓库根目录
Copy-Item "D:\ServerPackCreator\server-packs\renxingmie-mcserver\wiki\*.md" "D:\ServerPackCreator\server-packs\renxingmie-mcserver.wiki\"
```

### 4. 提交并推送

```powershell
cd D:\ServerPackCreator\server-packs\renxingmie-mcserver.wiki
git add .
git commit -m "初始化 Wiki 页面"
git push origin master
```

## 后续更新

修改 `wiki/` 下的 `.md` 文件后，重复步骤 3-4 即可同步到 GitHub Wiki。

## 访问 Wiki

部署完成后访问：

<https://github.com/SeeLifezy/renxingmie-mcserver/wiki>

## 注意事项

- `Home.md` 是 Wiki 首页，必须存在
- 文件名即页面名，中文文件名会显示为中文页面
- Wiki 仓库默认分支为 `master`（非 `main`）
- Wiki 页面间链接使用 `[[页面名]]` 格式，例如 `[[启动指南]]`
