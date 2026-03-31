# 國泰 DataEco 簡報版型與設計規範摘要

[cite_start]這份簡報範本展現了國泰金控（Cathay Financial Holdings）旗下 DataEco 生態系的專業形象 [cite: 2, 5, 260]，設計風格強調數位賦能、數據驅動與現代金融的穩重感。

## 1. 簡報設計規範摘要

### 設計主題 (Design Theme)
* [cite_start]**風格**：俐落知性、科技感、留白美學（CUBE App 風格）[cite: 187]。
* [cite_start]**核心視覺**：以摩天大樓仰視角、數位光纖、抽象方塊堆疊呈現「數據生態系」與「金融科技」意象 [cite: 54, 56, 84]。
* [cite_start]**版面率**：強調資訊的呼吸感與閱讀性，並建議文字內容以黑、灰、白色系為主 [cite: 152]。

### 字體規範 (Typography)
* [cite_start]**英文字體**：Arial [cite: 265, 271]。
* [cite_start]**中文字體**：微軟正黑體 (Microsoft JhengHei) [cite: 287, 296]。
* **層級與字級**：
  * [cite_start]大標一 (Title 1)：30pt (Bold) [cite: 265, 266, 287, 288]。
  * [cite_start]大標二 (Title 2)：28pt (Bold) [cite: 268, 269, 290, 291]。
  * [cite_start]副標 (Subtitle)：22pt 或 18pt [cite: 271, 272, 280, 281, 293, 294, 303, 304]。
  * [cite_start]內文 (Body)：14pt (內文一) / 12pt (內文二) [cite: 274, 275, 277, 278, 296, 297, 299, 300]。

### 色彩系統 (Color System) - 60/30/10 法則
* [cite_start]**主色 (Primary, 60%) - 藍綠色系，象徵科技與信任** [cite: 309]：
  * [cite_start]Dark Blue: `#0843AD` [cite: 311, 312]。
  * [cite_start]Blue: `#186AFF` [cite: 317, 318]。
  * [cite_start]Light Blue: `#B2D9FC` [cite: 313, 314]。
  * [cite_start]Teal: `#36CBDA` [cite: 319, 320]。
  * [cite_start]Light Teal: `#82DFE8` [cite: 315, 316]。
* [cite_start]**輔助色與中性色 (Neutrals, 30%) - 用於文字與背景** [cite: 321, 323]：
  * [cite_start]Dark Gray: `#262626` [cite: 325, 326]。
  * [cite_start]Gray: `#A5A5A5` [cite: 327, 328]。
  * [cite_start]Light Gray: `#F2F2F2` [cite: 329, 330]。
* [cite_start]**強調色 (Accent, 10%) - 暖色系，用於重點標示** [cite: 335]：
  * [cite_start]Yellow: `#FFD600` [cite: 331, 332]。
  * [cite_start]Orange: `#F75801` [cite: 333, 334]。
* [cite_start]**漸層應用 (Gradients)** [cite: 341]：
  * [cite_start]藍色漸層：`#B2D9FC` — `#186AFF` — `#0843AD` [cite: 343]。
  * [cite_start]青色漸層：`#CDF2F6` — `#82DFE8` — `#36CBDA` [cite: 344]。
  * [cite_start]混和漸層：`#82DFE8` — `#186AFF` [cite: 345]。

### 簡報版型 (Layouts)
* [cite_start]**章節頁**：全版出血圖片搭配漸層，或以網格系統搭配數字 01-05 呈現模組化資訊 [cite: 31, 32, 33, 34, 35, 36]。
* [cite_start]**圖表頁**：直方圖/長條圖使用主色系深淺搭配 (如 Blue / Light Blue) [cite: 229]。
* [cite_start]**結構圖**：樹狀圖、流程圖、表格等橫式/直式簡報樹狀圖應用，並搭配線條簡潔的圖標 (Icons) [cite: 77, 100, 347]。


### instructions_for_generation
  - "Maintain a professional, clean, and data-driven tone."
  - "Do not overuse bold formatting in regular body text; keep structural hierarchy intact."
  - "Leverage 'Canvas White' or 'Light Gray' for background to emphasize the 'leave-blank' aesthetics."
---

## 2. NotebookLLM 生成專用 YAML 指令 (Vibe Coding)

將以下 YAML 結構提供給 AI 助手，以自動生成符合國泰 DataEco 風格設定的簡報文案與版面結構。

```yaml
#檔案名稱: ppt_template.yaml
#風格: 俐落知性 / Cathay CUBE APP留白美學 / 數位賦能
#核心概念: 運用摘要整理出的色調堆疊層次，展現專業冷靜但不失暖色系點綴的留白美學

presentation_metadata:
  title: "DataEco Style Presentation"
  theme_concept: "Digital Empowerment & Minimalist Trust"
  aspect_ratio: "16:9"
  language: "Traditional Chinese (Taiwan)"

design_system:
  color_palette:
    rule: "60-30-10 Rule"
    primary_tones:
      - name: "Dark Blue"
        hex: "#0843AD"
      - name: "Blue"
        hex: "#186AFF"
      - name: "Teal"
        hex: "#36CBDA"
    neutral_tones:
      - name: "Dark Gray"
        hex: "#262626"
      - name: "Gray"
        hex: "#A5A5A5"
      - name: "Light Gray"
        hex: "#F2F2F2"
    accent_tones:
      - name: "Yellow"
        hex: "#FFD600"
      - name: "Orange"
        hex: "#F75801"
    gradients:
      - "Linear Gradient: #B2D9FC — #186AFF — #0843AD"
      - "Linear Gradient: #CDF2F6 — #82DFE8 — #36CBDA"

  typography:
    english_font: "Arial"
    chinese_font: "Microsoft JhengHei (微軟正黑體)"
    hierarchy:
      slide_title:
        size: "30pt"
        weight: "Bold"
      section_header:
        size: "28pt"
        weight: "Bold"
      subtitle:
        size: "22pt"
        weight: "Regular"
      body_text:
        size: "14pt"
        weight: "Regular"
      annotation:
        size: "12pt"
        weight: "Regular"

  layout_rules:
    whitespace: "High (Minimalist design simulating App UI)"
    grid_system: "Modular grid for tables and content blocks to minimize heavy borders"
    visual_style:
      - "Use pure color blocks or gradients to highlight sections"
      - "Use stroke-style icons"
      - "Apply Dark Blue or Accent colors only to highlight specific text"

slide_templates:
  - type: "Cover / Section Slide"
    layout: "Full bleed image or abstract blocks"
    elements:
      - "Background: Abstract tech imagery or Gradient Blue"
      - "Title: Align with high contrast readability"

  - type: "Content - Data / Chart"
    layout: "Bar chart / Donut chart"
    elements:
      - "Use Light Blue and Blue for bar charts"
      - "Prominent display of percentages (e.g., 92%, 73%)"

  - type: "Content - Flow / Timeline"
    layout: "Horizontal / Vertical Tree Diagram"
    elements:
      - "Step-by-step icons with clear subtitles"
      - "Minimalist layout with clear line directions"

instructions_for_generation:
  - "Maintain a professional, clean, and data-driven tone."
  - "Do not overuse bold formatting in regular body text; keep structural hierarchy intact."
  - "Leverage 'Canvas White' or 'Light Gray' for background to emphasize the 'leave-blank' aesthetics."