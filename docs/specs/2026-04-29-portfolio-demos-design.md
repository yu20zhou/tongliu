# Portfolio Interactive Demos — Design Spec

**Date**: 2026-04-29
**Author**: Joey (for Tong Liu's portfolio)
**Status**: Approved

---

## Overview

Add 3 interactive frontend demos to Tong Liu's portfolio website, showcasing real project work from her resume. Each demo is a standalone HTML file using Chart.js + vanilla JS — no build step, no framework, deployed alongside the existing reveal.js site on Vercel.

## Design Palette — PANTONE Light Theme

Light, warm palette using PANTONE Colors of the Year:
- Background: `#FAF8F5` (warm off-white)
- Surface: `#FFFFFF` (white cards with subtle shadow)
- Border: `#E8E2DA` (warm gray)
- Mocha Mousse: `#A47764` — PANTONE 2025 (primary, headings, active states)
- Peach Fuzz: `#FFBE98` — PANTONE 2024 (highlights, badges, hover)
- Peach Light: `#FFF3EB` (peach tint backgrounds for cards/callouts)
- Very Peri: `#6667AB` — PANTONE 2022 (links, accent, interactive elements)
- Viva Magenta: `#BB2649` — PANTONE 2023 (significant/alert indicators)
- Text: `#2C2420` (warm dark brown, not pure black)
- Muted: `#8B8680` (secondary text)
- Fonts: Cormorant Garamond (headings) + Inter (body)

## File Structure

```
tongliu/
├── index.html              (existing reveal.js presentation)
├── styles.css              (existing)
├── demos/
│   ├── index.html          (demo hub — links to all 3 demos)
│   ├── shared.css          (shared demo styles, PANTONE theme)
│   ├── experiment-dashboard.html
│   ├── pipeline-visualizer.html
│   └── ab-test-calculator.html
```

## Navigation

- Main presentation slide 17 (closing) gets a "View Interactive Demos →" link
- `/demos/index.html` is a card-grid hub page linking to each demo
- Each demo has a "← Back to Demos" breadcrumb + "← Portfolio" link

---

## Demo 1: Holdout Experiment Dashboard

**Source project**: Meta — Gen-AI Experiment Reporting Dashboard

### What it shows
An interactive experiment results dashboard with:
- **Metric selector**: dropdown to switch between metrics (e.g., DAU, Engagement Rate, Revenue per User)
- **Cohort filter**: checkboxes for age group, region, platform
- **Results panel**: treatment vs control with lift %, confidence interval, p-value
- **Chart**: bar chart showing treatment effect by cohort (Chart.js)
- **Statistical significance badge**: green "Significant" / gray "Not Significant" based on p-value threshold

### Data
Hardcoded JSON simulating experiment results:
- 3 metrics × 4 cohorts × 2 arms (control/treatment)
- Realistic-looking numbers (not real Meta data)
- P-values that demonstrate both significant and non-significant results

### Layout
```
┌─────────────────────────────────────────────┐
│  ← Back to Demos          Experiment Dashboard  │
├─────────────────────────────────────────────┤
│  [Metric ▾]  [☑ US ☑ EU ☑ APAC]  [☑ 18-24 ☑ 25-34]  │
├──────────────────────┬──────────────────────┤
│                      │  Summary Card         │
│   Bar Chart          │  ┌─────────────────┐ │
│   (by cohort)        │  │ Lift: +3.2%     │ │
│                      │  │ CI: [1.8, 4.6]  │ │
│                      │  │ p = 0.003       │ │
│                      │  │ ● Significant   │ │
│                      │  └─────────────────┘ │
├──────────────────────┴──────────────────────┤
│  Cohort Breakdown Table                      │
│  Region | Control | Treatment | Lift | p-val │
└─────────────────────────────────────────────┘
```

### Interactions
- Dropdown changes metric → chart and table update
- Checkbox filters toggle cohort visibility
- Hover on chart bars shows tooltip with exact values
- No animations on initial load (clean, professional)

---

## Demo 2: Pipeline Flow Visualizer

**Source project**: Meta — Production Pipeline for Holdout Measurement

### What it shows
An animated node-graph visualization of the multi-stage data pipeline:

```
[Raw Experiment Data] 
    → [Creator-Cohort Segmentation] 
    → [Subpopulation Breakout (Country/Region/Age)]
    → [Aggregation & Dedup]
    → [Product-Contribution Table]
    → [Leadership Dashboards]
```

### Implementation
- SVG-based node graph (hand-crafted, not a library)
- Each node is a rounded rectangle with icon + label
- Animated "data particles" flow along the edges (CSS animation)
- Click a node → side panel shows:
  - Description of the stage
  - Input/output schema (simplified)
  - Tech used (Python, Hive/Presto, etc.)
  - Sample data preview (3-4 rows)

### Layout
```
┌─────────────────────────────────────────────┐
│  ← Back to Demos       Pipeline Visualizer  │
├─────────────────────────────────────────────┤
│                                             │
│   ┌──────┐    ┌──────┐    ┌──────┐         │
│   │ Raw  │───→│Cohort│───→│ Sub- │         │
│   │ Data │    │ Seg  │    │ Pop  │         │
│   └──────┘    └──────┘    └──┬───┘         │
│                              │              │
│              ┌──────┐    ┌──┴───┐          │
│              │Dash- │←───│Agg & │          │
│              │board │    │Dedup │          │
│              └──────┘    └──────┘          │
│                                             │
├─────────────────────────────────────────────┤
│  ┌─ Stage Detail ────────────────────────┐  │
│  │ Creator-Cohort Segmentation           │  │
│  │ Splits raw data by creator cohort...  │  │
│  │ Tech: Python + Hive                   │  │
│  │ Input: raw_experiment_stats           │  │
│  │ Output: cohort_segmented_results      │  │
│  └───────────────────────────────────────┘  │
└─────────────────────────────────────────────┘
```

### Interactions
- Nodes highlight on hover (glow effect with Mocha Mousse)
- Click node → detail panel slides in from bottom
- Animated particles continuously flow through edges
- Mobile: nodes stack vertically

---

## Demo 3: A/B Test Calculator

**Source project**: LendingClub — A/B Testing for Verification Strategies

### What it shows
A statistical significance calculator for A/B tests:
- Input: sample sizes and conversion rates for control/treatment
- Output: z-score, p-value, confidence interval, required sample size
- Visualization: normal distribution curve showing rejection regions

### Layout
```
┌─────────────────────────────────────────────┐
│  ← Back to Demos      A/B Test Calculator   │
├──────────────────────┬──────────────────────┤
│  INPUT               │  RESULTS              │
│                      │                       │
│  Control             │  Z-Score: 2.58        │
│  ┌─ Sample: [10000]  │  P-Value: 0.0099      │
│  └─ Conv %: [4.2]    │  ● Significant (95%)  │
│                      │                       │
│  Treatment           │  Lift: +14.3%         │
│  ┌─ Sample: [10000]  │  CI: [3.6%, 24.9%]   │
│  └─ Conv %: [4.8]    │                       │
│                      │  MDE: 0.4%            │
│  [Calculate]         │  Power: 80%           │
├──────────────────────┴──────────────────────┤
│                                             │
│  Normal Distribution Chart                  │
│  (shaded rejection regions at α = 0.05)     │
│                                             │
├─────────────────────────────────────────────┤
│  Sample Size Estimator                      │
│  "To detect a 10% lift at 95% confidence    │
│   with 80% power, you need ~16,500/group"   │
└─────────────────────────────────────────────┘
```

### Interactions
- Inputs update results in real-time (no submit button needed, debounced)
- Chart animates the z-score position on the distribution
- Preset buttons: "Quick Test (1K)", "Medium (10K)", "Large Scale (100K)"
- Results card color changes: green if significant, gray if not

### Math (vanilla JS, no library)
```
z = (p_treatment - p_control) / sqrt(p_pooled * (1 - p_pooled) * (1/n1 + 1/n2))
p_value = 2 * (1 - normalCDF(abs(z)))
CI = (p_t - p_c) ± z_α/2 * SE
required_n = (z_α/2 + z_β)² * (p1(1-p1) + p2(1-p2)) / (p2 - p1)²
```

---

## Demo Hub Page (`/demos/index.html`)

A card grid linking to each demo:

```
┌─────────────────────────────────────────────┐
│  ← Portfolio           Interactive Demos     │
│                                             │
│  Explore live demonstrations of projects    │
│  from my data engineering career.           │
│                                             │
│  ┌─────────┐  ┌─────────┐  ┌─────────┐    │
│  │ 📊      │  │ 🔄      │  │ 🧮      │    │
│  │Experiment│  │Pipeline │  │  A/B    │    │
│  │Dashboard │  │Visualizer│ │Calculator│    │
│  │         │  │         │  │         │    │
│  │ Meta    │  │ Meta    │  │Lending  │    │
│  │         │  │         │  │ Club    │    │
│  └─────────┘  └─────────┘  └─────────┘    │
└─────────────────────────────────────────────┘
```

---

## Technical Constraints

- **Pure frontend**: HTML + CSS + vanilla JS + Chart.js CDN. No build step.
- **No real data**: All data is synthetic/hardcoded JSON
- **Mobile responsive**: All demos must work on phone screens
- **Performance**: Each demo < 200KB total (excluding Chart.js CDN)
- **Accessibility**: Labels on all inputs, sufficient contrast, keyboard navigable
- **Same design system**: PANTONE palette, Cormorant Garamond + Inter fonts

## What This Is NOT

- Not real Meta data (synthetic only)
- Not a working backend — all client-side
- Not trying to replicate internal tools — inspired by, not copies of
