# Unwind Retro Player - Open Theme Specification & AI Prompting Guide (v1.0.0)

**English** | [简体中文 (Chinese Version)](THEME_SPEC_CN.md)

> **License**: MIT License — 100% Free for Personal & Commercial Use.  
> Inspired by the legendary 1997 Winamp Skinning Movement. Dedicated to foldable outer-screens, smart cover displays, and retro hardware audio enthusiasts worldwide.

---

## 1. Overview & Vision

In 1997, Winamp revolutionized personal audio software by giving users complete freedom over the look, feel, and soul of their media players through community skins. 

**Unwind (不卡带)** brings that same spirit of creative sovereignty to modern smartphones and foldable cover displays (Moto Razr 50 Ultra, vivo X Flip, Galaxy Z Flip, Honor Magic V Flip, Xiaomi Mix Flip, and standard inner screens).

Every theme in Unwind is an open, declarative specification. You can customize:
- **LCD Dot-Matrix Color Schemes** (Active pixels, inactive ghost matrix, backlight illumination);
- **Physical Chassis Materials** (Brushed titanium, anodized aluminium, gunmetal, warm plastic, dark chrome);
- **Tactile Keycaps & Screws** (CNC specular bevels, chamfers, pressed state travel);
- **Rotary Camera Wave Wheels** (Tick dial illumination, rotating indicator jewels, sensitivity);
- **Screen Form Factor Adaptations** (1:1 square outer screen, tall cover screens, full inner screens).

---

## 2. Dual Audience: Designed for Humans & AI Assistants

This specification is explicitly engineered for **two audiences**:
1. **Designers & Developers**: Read the schema, tweak hex codes, and drop them into the player.
2. **AI Coding Assistants (Claude, Gemini, ChatGPT, Cursor)**: Contains a zero-shot prompting template so anyone can ask an AI to generate a complete, working theme in seconds!

---

## 3. Theme Specification Schema

An Unwind Theme is defined as a declarative `UnwindSkinSpec`:

### 3.1 JSON Schema

```json
{
  "$schema": "https://unwind.beckmint.com/schemas/theme-v1.json",
  "id": "theme_identifier",
  "name": "Display Name",
  "author": "Your Name / Handle",
  "license": "MIT",
  "description": "Short summary of the hardware inspiration",
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

### 3.2 Property Breakdown

| Property | Type | Description | Design Rule |
| :--- | :--- | :--- | :--- |
| `id` | `String` | Unique lowercase identifier (e.g. `cyberpunk_2077`) | lowercase letters, numbers, underscores |
| `name` | `String` | User-facing display title | Max 12 characters for LCD readability |
| `lcdPrimary` | `Hex Color` | Main active font, active VU bars, tick highlights | Must have high contrast with `lcdBg` (> 7:1) |
| `lcdDim` | `Hex Color` | Inactive dot-matrix pixels ("ghost pixels") | Low-contrast relative to `lcdBg` (< 2:1) |
| `lcdBg` | `Hex Color` | Backlight cavity base color | `#000000` to `#0A100D` for dark; `#98B828` for EL |
| `isLightBg` | `Boolean` | True if the entire screen glows like an EL panel | Inverts text contrast automatically |
| `hardwareAccent` | `Hex Color` | Rotary camera dials, screws, LED jewels | Usually matches or complements `lcdPrimary` |
| `chassisBg` | `Hex Color` | Anodized brushed metal body tone | Base midtone of the physical deck |
| `chassisBorder` | `Hex Color` | CNC specular rim highlight | Lighter than `chassisBg` for metallic shine |
| `buttonIdleTop` | `Hex Color` | 3D piano keycap upper face gradient stop | Gives top-down lighting perspective |
| `buttonIdleBottom`| `Hex Color` | 3D piano keycap lower face gradient stop | Darker than upper face by 20~30% |
| `buttonBorder`    | `Hex Color` | Piano key specular bevel or glow rim     | Metallic chamfer or neon outline |
| `chassisImage`    | `String`    | Optional relative texture path           | e.g. `"chassis.png"`, `"background.webp"` |

### 3.3 Theme Bundle Packaging Format (.zip / .unwindskin)

In addition to standalone JSON, Unwind supports complete theme bundles containing static images packaged as a standard `.zip` (or `.unwindskin`) archive:

```text
my_theme.zip
├── theme.json           # Declarative specification contract (Required)
├── chassis.png          # Custom hardware texture / brushed carbon / skin (Optional)
└── preview.png          # Skin preview image (Optional)
```

- **Automatic Image Detection**: If `chassisImage: "chassis.png"` is declared in `theme.json`, that specific asset is loaded. If omitted, the engine automatically checks for `chassis.png`, `chassis.webp`, `background.png`, etc.

### 3.4 Import, Auto-Apply & Deletion Guide

1. **One-Tap Import & Auto-Apply (OPEN)**:
   - In Unwind, tap **OPEN** to browse local storage or remote WebDAV NAS directories;
   - Tap on any theme archive (labeled with a `🎨` badge and `[🎨 导入主题]` action pill);
   - The app extracts the bundle internally, **immediately applies it to the active interface**, and registers it to the Theme selection list in Settings!
2. **Long-Press Deletion & Safe Reset (SETTINGS)**:
   - Tap **SET** and navigate to the "复古随身主题 / RETRO THEME" section;
   - **Long-press** any newly added custom theme to activate Edit/Delete mode: **all custom themes will reveal a red `✕` icon at the top-right** (built-in themes never show the `✕` icon);
   - Tap the `✕` icon to open the confirmation dialog;
   - Confirming deletion wipes the extracted files and **safely reverts the player to the default built-in theme (Amber)**.

---

## 4. 🤖 AI Prompting Guide (How to Generate Themes with AI)

Copy and paste the template below directly into **ChatGPT, Claude, Gemini, or Cursor** to have AI generate a brand new Unwind theme for you:

````markdown
You are an expert industrial designer specializing in retro skeuomorphic audio hardware and modern mobile design.
Generate a compliant theme for the open-source "Unwind (不卡带)" retro player app based on this concept:
CONCEPT: [Insert your concept here, e.g. "Cyberpunk 2077 High-Tech Low-Life", "1968 Braun Dieter Rams Minimalist", or "1980s Neon Synthwave Sunset"]

The output must strictly conform to the Unwind Theme Specification (v1.0.0).

Output format:
1. Short design summary & historical hardware inspiration (2-3 sentences).
2. JSON configuration block conforming to the schema:
```json
{
  "id": "...",
  "name": "...",
  "author": "...",
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
3. Kotlin DSL enum snippet ready to be added to RetroTheme.kt.
````

---

## 5. Showcase Reference Themes (Production Ready)

### Example 1: Cyberpunk 2077 Night City (High-Voltage Cyan & Hot Neon)
```json
{
  "id": "cyberpunk_neon",
  "name": "CYBERPUNK",
  "author": "NightCity Audio",
  "license": "MIT",
  "description": "High-voltage neon cyan laser display with dark forged carbon chassis",
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

### Example 2: Braun 1968 Dieter Rams Minimalist (Warm Bauhaus Ivory)
```json
{
  "id": "braun_1968",
  "name": "BRAUN 1968",
  "author": "Bauhaus Lab",
  "license": "MIT",
  "description": "Dieter Rams functionalist warm matte off-white chassis with safety orange accent",
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

### Example 3: Sony Walkman TPS-L2 1979 (Iconic Metallic Blue & Silver)
```json
{
  "id": "walkman_1979",
  "name": "TPS-L2 1979",
  "author": "Tokyo Sound",
  "license": "MIT",
  "description": "Classic 1979 metallic ocean blue body with brushed natural silver champagne keys",
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

## 6. Community Submissions & Commercial Rights

1. **Free for Commercial Use**: You may bundle, sell, or distribute custom themes created with this specification without paying royalties or requiring prior approval.
2. **Contributions**: To submit your theme for inclusion in the official Unwind build, open a Pull Request on GitHub with your theme JSON and screenshot!

## RX-C45 built-in preset and inner display (App 1.0.7, 2026-10-30)

RX_C45 (display name RX-C45) is the default preset when no saved selection exists. It uses a warm silver chassis, a grey-brown control plate, monochrome LCDs and a red OPEN key. Saved selections take precedence. Its horizontal sliders, four transport keys, HOLD rocker and National badge are native components selected by the built-in preset ID; importing its color values does not reproduce this dedicated geometry.

Imported themes continue to map the supported chassis, LCD and button colors/material properties onto the corresponding general layout. Do not invent RX-C45 geometry fields in theme JSON. Inner pages share the metal frame, labels and footer height; text follows the playlist font preference. The 95% visual fidelity target remains unverified. This section documents the app implementation and does not change the v1.0.0 theme file format.
