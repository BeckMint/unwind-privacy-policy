# 不卡带 (Unwind) 复古随身听 - 开放主题规范与 AI 提示词指南 (v1.0.0)

[English Version](THEME_SPEC.md) | **简体中文**

> **开源协议**：MIT License — 100% 个人与商业免费商用。  
> 致敬 1997 年传奇的 Winamp 皮肤换肤浪潮。专为折叠屏手机外屏、智能副屏以及全球复古硬件音频爱好者打造。

---

## 1. 概述与设计愿景

1997 年，Winamp 凭借完全开放的社区皮肤（Skins）体系革新了个人数字音频软件，赋予全球音乐爱好者对播放器视觉、交互手感与硬件灵魂的绝对自由主权。

**「不卡带 (Unwind)」** 将这份自由定制与拟物硬件的精神带入当今智能手机与折叠屏时代（已深度适配 Moto Razr 50 Ultra、vivo X Flip、Galaxy Z Flip、荣耀 Magic V Flip、小米 MIX Flip 等外屏，以及通用直板手机与内屏全屏体验）。

在 Unwind 中，每一套主题都是一份高度解耦、强类型的声明式规范（`UnwindSkinSpec`）。你可以深度定制：
- **点阵液晶屏 LCD 配色**（高亮激活像素、未点亮鬼影矩阵底色、背光透光腔体）；
- **物理机身材质质感**（阳极氧化铝合金、拉丝钛金属、冷轧枪色金属、复古暖调工程塑料、黑铬等）；
- **立体琴键与按键螺丝**（CNC 镜面微倒角、切角暗影、顶置光源立体受光与下沉行程）；
- **外屏物理双摄波轮 / 旋钮电位器**（刻度盘指示辉光、旋转指针宝石、震动与灵敏度步进）；
- **全机型多形态屏幕自适应**（1:1 正方形外屏、纵向异形外屏、超大挖孔外屏以及通用大内屏）。

---

## 2. 双重受众架构：专为人类与 AI 助手协同设计

本规范在架构之初即专门面向 **两大受众** 进行了工程级设计：

1. **👨‍💻 人类设计师与开发者**：清晰查阅 Schema 属性定义、微调十六进制 HEX 颜色值、并将其直接集成进播放器工程中；
2. **🤖 AI 编程助手（Claude, ChatGPT, Gemini, Cursor）**：内置零样本标准 Prompt 模板。任何没有编程基础的用户，只需对 AI 输入一句话硬件概念，AI 即可在数秒内自动推导并生成完全符合规格的代码与配置！

---

## 3. 主题声明式数据规范 (Theme Specification Schema)

在代码底层，Unwind 主题通过强类型契约 `UnwindSkinSpec` 声明并序列化：

### 3.1 JSON 架构 (JSON Schema)

```json
{
  "$schema": "https://unwind.beckmint.com/schemas/theme-v1.json",
  "id": "theme_identifier",
  "name": "DISPLAY NAME",
  "author": "Your Name / 开发者署名",
  "license": "MIT",
  "description": "设计理念与历史复古硬件灵感简述",
  "screenTarget": "AUTO",
  "colors": {
    "lcdPrimary": "#FFAA00",
    "lcdDim": "#281C06",
    "lcdBg": "#050402",
    "isLightBg": false,
    "hardwareAccent": "#FFAA00"
  },
  "chassis": {
    "chassisBg": "#0A0D10",
    "chassisBorder": "#323842",
    "chassisHighlight": "#4C5566",
    "chassisShadow": "#101318"
  },
  "controls": {
    "buttonIdleTop": "#565F73",
    "buttonIdleBottom": "#2A2F3B",
    "buttonBorder": "#8C97B0",
    "isWinampStyle": false
  }
}
```

### 3.2 详细属性说明与工业设计准则

| 属性字段 | 数据类型 | 说明与职责 | 工业设计法则与最佳实践 |
| :--- | :--- | :--- | :--- |
| `id` | `String` | 主题唯一全局标识符 | 全小写字母、数字与下划线，如 `cyberpunk_neon` |
| `name` | `String` | 面向用户的点阵屏显示名称 | 建议大写，长度 ≤ 12 个英文字符以保证点阵居中 |
| `author` | `String` | 作者昵称 / 团队 Handle | 支持署名、社交账号或开源组织名 |
| `license` | `String` | 授权协议标识 | 统一为 `MIT` 协议（保证社区完全自由分发） |
| `description` | `String` | 主题设计概念与硬件原型简述 | 1~2 句话说明复古灵感与声学硬件来源 |
| `screenTarget`| `String` | 屏幕适配倾向 | 默认为 `AUTO`（自动适配外屏与内屏） |
| `lcdPrimary` | `Hex Color` | 激活点阵文字、VU 表动态跃动条 | 高饱和主色，与 `lcdBg` 对比度必须 **> 7:1** |
| `lcdDim` | `Hex Color` | 未点亮鬼影像素 (Ghost Matrix) | 极弱微光，与 `lcdBg` 形成真实物理反光层 (**< 2:1**) |
| `lcdBg` | `Hex Color` | 点阵腔体暗箱底色 | 暗色液晶一般在 `#000000` 到 `#0A100D`；冷光板为浅青绿 |
| `isLightBg` | `Boolean` | 是否为浅色冷光屏（如 GameBoy/电子管）| 若为 `true`，系统自动将文字反相为深色高对比墨水点阵 |
| `hardwareAccent`| `Hex Color` | 双摄镜头刻度环、按键边缘与状态 LED | 机械电位器点缀色，通常与 `lcdPrimary` 同色或撞色 |
| `chassisBg` | `Hex Color` | 随身听铝合金/碳纤维机身主底色 | 决定机身的冷暖倾向与金属阳极氧化质感 |
| `chassisBorder`| `Hex Color` | 机身外边框微凸高光反光边缘 | 比 `chassisBg` 稍明亮，营造 CNC 精雕边缘光泽 |
| `buttonIdleTop` | `Hex Color` | 3D 拟物琴键按键上表面渐变高光点 | 模拟顶部 45° 顶置光源斜射下的受光面 |
| `buttonIdleBottom`| `Hex Color` | 3D 拟物琴键按键下表面渐变暗部 | 通常比 `buttonIdleTop` 深 **20%~30%**，形成立体倒角 |
| `buttonBorder` | `Hex Color` | 琴键按键外边缘倒角或发光描边 | 金属切削高光；在赛博朋克主题下可为荧光描边 |
| `isWinampStyle`| `Boolean` | 是否开启 1997 黄金年代双卡座机柜样式 | `true` 时采用 Winamp 极具仪式感的微圆角机柜排版 |
| `chassisImage` | `String` | 可选机身贴图静态资源（相对文件名） | 如 `"chassis.png"`, `"background.webp"`，将自适应铺满机体底盘 |

### 3.3 主题包打包格式 (.zip / .unwindskin)

除了单独的 `theme.json`，主题包支持组合静态图片贴图等资源打包为一个标准的 `.zip`（或 `.unwindskin`）压缩包：

```text
my_theme.zip
├── theme.json           # 核心声明式主题配置文件 (必选)
├── chassis.png          # 自定义机身贴图 / 阳极氧化拉丝 / 锻造碳纹理 (可选)
└── preview.png          # 主题预览截图 (可选)
```

- **静态图片自动识别**：如果在 `theme.json` 的 `chassis` 中指定了 `chassisImage: "chassis.png"`，系统将优先加载指定文件；若未指定，系统会自动检测包内是否存在 `chassis.png`、`chassis.webp`、`background.png` 等标准命名的贴图并自动应用。

### 3.4 导入、应用与删除交互指南

1. **一键导入与自动应用 (OPEN)**：
   - 打开应用，点击 **OPEN**（文件与目录浏览器，支持手机本机存储与 WebDAV 远程曲库）；
   - 找到您的主题包（显示为 `🎨 [主题包名].zip` 并带有 `🎨 导入主题` 标识），点击即可；
   - 应用将在内部安全解压，**自动立即应用到当前界面**，并将新主题加入系统主题选择列表！
2. **长按删除与重置保护 (SETTINGS)**：
   - 点击 **SET** 进入设置页的「复古随身主题」栏目；
   - **长按**任意新添加的自定义主题，系统将进入主题编辑删除模式：**所有新加入的自定义主题右上角均会出现红色 `✕` 按钮**（系统自带的主题绝对不会显示 `✕`，避免误删）；
   - 点击自定义主题右上角的 `✕` 按钮，弹出确认提示框；
   - 点击**确认删除**后，应用将彻底清除该主题解压的全部静态文件，并**安全恢复至系统默认自带配色（琥珀橙）**。

---

## 4. 🤖 AI 提示词指南 (如何使用 AI 秒级生成主题)

无需手动查找色号！直接复制以下模板，将其粘贴到 **Claude (推荐 3.5 Sonnet)、ChatGPT (GPT-4o)、Gemini 或 Cursor** 中即可：

### 复制给 AI 的标准提示词模板：

````markdown
你是一名专精于工业设计、复古拟物音频硬件（Skeuomorphic Audio Hardware）以及现代折叠屏界面美学的资深设计师。
请基于以下概念，为开源播放器 "Unwind (不卡带)" 生成一套完全合规的主题规范：

【设计概念】：[在此替换为您想要的概念，例如："Cyberpunk 2077 夜之城高压荧光", "1968 年迪特·拉姆斯 Braun 极简包豪斯", "1980 年代迈阿密霓虹蒸汽波", 或 "1979 年索尼初代 Walkman TPS-L2 蓝金限定版"]

输出必须严格遵循 Unwind Theme Specification (v1.0.0)。

请严格按照以下格式输出：
1. 设计灵感简述与对应的经典音频硬件原型（2-3 句话）。
2. 符合 Schema 的完整 JSON 配置代码块：
```json
{
  "id": "theme_identifier",
  "name": "DISPLAY NAME",
  "author": "Your Name",
  "license": "MIT",
  "description": "...",
  "screenTarget": "AUTO",
  "colors": {
    "lcdPrimary": "#...",
    "lcdDim": "#...",
    "lcdBg": "#...",
    "isLightBg": false,
    "hardwareAccent": "#..."
  },
  "chassis": {
    "chassisBg": "#...",
    "chassisBorder": "#...",
    "chassisHighlight": "#...",
    "chassisShadow": "#..."
  },
  "controls": {
    "buttonIdleTop": "#...",
    "buttonIdleBottom": "#...",
    "buttonBorder": "#...",
    "isWinampStyle": false
  }
}
```
3. 可直接加入 RetroTheme.kt 的 Kotlin DSL 声明代码片段。
````

---

## 5. 官方典范主题 (Showcase Reference Themes)

以下提供 3 套已通过真机验证的开箱即用典范主题：

### 典范 1: Cyberpunk 2077 夜之城 (高压荧光青 + 烈焰霓虹粉 + 锻造碳机身)
```json
{
  "id": "cyberpunk_neon",
  "name": "CYBERPUNK",
  "author": "NightCity Audio",
  "license": "MIT",
  "description": "高压荧光青激光点阵显示屏，搭配黑色锻造碳纤维机体与烈焰霓虹粉镜头旋钮",
  "screenTarget": "AUTO",
  "colors": {
    "lcdPrimary": "#00FFCC",
    "lcdDim": "#00332B",
    "lcdBg": "#030807",
    "isLightBg": false,
    "hardwareAccent": "#FF007F"
  },
  "chassis": {
    "chassisBg": "#0D1117",
    "chassisBorder": "#1E2633",
    "chassisHighlight": "#00FFCC",
    "chassisShadow": "#05070A"
  },
  "controls": {
    "buttonIdleTop": "#263040",
    "buttonIdleBottom": "#141922",
    "buttonBorder": "#FF007F",
    "isWinampStyle": false
  }
}
```

### 典范 2: Braun 1968 迪特·拉姆斯极简包豪斯 (暖调象牙白 + 德国工业安全橙)
```json
{
  "id": "braun_1968",
  "name": "BRAUN 1968",
  "author": "Bauhaus Lab",
  "license": "MIT",
  "description": "迪特·拉姆斯功能主义极简机身，暖象牙白哑光质感与经典的德国工业安全橙指示",
  "screenTarget": "AUTO",
  "colors": {
    "lcdPrimary": "#1A1A1A",
    "lcdDim": "#C8C4B8",
    "lcdBg": "#E8E4DA",
    "isLightBg": true,
    "hardwareAccent": "#FF5500"
  },
  "chassis": {
    "chassisBg": "#DCD8CC",
    "chassisBorder": "#EDEAE2",
    "chassisHighlight": "#FFFFFF",
    "chassisShadow": "#B8B4A6"
  },
  "controls": {
    "buttonIdleTop": "#EFECE4",
    "buttonIdleBottom": "#D0CCC2",
    "buttonBorder": "#FF5500",
    "isWinampStyle": false
  }
}
```

### 典范 3: Sony Walkman TPS-L2 1979 初代传奇 (金属深海蓝 + 香槟银拉丝实体键)
```json
{
  "id": "walkman_1979",
  "name": "TPS-L2 1979",
  "author": "Tokyo Sound",
  "license": "MIT",
  "description": "致敬 1979 年索尼初代随身听经典金属深海蓝机身，香槟银实体按键与暖橙热键",
  "screenTarget": "AUTO",
  "colors": {
    "lcdPrimary": "#00E1D9",
    "lcdDim": "#072928",
    "lcdBg": "#020B0B",
    "isLightBg": false,
    "hardwareAccent": "#FF6B00"
  },
  "chassis": {
    "chassisBg": "#1E3B68",
    "chassisBorder": "#4A6E9E",
    "chassisHighlight": "#7B9ECB",
    "chassisShadow": "#0E1F38"
  },
  "controls": {
    "buttonIdleTop": "#C8D1DC",
    "buttonIdleBottom": "#8A97A8",
    "buttonBorder": "#DDE4ED",
    "isWinampStyle": false
  }
}
```

---

## 6. 商业权益与社区贡献 (Contributing & Commercial Rights)

1. **100% 免费商业使用**：遵循 MIT 开源许可协议，您可以自由地将基于本规范创建的主题打包、分发、用于商业产品或作为独立附加组件销售，无需支付任何专利版权费，亦无需取得预先书面许可；
2. **提交至官方版本曲库 (Pull Request)**：非常欢迎全球开发者与设计爱好者将自己制作的主题贡献至主仓库！只需在 GitHub 提交包含主题 JSON 与外屏运行效果截图的 PR，审核通过后将直接合并入「不卡带 (Unwind)」正式版官方主题库中。
