# 家豪的打枪

Minecraft Java **1.21.1**，Fabric Loader **0.19.5** 的整合包。GitHub 仓库名是英文 [`jiahao-guns`](https://github.com/yywill/jiahao-guns)。游戏里的名字是「家豪的打枪」。

原来的本地包叫 Adrenaline，作者署名 `cjk123`。它不是单独一个枪械模组，而是一整包：

- **打枪：** Point Blank，现代枪械。SkyLance 是空中打击，要另外从作者页面安装。
- **飞机：** Immersive Aircraft 1.4.6，加上 Do a Barrel Roll、Flight Assistant。
- **地形和建筑：** Regions Unexplored、Profundis、Galosphere、YUNG 的几种结构、村庄翻新等。
- **性能：** Sodium、Lithium、FerriteCore、ModernFix、ImmediatelyFast、C2ME 等。

语言已经设成简体中文。

## 我们做了什么

本地原来是一份 MCBBS 整合包：88 个正在用的模组 JAR 直接放在 `overrides/mods/` 里，大约 204 MB。另外 11 个文件带 `.disabled`，是小朋友关掉的，没有打进这个包。

处理步骤：

1. 读出每个启用 JAR 里的模组 id 和版本，并计算 SHA1、SHA512。
2. 用 SHA1 到 Modrinth 上对文件。88 个里有 **82 个是站上的同一个 JAR**。
3. 写成 Modrinth 的 `.mrpack`：`dist/家豪的打枪-1.0.0.mrpack`。索引在 `pack/modrinth.index.json`。
4. 包里只带配置、按键和视频选项。启动器导入后，自己去 Modrinth 下载那 82 个模组。
5. 存档、玩家数据、崩溃缓存和本机用户名没有放进仓库。

还有 6 个 JAR 在 Modrinth 上没有同一个文件，许可证也不允许我们代为上传。名字和作者页面在下面。

## 为什么用哈希，不放 JAR

这些 JAR 是别人的模组，许可证各不相同。把文件再传到这个仓库，等于替作者公开分发一次。CurseForge 上有几个还明确写了只在他们那里发布。

Modrinth 的整合包格式也不把 JAR 塞进压缩包。`modrinth.index.json` 里每条只记四样东西：

- 装到哪个路径，例如 `mods/sodium-fabric-0.8.13+mc1.21.1.jar`
- SHA1 和 SHA512
- 官方下载地址，这里是 `cdn.modrinth.com`
- 这个模组要装在客户端、服务端，还是两边都要

启动器按地址下载，下载完再算一遍哈希。和索引里的值一致，才放进 `mods/`。这样装到的文件就是原来那一份，不是同名的另一个版本。

所以这个仓库大约一百多 KB。游戏本体也不在里面，用 Minecraft Launcher 和 Microsoft 账号。

## 安装

1. 用 Modrinth App 或 Prism Launcher 导入 [`dist/家豪的打枪-1.0.0.mrpack`](dist/家豪的打枪-1.0.0.mrpack)。
2. 等它下完 82 个模组。
3. 按下一节补上剩下的 6 个文件。

## 要自己放进 `mods/` 的 6 个文件

请到作者的发布页下载与下表相同的版本。不要用来路不明的转载站。

| 文件 | 作用 | 发布页 |
| --- | --- | --- |
| `cupboard-fabric-1.21.1-4.2.jar` | Chunk Sending 的依赖库 | [CurseForge · Cupboard](https://www.curseforge.com/minecraft/mc-mods/cupboard) |
| `chunksending-fabric-1.21-3.9.jar` | 区块发包优化 | [CurseForge · Chunk Sending](https://www.curseforge.com/minecraft/mc-mods/chunk-sending-forge-fabric) |
| `gpumemleakfix-fabric-1.21-1.8.jar` | 客户端显存泄漏修复 | [CurseForge · fix GPU memory leak](https://www.curseforge.com/minecraft/mc-mods/fix-gpu-memory-leak) |
| `geogradient-1.0.3-1.21.1-FABRIC.jar` | 按纬度分气候带 | [CurseForge · GeoGradient](https://www.curseforge.com/minecraft/mc-mods/geogradient) |
| `hassium-fabric-2.0.1-1.21.1.jar` | 区块压缩与客户端缓存 | [GitHub · limuqy/hassium](https://github.com/limuqy/hassium) |
| `skylance-fabric-1.21.1-0.1.0.jar` | 空中支援瞄准 | [CurseForge · SkyLance](https://www.curseforge.com/minecraft/mc-mods/skylance) |

缺这 6 个时游戏仍然能进，只是少对应功能。

## 原来被关掉的模组

`overrides/mods/` 里带 `.disabled` 的文件没有打进包。其中包括 Nvidium、Dynamic Surroundings、Guard Villagers、Just Enough Guns、Verdant，以及 Immersive Aircraft 的 1.5.0 和 1.5.2。当前启用的飞机模组是 **1.4.6**。

## 目录

- `dist/家豪的打枪-1.0.0.mrpack`：给启动器导入的包。
- `pack/modrinth.index.json`：82 个模组的路径、哈希和下载地址。
- `pack/modrinth-catalog.json`：模组 id 和 Modrinth 项目 slug，方便核对。
- `overrides/`：原来的配置。存档、崩溃缓存和模组 JAR 不进入 git。
