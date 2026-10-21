# 家豪的打枪

Minecraft Java **1.21.1**，Fabric Loader **0.19.5**。核心玩法是 **Point Blank** 的现代枪械，再加上飞机、新地形和一套性能模组。

原来的本地包名叫 Adrenaline，作者署名 `cjk123`。这一份把它整理成 Modrinth 的 `.mrpack`。

## 安装

1. 用 Modrinth App 或 Prism Launcher 导入 [`dist/家豪的打枪-1.0.0.mrpack`](dist/家豪的打枪-1.0.0.mrpack)。
2. 启动器按文件哈希从 Modrinth 下载 82 个模组。包里只有配置和视频选项，没有模组 JAR。
3. 语言已设为简体中文。
4. 游戏本体用 Minecraft Launcher 和 Microsoft 账号。这个包不带游戏客户端。

## 还要自己放进 `mods/` 的 6 个文件

这 6 个 JAR 的许可证不允许再分发，Modrinth 上也没有同一个文件。请到作者的发布页下载与原来相同的版本，放进实例的 `mods/` 目录。不要用来路不明的转载站。

| 文件 | 作用 | 发布页 |
| --- | --- | --- |
| `cupboard-fabric-1.21.1-4.2.jar` | Chunk Sending 的依赖库 | [CurseForge · Cupboard](https://www.curseforge.com/minecraft/mc-mods/cupboard) |
| `chunksending-fabric-1.21-3.9.jar` | 区块发包优化 | [CurseForge · Chunk Sending](https://www.curseforge.com/minecraft/mc-mods/chunk-sending-forge-fabric) |
| `gpumemleakfix-fabric-1.21-1.8.jar` | 客户端显存泄漏修复 | [CurseForge · fix GPU memory leak](https://www.curseforge.com/minecraft/mc-mods/fix-gpu-memory-leak) |
| `geogradient-1.0.3-1.21.1-FABRIC.jar` | 按纬度分气候带 | [CurseForge · GeoGradient](https://www.curseforge.com/minecraft/mc-mods/geogradient) |
| `hassium-fabric-2.0.1-1.21.1.jar` | 区块压缩与客户端缓存 | [GitHub · limuqy/hassium](https://github.com/limuqy/hassium) |
| `skylance-fabric-1.21.1-0.1.0.jar` | 空中支援瞄准 | [CurseForge · SkyLance](https://www.curseforge.com/minecraft/mc-mods/skylance) |

缺这 6 个时，游戏仍然能进。缺的是对应功能，不是 Fabric 本身。

## 原来被关掉的模组

`overrides/mods/` 里带 `.disabled` 的文件没有打进包。其中包括 Nvidium、Dynamic Surroundings、Guard Villagers、Just Enough Guns、Verdant，以及 Immersive Aircraft 的 1.5.0 和 1.5.2。当前启用的飞机模组是 **1.4.6**。

## 目录

- `dist/家豪的打枪-1.0.0.mrpack`：给启动器导入的包。
- `pack/modrinth.index.json`：Modrinth 索引，82 个文件都指向 `cdn.modrinth.com`。
- `pack/modrinth-catalog.json`：模组 id、slug 和下载地址，方便核对。
- `overrides/`：原来的配置。存档、崩溃缓存和模组 JAR 不进入 git。
