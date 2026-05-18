# AGENT.md — Site Update Guidelines for mscest-cut

> **Golden Rule:** Never push to `main` without a passing local build.
> Run `hugo server` after every change. Check the affected page visually at
> `http://localhost:1313`. Only then commit and push.

```bash
# Standard verify-then-push workflow
hugo server --buildDrafts --disableFastRender
# When page looks correct:
git add -p
git commit -m "feat: <short description>"
git push origin main
```

---

## Task 1 — Clean Up and Rebuild the Entire Publication Section

The current `content/en/publication/` contains duplicate stub folders
(e.g. `2025_Cheng-Yi_Feng/` alongside
`2025_Cheng-Yi_Feng_hybrid-neural-network-pin-fin/`) and entries for students
with no publications. Delete everything and rebuild from the authoritative
source: the 2026 assessment spreadsheet. Only publications with confirmed
DOI or proceedings evidence are included.

### 1.1 Delete all existing publication folders

```bash
# Remove all subfolders but keep the section index
find content/en/publication -mindepth 1 -maxdepth 1 -type d -exec rm -rf {} +
git add content/en/publication
git commit -m "chore: wipe publication folders for clean rebuild from 2026 assessment data"
```

### 1.2 Verify the section index exists

Keep `content/en/publication/_index.md` untouched (it controls the page title
and layout). If it is missing, create it:

```yaml
---
title: "Publications"
subtitle: "Peer-reviewed publications by MScEST graduates."
---
```

### 1.3 Naming convention

Folder names follow `{YEAR}{TYPE}{Surname}{disambiguator}` where TYPE is:

| Code | Meaning |
|------|---------|
| `J`  | Journal article |
| `C`  | Conference paper |
| `BC` | Book chapter |
| `CW` | Conference workshop paper |
| `P`  | Patent |

Disambiguator `a/b/c` is added only when the same `surname+type+year`
collides. Example: three journals by Feng in 2025 →
`2025JFenga`, `2025JFengb`, `2025JFengc`.

### 1.4 Create one folder per publication

Each `index.md` uses standard Hugo Blox publication front-matter.
The `authors` field lists: student first, then HDU supervisor, then CUT supervisor.

---

#### CHENGYI FENG — 4 publications (all Q1 journals)

`content/en/publication/2024JFeng/index.md`
```yaml
---
title: "Hybrid neural network based multi-objective optimal design of hybrid pin-fin microchannel heatsink for integrated microsystems"
authors: ["Chengyi Feng", "Zhao Wensheng", "Paul Christodoulides"]
date: "2024-01-01"
doi: "10.1016/j.icheatmasstransfer.2024.108137"
publication_types: ["article-journal"]
publication: "*International Communications in Heat and Mass Transfer*"
publication_short: "Int. Commun. Heat Mass Transf."
tags: ["Q1 Journal"]
featured: false
---
```

`content/en/publication/2025JFenga/index.md`
```yaml
---
title: "Smart cooling: Hydrogel-enhanced adaptive jet impingement utilizing through silicon via for integrated microsystems"
authors: ["Chengyi Feng", "Zhao Wensheng", "Paul Christodoulides"]
date: "2025-01-01"
doi: "10.1016/j.applthermaleng.2025.125895"
publication_types: ["article-journal"]
publication: "*Applied Thermal Engineering*"
publication_short: "Appl. Therm. Eng."
tags: ["Q1 Journal"]
featured: false
---
```

`content/en/publication/2025JFengb/index.md`
```yaml
---
title: "Adaptive Deep Reinforcement Learning Optimization Design Process for Hybrid Pin-Fin Microchannel Heat Sink Based on Hybrid Neural Network Acceleration"
authors: ["Chengyi Feng", "Zhao Wensheng", "Paul Christodoulides"]
date: "2025-01-01"
doi: "10.23919/cje.2025.00.145"
publication_types: ["article-journal"]
publication: "*Chinese Journal of Electronics*"
publication_short: "Chin. J. Electron."
tags: ["Q1 Journal"]
featured: false
---
```

`content/en/publication/2025JFengc/index.md`
```yaml
---
title: "Multiobjective Deep Reinforcement Learning Driven Collaborative Optimization of TSV-Based Microchannel and PDN for 3-D ICs"
authors: ["Chengyi Feng", "Zhao Wensheng", "Paul Christodoulides"]
date: "2025-01-01"
doi: "10.1109/tcpmt.2025.3618021"
publication_types: ["article-journal"]
publication: "*IEEE Transactions on Components, Packaging and Manufacturing Technology*"
publication_short: "IEEE Trans. Compon. Packag. Manuf. Technol."
tags: ["Q1 Journal"]
featured: false
---
```

---

#### YU WENG — 2 publications (Q2 journal + conference)

`content/en/publication/2025JWeng/index.md`
```yaml
---
title: "NLMap-ATVR: A novel combination of nonlinear mapping network and adaptive total variation regularization for MRI denoising"
authors: ["Yu Weng", "Zhao Jufeng", "Christakis Damianou"]
date: "2025-01-01"
doi: "10.1016/j.mri.2025.110608"
publication_types: ["article-journal"]
publication: "*Magnetic Resonance Imaging*"
publication_short: "Magn. Reson. Imaging"
tags: ["Q2 Journal"]
featured: false
---
```

`content/en/publication/2025CWeng/index.md`
```yaml
---
title: "Adaptive Phase Image Denoising to Improve MRgFUS Thermometry with a Thermal-Response Gaussian Model"
authors: ["Yu Weng", "Zhao Jufeng", "Christakis Damianou"]
date: "2025-01-01"
doi: "10.1145/3773365.3773482"
publication_types: ["paper-conference"]
publication: "Proceedings of the 2025 8th International Conference on Computer Information Science and Artificial Intelligence"
publication_short: "CISAI 2025"
featured: false
---
```

---

#### YUHAN LYU — 1 publication (Q2 journal)

`content/en/publication/2025JLyu/index.md`
```yaml
---
title: "DDPM-EMF: a denoising diffusion probabilistic model-based feature-enhancement fusion network for medical image fusion"
authors: ["Yuhan Lyu", "Zhao Jufeng", "Christakis Damianou"]
date: "2025-01-01"
doi: "10.1364/josaa.549576"
publication_types: ["article-journal"]
publication: "*Journal of the Optical Society of America A*"
publication_short: "J. Opt. Soc. Am. A"
tags: ["Q2 Journal"]
featured: false
---
```

---

#### HAOJIE ZHOU — 1 publication (Q2 journal)

`content/en/publication/2025JZhou/index.md`
```yaml
---
title: "Comparison of hyperbolic embedding methods for Autonomous Systems networks: machine learning versus network science"
authors: ["Haojie Zhou", "Dong Zhekang", "Fragkiskos Papadopoulos"]
date: "2025-01-01"
doi: "10.1088/1402-4896/ae0ebe"
publication_types: ["article-journal"]
publication: "*Physica Scripta*"
publication_short: "Phys. Scr."
tags: ["Q2 Journal"]
featured: false
---
```

---

#### YUCHI HU — 1 publication (Q2 journal)

`content/en/publication/2025JHu/index.md`
```yaml
---
title: "Dynamic Response Comparison of CYTOP and Silica Fiber Bragg Gratings for Vital Sign Monitoring"
authors: ["Yuchi Hu", "Yu Changqiu", "Kyriacos Kalli"]
date: "2025-01-01"
doi: "10.1109/lsens.2025.3625752"
publication_types: ["article-journal"]
publication: "*IEEE Sensors Letters*"
publication_short: "IEEE Sens. Lett."
tags: ["Q2 Journal"]
featured: false
---
```

---

#### JIALE HOU — 1 publication (conference)

`content/en/publication/2025CHou/index.md`
```yaml
---
title: "Automated Prostate Segmentation in Ultrasound Images Based on Different Pre-processing Schemes"
authors: ["Jiale Hou", "Huang Xiwei", "Christos P. Loizou"]
date: "2025-01-01"
doi: "10.1007/978-3-031-96235-6_3"
publication_types: ["paper-conference"]
publication: "*IFIP Advances in Information and Communication Technology*"
publication_short: "IFIP AICT"
featured: false
---
```

---

#### CHENGZHANG WANG — 1 publication (conference)

`content/en/publication/2025CWang/index.md`
```yaml
---
title: "CMAD: Conditional Modeling-Adapter Diffusion for Video Super-Resolution"
authors: ["Chengzhang Wang", "He Zhiwei", "Sotiris Chatzis"]
date: "2025-01-01"
doi: "10.1007/978-3-032-14495-9_9"
publication_types: ["paper-conference"]
publication: "*Lecture Notes in Computer Science*"
publication_short: "LNCS"
featured: false
---
```

---

#### YAZHOU DONG — 1 publication (Q2 journal, DOI pending)

`content/en/publication/2025JDong/index.md`
```yaml
---
title: "Design of Dual-range TMR Current Sensor with SOG-MR Structure for Enhanced Anti-Interference Performance"
authors: ["Yazhou Dong", "Bai Ru", "Petros Aristidou"]
date: "2025-01-01"
doi: ""          # DOI pending — update when issued by publisher
url_source: "https://www.scimagojr.com/journalsearch.php?clean=0&q=15526&tip=sid"
publication_types: ["article-journal"]
publication: "*Measurement Science and Technology*"
publication_short: "Meas. Sci. Technol."
tags: ["Q2 Journal", "DOI Pending"]
featured: false
---
> **Note:** DOI is pending. Acceptance letter submitted as evidence.
> Update the `doi` field above once the publisher issues it.
```

---

#### HAOHAN YU — 1 publication (conference)

`content/en/publication/2025CHaohanYu/index.md`
```yaml
---
title: "An Integrated System for the Texture Analysis of Prostate Ultrasound Images Based on Different Pre-processing Schemes"
authors: ["Haohan Yu", "Huang Xiwei", "Christos P. Loizou"]
date: "2025-01-01"
doi: "10.1007/978-3-031-96235-6_2"
publication_types: ["paper-conference"]
publication: "*IFIP Advances in Information and Communication Technology*"
publication_short: "IFIP AICT"
featured: false
---
```

---

#### RUI ZHENG — 1 publication (conference)

`content/en/publication/2025CZheng/index.md`
```yaml
---
title: "Design of a Marine Environment Buoy Monitoring Platform Based on LoRa"
authors: ["Rui Zheng", "Dong Linxi", "Michalis Michaelides"]
date: "2025-01-01"
doi: "10.1109/maris64137.2025.11139723"
publication_types: ["paper-conference"]
publication: "2025 Symposium on Maritime Informatics and Robotics"
publication_short: "MARIS 2025"
featured: false
---
```

---

#### LINGMING YU — 1 publication (conference workshop)

`content/en/publication/2025CLingmingYu/index.md`
```yaml
---
title: "Smartphone-Based Attitude-Unconstrained Pedestrian Dead Reckoning System with Positioning Adjustment using Wi-Fi Fingerprinting"
authors: ["Lingming Yu", "Cai Wenyu", "Michalis Michaelides"]
date: "2025-01-01"
url_pdf: "https://ceur-ws.org/Vol-4047/short10.pdf"
publication_types: ["paper-conference"]
publication: "CEUR Workshop Proceedings, IPIN-WCAL 2025"
publication_short: "IPIN-WCAL 2025"
featured: false
---
```

---

#### ZIHENG HUANG — 1 publication (conference)

`content/en/publication/2025CHuang/index.md`
```yaml
---
title: "Advanced Cloud Computing and Machine Learning Framework for NDVI Time-Series Analysis and Environmental Change Detection"
authors: ["Ziheng Huang", "Wang Gaofeng", "Takis Kasparis"]
date: "2025-01-01"
doi: "10.1109/girst67753.2025.11382153"
publication_types: ["paper-conference"]
publication: "2025 4th International Conference on Geographic Information and Remote Sensing Technology"
publication_short: "GIRST 2025"
featured: false
---
```

---

### 1.5 Folder name reference table

| Folder | Student | Type | Year |
|--------|---------|------|------|
| `2024JFeng` | Chengyi Feng | Q1 Journal | 2024 |
| `2025JFenga` | Chengyi Feng | Q1 Journal | 2025 |
| `2025JFengb` | Chengyi Feng | Q1 Journal | 2025 |
| `2025JFengc` | Chengyi Feng | Q1 Journal | 2025 |
| `2025JWeng` | Yu Weng | Q2 Journal | 2025 |
| `2025CWeng` | Yu Weng | Conference | 2025 |
| `2025JLyu` | Yuhan Lyu | Q2 Journal | 2025 |
| `2025JZhou` | Haojie Zhou | Q2 Journal | 2025 |
| `2025JHu` | Yuchi Hu | Q2 Journal | 2025 |
| `2025CHou` | Jiale Hou | Conference | 2025 |
| `2025CWang` | Chengzhang Wang | Conference | 2025 |
| `2025JDong` | Yazhou Dong | Q2 Journal (DOI pending) | 2025 |
| `2025CHaohanYu` | Haohan Yu | Conference | 2025 |
| `2025CZheng` | Rui Zheng | Conference | 2025 |
| `2025CLingmingYu` | Lingming Yu | Conf. Workshop | 2025 |
| `2025CHuang` | Ziheng Huang | Conference | 2025 |

### 1.6 Verify publications locally

```bash
hugo server
# Check http://localhost:1313/publication/
# Confirm 16 entries appear, no build errors.
git add content/en/publication
git commit -m "feat: rebuild publication section with canonical naming (2026 cohort, 16 papers)"
```

---

## Task 2 — Awards Section (2026 Cohort, Top-3)

### 2.1 Create section

```bash
mkdir -p content/en/awards
```

`content/en/awards/_index.md`:
```yaml
---
title: "Top Graduate Awards"
subtitle: "Recognising the top 3 graduates of each cohort based on academic performance and research output."
date: 2026-01-01
---
```

### 2.2 Create 2026 cohort file

`content/en/awards/2026.md`:
```markdown
---
title: "2026 Cohort — Top-3 Graduate Awards"
date: 2026-05-18
---

The MScEST Top-3 Graduate Awards for the **2026 graduation cohort** are based
on a composite score (max 7 pts): GPA component (max 5 pts) + research bonus
for peer-reviewed publications and patents (max 2 pts).

| Prize | Student | Score (/7) | HDU Supervisor | CUT Supervisor |
|-------|---------|-----------|----------------|----------------|
| 🥇 1st Prize | Chengyi Feng (冯丞毅) | 6.23 | 赵文生 (Zhao Wensheng) | Paul Christodoulides |
| 🥈 2nd Prize | Yu Weng (翁雨) | 4.99 | 赵巨峰 (Zhao Jufeng) | Christakis Damianou |
| 🥉 3rd Prize | Yuhan Lyu (吕玉涵) | 4.60 | 赵巨峰 (Zhao Jufeng) | Christakis Damianou |

*Awards are decided annually by the MScEST Academic Committee.*  
Contact: [mscest@cut.ac.cy](mailto:mscest@cut.ac.cy)
```

### 2.3 Add Awards to nav menu

In `config/_default/menus.yaml`, add:
```yaml
- name: Awards
  url: /awards/
  weight: 50
```

### 2.4 Verify locally

```bash
hugo server
# Check http://localhost:1313/awards/2026/
git add content/en/awards config/
git commit -m "feat: add 2026 Top-3 Graduate Awards with HDU and CUT supervisors"
```

---

## Task 3 — Simplify the Program Page

### 3.1 Archive and replace

```bash
git mv content/en/program content/en/program_archive
git commit -m "chore: archive detailed course pages"
mkdir -p content/en/program
```

`content/en/program/_index.md`:
```markdown
---
title: "MSc in Energy Systems Technology"
subtitle: "A joint programme between Cyprus University of Technology (CUT) and Hangzhou Dianzi University (HDU), China."
date: 2026-01-01
---

## Overview

The MScEST is a 2-year, 120 ECTS postgraduate programme jointly delivered
by CUT and HDU. It combines rigorous training in engineering fundamentals
with specialisation in energy systems, embedded computing, and intelligent
technologies.

## Programme Structure

| Component | Duration | Location |
|---|---|---|
| Core coursework | Year 1 (Semesters 1–2) | HDU, Hangzhou, China |
| Specialisation & electives | Year 2 (Semester 3) | CUT, Limassol, Cyprus |
| Master's thesis | Year 2 (Semesters 3–4) | CUT (co-supervised) |

## Key Facts

- **Duration:** 2 years (4 semesters), 120 ECTS
- **Language of instruction:** English
- **Degree awarded:** MSc by CUT (EU-recognised)
- **Thematic areas:** Renewable energy systems · Power electronics · Embedded systems & IoT · Intelligent control & ML · Signal processing

## Admissions

For requirements, deadlines and fees contact:
📧 [mscest@cut.ac.cy](mailto:mscest@cut.ac.cy)
```

### 3.2 Remove archive after verification

```bash
hugo server
# Verify http://localhost:1313/program/ renders correctly.
rm -rf content/en/program_archive
git add content/en/program content/en/program_archive
git commit -m "feat: replace detailed course pages with simplified program overview"
```

---

## Task 4 — Remove People Page, Update Contact

### 4.1 Remove people section

```bash
rm -rf content/en/people
```

Remove the People entry from `config/_default/menus.yaml`.

### 4.2 Update contact page

Replace the full content of `content/en/contact/index.md` (or `_index.md`):

```markdown
---
title: "Contact"
date: 2026-01-01
---

## Programme Coordinators

**Prof. Yicheng Wang** — HDU Coordinator  
School of Electronics and Information, Hangzhou Dianzi University, China

**Prof. Petros Aristidou** — CUT Coordinator  
Department of Electrical Engineering, Computer Engineering and Informatics  
Cyprus University of Technology, Limassol, Cyprus

---

## General Enquiries

For admissions, fees, and all programme information:

📧 **[mscest@cut.ac.cy](mailto:mscest@cut.ac.cy)**

🌐 [https://mscest.cut.ac.cy](https://mscest.cut.ac.cy)
```

### 4.3 Verify and commit

```bash
hugo server
# /people/ should return 404 (correct).
# /contact/ should show both coordinators and mscest@cut.ac.cy.
git add content/en/people content/en/contact config/
git commit -m "feat: remove people page; add coordinators to contact with official email"
```

---

## Task 5 — Final Build Check and Push

```bash
# Clean build — mirrors Netlify exactly
hugo --gc --minify -b http://localhost:1313

# If zero errors or warnings:
git log --oneline -8    # review all commits
git push origin main
```

Monitor the [Netlify deploy log](https://app.netlify.com/projects/mscest).
Typical deploy time is ~15 seconds.

---

## Quick Reference

| Section | Path |
|---|---|
| Publications | `content/en/publication/` |
| Awards | `content/en/awards/` |
| Program overview | `content/en/program/_index.md` |
| Contact | `content/en/contact/` |
| Nav menus | `config/_default/menus.yaml` |
