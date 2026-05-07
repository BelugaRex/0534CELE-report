# ELEC4350 Final Group Project — Report

*课程大作业报告*

> **Group 5**
>
> Network-on-Chip (NoC) Architectures in AI Chip and System
>
> *AI 芯片与系统中的片上网络（NoC）架构*

---

## Project Overview

*项目简介*

**Topic**:

Network-on-Chip (NoC) Architectures in AI Chip and System

*AI 芯片与系统中的片上网络（NoC）架构*

**Type**:

Survey Paper / Literature Review

*综述论文 / 文献综述*

**Deadline**:

May 29

*5 月 29 日*

**Length**:

Double-column, 8 pages (excluding references)

*双栏排版，8 页（不含参考文献）*

**Template**:

IEEEtran (`\documentclass[journal]{IEEEtran}`)

*IEEEtran 模板（`\documentclass[journal]{IEEEtran}`）*

---

## File Structure

*文件结构*

```
report/
├── .AGENT.md              # Agent instructions
│                          # 代理指令文件
├── .gitignore              # Git ignore rules
│                          # Git 忽略规则
├── .vscode/                # VS Code config (LaTeX Workshop)
│                          # VS Code 配置
├── README.md               # Project overview
│                          # 项目说明（本文件）
├── main.tex                # Main LaTeX file (preamble + \input sections)
│                          # LaTeX 主文件（导言区 + \input 引入各章节）
├── references.bib          # References
│                          # 参考文献
├── sections/               # Section files
│                          # 各章节文件
│   ├── introduction.tex
│   ├── fundamentals.tex
│   ├── ai-optimizations.tex
│   ├── chiplets.tex
│   ├── security.tex
│   ├── photonic.tex
│   ├── crosscut.tex
│   └── conclusion.tex
├── image/                  # Figures and assets
│                          # 图片资源
│   ├── fig_path_multicast.png
│   └── fig_tree_multicast.png
└── build/                  # Build outputs (gitignored)
                           # 编译输出（已忽略）
    └── main.pdf
```

---

## How to Compile

*编译方法*

1. Install the VS Code extension **LaTeX Workshop**.

    *安装 VS Code 扩展 **LaTeX Workshop**。*
2. Open `main.tex` and compile with LaTeX Workshop (Recipe: `latexmk` or `pdflatex → bibtex → pdflatex ×2`).

    *打开 `main.tex`，使用 LaTeX Workshop 编译（Recipe: `latexmk` 或 `pdflatex → bibtex → pdflatex ×2`）。*
3. The compiled files will be written to `build/` automatically, and the main PDF is also copied to the repository root for convenience.

    *编译产物会自动输出到 `build/` 目录，主 PDF 也会额外复制到仓库根目录方便预览。*

```bash
# Command-line build (if not using VS Code)
# 命令行编译（如不使用 VS Code）
latexmk -pdf -outdir=build main.tex
```
---

## Course Requirements

*课程要求*

- Focus on AI-computing-related research from the past **3–5 years**.

    *研究范围聚焦近 **3~5 年** AI 计算相关研究。*
- Extend beyond lecture content to emerging technologies, algorithms, and design methodologies rather than repeating class discussion.

    *在课堂内容基础上扩展到新兴技术、算法和设计方法学，而非重复课堂讨论。*
- Extract cross-paper design insights instead of simply listing papers by category.

    *提炼跨论文的设计洞察（insights），而非简单罗列分类论文。*
- A high-quality survey paper may be publishable directly with advisor approval.

    *高质量综述论文有望在导师批准下直接发表。*

---

*Last updated: 2026-05-06 | Group 5*

*最后更新：2026-05-06 | 第 5 组*
