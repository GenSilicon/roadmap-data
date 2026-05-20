<div align="center">

# 🗺️ Roadmap Data

**A community-curated timeline of how the EDA industry is shipping AI.**

DSO.ai · Cerebrus · Aprisa AI · SimAI · ChipStack · …

[![License](https://img.shields.io/badge/data-CC--BY--4.0-blue.svg)](LICENSE)
![Vendors](https://img.shields.io/badge/vendors-6-brightgreen)
![Products](https://img.shields.io/badge/products-21-purple)
![Live](https://img.shields.io/badge/live-gen--silicon.com%2Froadmap-success)

</div>

---

## ✨ What this is

A structured record of **AI / Agentic EDA products** released by traditional EDA vendors (Synopsys / Cadence / Siemens EDA / Ansys) and Chinese players (Empyrean / X-EPIC / …) — when they shipped, what they do, and which part of the design flow they touch.

Each entry is one PR away from showing up on the public timeline at **[gen-silicon.com/roadmap](https://gen-silicon.com/roadmap)**.

> **Why?** AI EDA has gone from a curiosity in 2020 to a full-on agentic race in 2026. There's no single place to see the cadence — vendor sites bury it in marketing, news articles drift out of date. This repo is the canonical, dated, source-cited list.

---

## 📁 Repository layout

```
vendors/
├── synopsys.yaml        # Synopsys.ai suite (DSO/VSO/TSO/ASO + Copilot)
├── cadence.yaml         # Cerebrus / Verisium / JedAI / Cadence.AI / ChipStack
├── siemens.yaml         # Solido / Calibre ML / Aprisa AI / Catapult AI HLS
├── ansys.yaml           # RedHawk-SC ML / SimAI / AnsysGPT
├── empyrean.yaml        # 华大九天 — ALPS-GT
└── xepic.yaml           # 芯华章 — GalaxFV
```

One YAML per vendor. New vendors → drop a new file. New products → append to an existing file.

---

## 📐 Schema

```yaml
id: synopsys                # globally unique slug
name: Synopsys              # display name (English)
nameCn: 新思科技             # display name (Chinese, optional)
region: us                  # us | eu | cn
color: '#22d3ee'            # primary brand color (hex)
accent: '#7c3aed'           # secondary color for gradients (optional)
tagline: One-line positioning sentence
url: https://www.synopsys.com/ai.html

products:
  - name: DSO.ai
    date: '2020-03'                # 'YYYY' or 'YYYY-MM' (always quoted)
    stage: ga                      # announced | shipped | ga | discontinued
    capabilities:                  # tag list, multi-select
      - digital-impl               # digital-impl | verification | analog
                                   # | signoff | dft | pcb | copilot
                                   # | multi-physics | foundation
    summary: One-sentence functional description, ≤ 60 Chinese chars.
    url: https://...               # source link (optional)
    highlight: true                # mark as a milestone product (optional)
```

---

## 🤝 Contributing

1. **Fork** this repo and edit the relevant `vendors/*.yaml` (or add a new one).
2. **Cite the source** in your PR description — official press release, vendor news page, or reputable trade media. We don't accept "industry rumors" or guesses.
3. **If you're not sure of the exact month**, just use the year (`date: '2024'`) — never invent a month.
4. Submit the PR. Reviewer will sanity-check against the source, then merge.

> Spotted a wrong date or a missing product? Open an issue with a link and we'll get it fixed.

---

## 🧭 Editorial principles

- **Verifiability over coverage** — we'd rather have 15 entries that are all correct than 50 with a few fabrications.
- **Public sources only** — analyst-leaked, embargoed, or insider info doesn't qualify.
- **Brand neutrality** — every vendor's tagline is written in their own marketing voice, then copy-edited for clarity. No editorializing.

---

## 📜 License

Data published under **CC-BY-4.0**. You're welcome to mirror, embed, or build on it — please credit `GenSilicon/roadmap-data` and link back so updates flow.
