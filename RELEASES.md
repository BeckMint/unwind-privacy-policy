# 不卡带 (Unwind) - 产品正式发布版本与更新记录 (Releases)

欢迎查阅「不卡带 (Unwind)」官方版本演进记录与安装包下载清单。本仓库为开源合规与产品正式交付公开仓。

- **官方在线产品发布与下载页**：https://beckmint.github.io/unwind-privacy-policy/releases.html
- **官方开源主题与AI生成指南 (在线网页)**：https://beckmint.github.io/unwind-privacy-policy/theme-spec.html
- **官方开源主题规范文档 (GitHub)**：[🇨🇳 简体中文](THEME_SPEC_CN.md) | [🇬🇧 English](THEME_SPEC.md)
- **官方在线隐私保护政策页**：https://beckmint.github.io/unwind-privacy-policy/
- **开发者**：BeckMint（独立开发者）
- **适用平台**：Android 10+ / 专为纵向小折叠手机（vivo X Flip 和 moto razr 50 ultra）外屏及通用内屏打造

---

## 🌟 当前最新正式版：v1.0.0

- **安装包文件**：[`releases/Unwind-v1.0.0-release.apk`](releases/Unwind-v1.0.0-release.apk)
- **体积**：`6.07 MB`
- **发布日期**：`2026-10-26`
- **SHA-256 完整校验码**：`ec338a93997b50dea795085f891013bd5ede3e410661ae732aaf1baadc1a9379`

### 核心新特性与优化：
1. **现代化架构演进（Kotlin 2.0.21 + Compose Compiler Plugin）**：彻底对齐 Google 最新 Modern Android Development (MAD) 官方指南，编译器升级至 Kotlin 2.0.21，采用第一方 Compose Compiler Gradle 插件，清理冗余无用库依赖与 300 余行调试废代码，全工程 100% 纯 Kotlin 现代化声明式架构；
2. **静态音频与图标深度重采样（包体积立减 20%，内存削减 50%）**：将内置的 11 套复古音效（4 款收音机扫频 + 7 套真实黑胶落针）重采样为 22,050 Hz 16-bit 单声道 PCM WAV，彻底消除高频冗余带宽。安装包体积由 7.7MB 直降至 6.07MB，开机 JVM 堆内存常驻占用立省 1.5MB（削减 50%），兼具 0 延迟即刻出声与极致轻量化；启动图标转为无损高压缩 WebP（减少 88%）；
3. **外屏双摄旋钮「镜头几何圆心运动学」算法重构**：彻底重构双摄旋钮触控算法，严格以手机物理镜头中心为极坐标基准。两指环绕旋转时角位移平滑均值累加，消除参考系跳动与两指间距缩放误触；音量波轮步进阈值优化至 6.8°，旋转灵敏度提升 100%，细腻跟手；
4. **4 套 CC0 收音机起始音效与智能播放规则**：精选 4 套 Freesound 经典搜台扫频音（全量 CC0 1.0 Universal 免责免版权），在 2.5~4.0 秒平滑淡出并联动滤镜音量；新设智能触发规则：仅在载入全新播放列表或播放新追加的首曲时触发，常规连续切歌不打扰；
5. **远程媒体库通用化升级（支持所有标准 WebDAV）**：全面通用化适配飞牛私有云 (fnOS)、群晖 Synology、威联通 QNAP、极空间、坚果云、AList 等私有云与网盘，实现点对点无损串流；
6. **重磅开源：Unwind Theme Open Specification (v1.0.0，MIT 协议)**：传承 Winamp 1997 经典皮肤自由定制精神，将主题体系彻底开源解耦，遵循 MIT 免费商用协议。发布专为人类与 AI 双向设计的全套规范文档（THEME_SPEC.md），内置标准化 AI 提示词模板，支持用户直接借助 Claude / ChatGPT / Gemini / Cursor 一秒自动生成符合规范的复古外屏主题。

---

## 📦 完整版本发布与历史记录汇总表

| 版本号 | 发布日期 | 安装包文件名 | 体积 | SHA-256 校验摘要 | 核心演进简述 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **v1.0.0** | 2026-10-26 | [`Unwind-v1.0.0-release.apk`](releases/Unwind-v1.0.0-release.apk) | 6.07 MB | `ec338a93997b50de...` | 里程碑正式版：底层全面迁移至官方最新 Kotlin 2.0.21 与 Compose Compiler 引擎；深度优化静态资源，APK 体积立减 20%（7.7MB ➔ 6.07MB），运行时常驻内存节省 50%；外屏双摄波轮重构为物理镜头几何圆心极坐标算法，灵敏度提升 100%；新增 4 套 CC0 收音机扫频起始音与智能首曲播放机制；远程媒体库通用化适配所有标准 WebDAV；重磅开源 Unwind Theme Open Specification (MIT 协议)，附赠专为 AI 设计的提示词模板。 |
| **v0.8.11** | 2026-10-26 | [`Unwind-v0.8.11-release.apk`](releases/Unwind-v0.8.11-release.apk) | 6.34 MB | `59b9668375ed6aa1...` | Moto Razr 50 Ultra 双摄物理旋钮精准坐标永久固定（左: 327dp / 右: 431dp / 高度: 75.5dp）；引入 Freesound 评级前七套 CC0 真实黑胶落针声学采样池，起播随机触发并严格遵循声音滤镜音量联动规则；重构黑胶连续播放动态随机爆擦音与 33 1/3 RPM 转盘偏心声场。 |
| **v0.8.10** | 2026-10-25 | [`Unwind-v0.8.10-release.apk`](releases/Unwind-v0.8.10-release.apk) | 4.78 MB | `94d777f644e86f5d...` | 重磅推出「外屏双摄旋钮真机物理实时校准工具」，长按底栏或在设置页即可一边看着物理镜头一边点按微调（支持红绿准星与 0.5dp/2dp 步进），永久保存且刻度与文字实时联动；全面重构真实黑胶落针声学，消除啪声爆音，呈现柔和低沉的阻尼触感与温润槽音；旋钮触控升级支持单指滑动与双指捏转双重模式。 |
| **v0.8.9** | 2026-10-25 | [`Unwind-v0.8.9-release.apk`](releases/Unwind-v0.8.9-release.apk) | 4.77 MB | `07a997235826c8dd...` | 精确复原 moto razr 50 ultra 双摄旋钮物理开孔基准坐标（318dp / 423dp），修复音量旋钮旋转响应；重构物理真实黑胶落针声学消除电子音；新增 ID3 标签主动预读与持久化缓存，导入歌曲即刻秒显歌手与曲目。 |
| **v0.8.8** | 2026-10-25 | [`Unwind-v0.8.8-release.apk`](releases/Unwind-v0.8.8-release.apk) | 4.77 MB | `7faef8252c8a4387...` | 修复 moto razr 50 ultra 双摄旋钮刻度圆圈同轴对齐，左旋钮刻字升级为完整英文 EQUALIZER；彻底规范播放列表歌名显示规则，智能剥离专辑音轨序号并过滤远程 NAS 标签。 |
| **v0.8.7** | 2026-10-25 | [`Unwind-v0.8.7-release.apk`](releases/Unwind-v0.8.7-release.apk) | 4.75 MB | `4a19d319c7e7d087...` | 新增 moto razr 50 ultra 外屏双摄物理旋钮（重音/音量双指防误触旋转电位器）；新增 MD (MiniDisc 磁光随身听) 复古声音滤镜与 40 秒抗震内存 (ESP) 律动；重构黑胶唱片 (Vinyl) 落针仪式声学并消除切滤镜杂音；优化 CD 裸盘光驱连续运转质感；解耦 EQ 音效与硬件滤镜；全量适配 vivo X Flip 与 moto razr 50 ultra 双折叠外屏。 |
| **v0.8.5** | 2026-10-24 | [`Unwind-v0.8.5-release.apk`](releases/Unwind-v0.8.5-release.apk) | 4.75 MB | `949604946189d37c...` | moto razr 50 ultra 外屏 OPEN 目录与 SET 设置视窗完整避让双摄镜头底栏；OPEN 目录返回上一级（UP ⬆）滚动记忆重构；PLAYLIST 抽屉新增 CLEAR 一键清空播放列表并解除删除规则限制。 |
| **v0.8.4** | 2026-10-24 | [`Unwind-v0.8.4-release.apk`](releases/Unwind-v0.8.4-release.apk) | 4.73 MB | `2b5b82264f6fb2d6...` | 全面适配 moto razr 50 ultra 与 vivo X Flip 双机型外屏；Winamp 拟物 UI 黄金排版重构与基线等高对齐（34dp）、复古 3-4dp 倒角；拟物磁带双对称齿轮与磁带走带物理重构；原音直通声波缩放防贴边；收音机响度与滤镜纯净度提升。 |
| **v0.7.7** | 2026-10-23 | [`Unwind-v0.7.7-release.apk`](releases/Unwind-v0.7.7-release.apk) | 4.69 MB | `fb521242b0749ffe...` | 5 重拟物声音滤镜与声画一体联动，飞牛私有云 (fnOS / WebDAV) 远程无损直连，TEE AES-256 GCM 硬件密钥存储，Auto-Dim 微光伴听与双击全屏。 |
| **v0.7.6** | 2026-10-23 | [`Unwind-v0.7.6-release.apk`](releases/Unwind-v0.7.6-release.apk) | 4.69 MB | `f96e73d9dd922945...` | 升级 VintageAudioTextureEngine 音频纹理引擎，优化黑胶微跳爆豆与磁带 Hiss 底噪合成拟真度，提速 WebDAV 目录索引与硬件安全凭证管理。 |

---

## 📱 纵向小折叠外屏安装与使用指南

### 🔹 moto razr 50 ultra（4.0 英寸超大外屏）专属设置：
1. 下载最新安装包并完成安装；
2. 进入手机系统【设置】 > 【外屏】 > 【外屏应用】（或在桌面外屏卡片管理中）；
3. 在应用列表中勾选「不卡带 (Unwind)」允许在外屏显示与运行；
4. 长按应用卡片或在设置中选择「全屏显示 (Full Screen)」模式，使应用自适应覆盖整块 4.0 英寸大外屏；
5. 合盖后点亮外屏，点击「不卡带」图标即可启动。专属 Winamp 拟物双卡座、全量居中弹窗视窗（设置、目录、播放列表等）完美避让左下角双摄镜头，沉浸享受复古走带与无损音质！

### 🔹 vivo X Flip（外屏魔镜）启用步骤：
1. 下载最新安装包并完成安装；
2. 打开系统【设置】 > 【外屏专区】或【魔镜应用 / 外屏应用管理】；
3. 在应用列表中找到「不卡带 (Unwind)」并勾选开启允许在外屏显示；
4. 合上手机翻盖，点亮外屏向左滑动至应用列表，点击「不卡带」图标即可开始沉浸播放！（长按可拖动至外屏首位，合盖双击秒开秒听）。
