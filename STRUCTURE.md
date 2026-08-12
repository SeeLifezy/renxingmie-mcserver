# 仓库目录结构说明

> 本文件用于说明 renxingmie-mcserver 仓库的目录组织方式。

## 仓库定位

本仓库是 **服务端 ZIP 发布归档仓库**，不包含服务端源文件本身。

- **git 历史中**：仅包含 README、CHANGELOG、说明文档
- **Release 附件中**：存放所有服务端的完整 ZIP 包

## 目录结构

```
renxingmie-mcserver/
├── README.md            # 仓库主页（服务端索引 + 下载说明）
├── CHANGELOG.md         # 各服务端版本变更记录
├── STRUCTURE.md         # 本文件，目录说明
├── .gitignore           # 忽略 ZIP 与运行时产物
├── docs/                # （可选）各服务端的详细文档
│   ├── sakura-city.md   # 樱之城服务端详细说明
│   ├── summer.md        # 夏日清凉服务端详细说明
│   ├── midautumn.md     # 中秋服务端详细说明
│   └── ...
└── 中秋幸运方块服务端1.1.zip          # 本地存在的 ZIP，不提交 git
└── 夏日清凉幸运方块服务端1.3.zip      # 本地存在的 ZIP，不提交 git
└── ...                                # 其他 ZIP 同理
```

## 本地 ZIP 文件处理

本地目录中的 7 个 ZIP 文件已被 `.gitignore` 忽略：

- `中秋幸运方块服务端1.0.zip`
- `中秋幸运方块服务端1.1.zip`
- `夏日清凉幸运方块服务端1.3.zip`
- `幸运方块服务端1.0.zip`
- `我的世界幸运空岛竞技服务端1.1.zip`
- `我的世界樱之城幸运方块服务端1.4.zip`
- `脚下随机生成幸运方块服务端1.0.zip`

它们需要 **手动上传到 GitHub Release 附件**：

1. 在本地打 tag：`git tag -a v1.4 -m "樱之城幸运方块服务端 v1.4"`
2. 推送 tag：`git push origin v1.4`
3. 在 GitHub 网页端基于该 tag 创建 Release
4. 上传对应的 ZIP 文件作为 Release 附件

## Release 命名规范

建议采用 `服务端名-v版本号` 的格式：

- `sakura-city-v1.4` - 樱之城幸运方块 v1.4
- `summer-v1.3` - 夏日清凉幸运方块 v1.3
- `midautumn-v1.1` - 中秋幸运方块 v1.1
- `luckywalk-v1.0` - 脚下随机生成幸运方块 v1.0
- `skyblock-arena-v1.1` - 幸运空岛竞技 v1.1
- `midautumn-v1.0` - 中秋幸运方块 v1.0（历史版本）
- `basic-v1.0` - 基础幸运方块 v1.0
