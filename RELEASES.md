# 不卡带 (Unwind) - 产品正式发布版本与更新记录 (Releases)

欢迎查阅「不卡带 (Unwind)」官方版本演进记录与安装包下载清单。本仓库为开源合规与产品正式交付公开仓。

- **官方在线产品发布与下载页**：https://beckmint.github.io/unwind-privacy-policy/releases.html
- **官方在线隐私保护政策页**：https://beckmint.github.io/unwind-privacy-policy/
- **开发者**：BeckMint（独立开发者）
- **适用平台**：Android 10+ / 专为 vivo X Flip 等纵向小折叠外屏深度定制

---

## 🌟 当前最新正式版：v0.7.7

- **安装包文件**：[`releases/Unwind-v0.7.7-release.apk`](releases/Unwind-v0.7.7-release.apk)
- **体积**：`4.69 MB`
- **发布日期**：`2026-10-23`
- **SHA-256 完整校验码**：`fb521242b0749ffe8c658898a54a1720a533252e851cc4b4d30bba6fd2408e20`

### 核心新特性与优化：
1. **5 重拟物声音滤镜与声画一体联动**：支持原音直通、磁带随身听、33转黑胶唱机、电子管广播、千禧随身光盘 5 大模式，轻触中央机芯视窗循环切换；伴随黑胶唱针微跳与温润爆豆、磁带双轴旋转消长与 Hiss 微噪、收音机 6E2 猫眼呼吸、光驱反光寻轨等多感官声画联动；支持 25% / 50% / 75% 滤镜强度随心微调；
2. **飞牛私有云 (fnOS / WebDAV) 远程无损直连**：点对点 WebDAV 高速串流家中私有云 NAS 海量无损母带，凭据交由 Android Keystore 底层硬件安全区 (TEE) 以 AES-256 GCM 硬件加密存储，零第三方中转，100% 数据掌控；
3. **小折叠 30°~60° 悬停案头伴听与 Auto-Dim 微光节能**：深度自适应 AMOLED 纯黑发光特性，静置自动进入微光低功耗走带，机身不发热、电量超长寿；支持防误触 HOLD 实体拨片开关；
4. **外屏本地视频播放与双击全屏**：自由载入本地个人视频文件，双击即刻切换全屏沉浸播放，合盖立放桌畔秒变私享小影院；
5. **16 段双通道高阻尼动态 VU 电平表与 7 档硬件级 DSP 纯音**：精准捕捉声波电平跳动，提供 MEGA BASS 澎湃低频增强、清澈人声等 7 档纯音预设。

---

## 📦 完整版本发布与历史记录汇总表

| 版本号 | 发布日期 | 安装包文件名 | 体积 | SHA-256 校验摘要 | 核心演进简述 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **v0.7.7** | 2026-10-23 | [`Unwind-v0.7.7-release.apk`](releases/Unwind-v0.7.7-release.apk) | 4.69 MB | `fb521242b0749ffe...` | 5 重拟物声音滤镜与声画一体联动，飞牛私有云 (fnOS / WebDAV) 远程无损直连，TEE AES-256 GCM 硬件密钥存储，Auto-Dim 微光伴听与双击全屏。 |
| **v0.7.6** | 2026-10-23 | [`Unwind-v0.7.6-release.apk`](releases/Unwind-v0.7.6-release.apk) | 4.69 MB | `f96e73d9dd922945...` | 升级 VintageAudioTextureEngine 音频纹理引擎，优化黑胶微跳爆豆与磁带 Hiss 底噪合成拟真度，提速 WebDAV 目录索引。 |
| **v0.7.5** | 2026-10-23 | [`Unwind-v0.7.5-release.apk`](releases/Unwind-v0.7.5-release.apk) | 4.69 MB | `69d2fdb09773d2cb...` | 针对 vivo X Flip 优化 30°~60° 悬停案头伴听视角，增强物理防误触锁 (HOLD)，降低 AMOLED 桌面微刷新功耗。 |
| **v0.7.4** | 2026-10-23 | [`Unwind-v0.7.4-release.apk`](releases/Unwind-v0.7.4-release.apk) | 4.69 MB | `c3d8704bc145900c...` | 优化 Media3 后台保活服务与蓝牙断连自动暂停，拦截物理音量在 LCD 呈现点阵音量条浮层。 |
| **v0.7.3** | 2026-10-23 | [`Unwind-v0.7.3-release.apk`](releases/Unwind-v0.7.3-release.apk) | 4.69 MB | `bda384272b22d041...` | 新增 Auto-Dim 微光定时器设置（15s / 30s / 60s），静置伴放更低温省电，调优线性马达触感震动反馈。 |
| **v0.7.2** | 2026-10-23 | [`Unwind-v0.7.2-release.apk`](releases/Unwind-v0.7.2-release.apk) | 4.69 MB | `79b72831ba51b62e...` | 增加声音滤镜强度档位调节（25% / 50% / 75%），优化中央机芯视窗触控区域判定。 |
| **v0.7.1** | 2026-10-23 | [`Unwind-v0.7.1-release.apk`](releases/Unwind-v0.7.1-release.apk) | 4.69 MB | `7d8ef18c11261dd9...` | 优化 WebDAV 弱网与高延迟环境下的重连与自适应流式缓冲，支持 FLAC / APE / WAV 预缓存。 |
| **v0.7.0** | 2026-10-23 | [`Unwind-v0.7.0-release.apk`](releases/Unwind-v0.7.0-release.apk) | 4.69 MB | `162ba102fa06b3ea...` | 产品全面更名为「不卡带 (Unwind)」，视觉全面升级索尼 Walkman 经典暖琥珀橙与 7 款复古点阵背光。 |
| **v0.6.9** | 2026-10-22 | [`Unwind-v0.6.9-release.apk`](releases/Unwind-v0.6.9-release.apk) | 4.66 MB | `acb49f678df0b717...` | 首次引入飞牛私有云 (fnOS) 远程直连与 WebDAV 协议，搭建 Android Keystore TEE 硬件级加密架构。 |
| **v0.6.8** | 2026-10-22 | [`Unwind-v0.6.8-release.apk`](releases/Unwind-v0.6.8-release.apk) | 4.65 MB | `d4a2a9cb67f6bbd3...` | 深度优化 Storage Access Framework (SAF) 批量扫描与多级子目录递归解析，强化中文 ID3v2 编码兼容。 |
| **v0.6.7** | 2026-10-22 | [`Unwind-v0.6.7-release.apk`](releases/Unwind-v0.6.7-release.apk) | 4.65 MB | `3142d16e9705a1c3...` | 新增本地个人视频文件导入与微型 CRT 扫描线小视窗伴放，支持双击一键全屏沉浸播放。 |
| **v0.6.6** | 2026-10-21 | [`Unwind-v0.6.6-release.apk`](releases/Unwind-v0.6.6-release.apk) | 3.73 MB | `3285554e378cd9a8...` | vivo X Flip 外屏原生魔镜应用适配首发版本，支持 682×422 黄金分辨率自适应与双轴拟物机械控制台。 |

---

## 📱 小折叠外屏（vivo X Flip 等）启用步骤
1. 下载最新安装包并完成安装；
2. 打开系统【设置】 > 【外屏专区】或【魔镜应用 / 外屏应用管理】；
3. 勾选「不卡带 (Unwind)」允许常驻外屏；
4. 合上翻盖，外屏左滑点开应用图标即可享受复古随身听仪式感！
