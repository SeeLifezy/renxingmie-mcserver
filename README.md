# 我的世界幸运方块服务端合集

> 作者：**任性咩**  |  B站主页：<https://space.bilibili.com/3494379041852080>
> 交流QQ群：**327320945**  |  支持作者：<https://afdian.com/a/renxingmie>
> Minecraft 版本：**1.20.1 Forge 47.3.3**  |  Java：**17**

---

## 简介

本仓库收录任性咩制作的全部幸运方块系列服务端整合包。所有服务端完全免费，仅供学习与娱乐。

> **重要**：本仓库 git 历史中 **不含 ZIP 文件**（避免仓库体积膨胀）。
> 请通过 [Releases](../../releases) 页面下载对应版本的完整服务端 ZIP 包。

## 服务端列表

| 序号 | 服务端名称 | 最新版本 | 简介 |
|------|-----------|---------|------|
| 1 | 樱之城幸运方块 | 1.4 | 樱之城主题幸运方块空岛竞技 |
| 2 | 夏日清凉幸运方块 | 1.3 | 夏日清凉主题幸运方块 |
| 3 | 中秋幸运方块 | 1.1 | 中秋节主题幸运方块 |
| 4 | 脚下随机生成幸运方块 | 1.0 | 走路脚下随机生成幸运方块（空岛版） |
| 5 | 幸运空岛竞技 | 1.1 | 幸运方块空岛竞技对抗 |
| 6 | 幸运方块（基础版） | 1.0 | 基础幸运方块服务端 |

## 下载方式

### Releases 页面（推荐）

1. 前往 [Releases](../../releases) 页面
2. 选择对应服务端的 Release
3. 下载附件中的 ZIP 文件

## 启动说明

1. 解压下载的 ZIP 文件到任意目录
2. 确保已安装 **Java 17**
3. 双击 `run.bat` 启动服务器（Windows）
4. 首次启动请阅读压缩包内的 `1启动前观看.txt`

### 关键配置（`server.properties`）

| 配置项 | 推荐值 | 说明 |
|--------|--------|------|
| `online-mode` | `true` / `false` | 正版验证；非正版客户端需改为 `false` |
| `enable-command-block` | `true` | **必须开启**，命令方块用于幸运方块逻辑 |
| `max-players` | `10` | 最大在线人数 |
| `server-port` | `25565` | 服务器端口 |

### 内存调整

编辑 `run.bat`，修改 JVM 参数：

```bat
java -Xmx4G -Xms4G @libraries/net/minecraftforge/forge/1.20.1-47.3.3/win_args.txt %*
```

建议预留 1~2 GB 给系统，例如 8 GB 内存机器设置 `-Xmx6G`。

## 特色功能

### 脚下随机生成幸运方块

```
开启：/luckywalk true
关闭：/luckywalk false
```

### 集成内容

- **幸运方块系列**：lucky-block、ChanceCubes、path_lucky_block、randomly_generate_lucky_blocks、Re-Avaritia 等
- **扩展包**：AmongUs、Car、Desert、Fire、Jello、Summer、Water、Pink、Magical 等十余种 Lucky Block addon
- **优化模组**：ferritecore、modernfix、starlight、embeddium、entityculling、memoryleakfix
- **工具模组**：worldedit、WorldEditCUI、litematica、Jade、JEI、Xaero's Minimap/WorldMap
- **枪械系统**：tacz、tp_shooting

## 版本历史

完整版本历史请查看 [Releases](../../releases) 页面。

| 服务端 | 版本 | 说明 |
|--------|------|------|
| 樱之城幸运方块 | 1.4 | 当前稳定版 |
| 夏日清凉幸运方块 | 1.3 | 当前稳定版 |
| 中秋幸运方块 | 1.1 | 修复版本 |
| 脚下随机生成幸运方块 | 1.0 | 初始版本 |
| 幸运空岛竞技 | 1.1 | 平衡性调整 |
| 中秋幸运方块 | 1.0 | 初始版本 |
| 幸运方块（基础版） | 1.0 | 初始版本 |

## 贡献与反馈

- 发现 bug 或有建议：请提 [Issue](../../issues)
- 加群交流：QQ群 **327320945**

## 致谢

- B站 UP 主 **CQz** 制作的幸运方块服务器端
- 任性群友 **SeeLife** 出品，仅供娱乐
- 服务端由 [ServerPackCreator](https://github.com/Griefed/ServerPackCreator) 打包生成

## 许可协议

- 服务端整合包：**免费使用，禁止二次倒卖**
- 第三方模组：遵循各自原始 License
- 世界存档与配置文件：作者保留所有权利

---

**免责声明**：本服务端仅供学习与娱乐用途。使用前请确保已阅读 Mojang EULA 并遵守 Minecraft 最终用户许可协议。
