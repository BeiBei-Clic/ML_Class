# 论文项目说明

这是一个整理后的 LaTeX 项目模板，适合在本地用 `latexmk + xelatex` 编译中文论文或翻译类文档。本文档说明项目结构、编译方式，以及如何开始写作。

## 项目结构

- `tex/`：主文件与封面等 TeX 源文件
  - `tex/main.tex`：主入口，编译这个文件
  - `tex/cover.tex`：封面页
- `styles/`：样式与宏包配置
  - `styles/template.sty`：模板样式
- `figures/`：图片资源（如封面图）
- `build/`：编译产物（PDF、辅助文件）
- `.latexmkrc`：根目录编译配置
- `tex/.latexmkrc`：在 `tex/` 目录编译时的配置

## 编译方式（推荐）

在项目根目录：
```
latexmk tex/main.tex
```

在 `tex/` 目录：
```
latexmk main.tex
```

编译产物统一输出到 `build/`。

## 如何开始写论文

1. 打开 `tex/main.tex`，在 `longtable` 环境内写正文内容。
2. 如果需要封面，编辑 `tex/cover.tex` 中的姓名、学院、日期等信息。
3. 图片放在 `figures/`，在 `tex/main.tex` 中用 `\\includegraphics` 引用。
4. 编译生成 PDF，查看 `build/main.pdf`。

## 架构说明（为什么这样组织）

- **源文件与产物分离**：`tex/` 管源码、`build/` 放产物，目录清爽。
- **样式集中管理**：`styles/template.sty` 统一管理字体、排版、宏包。
- **资源集中管理**：`figures/` 统一存图片，便于维护与版本控制。
- **编译固定 XeLaTeX**：避免 `pdflatex` 导致的中文字体报错。

## 常见问题

- 编译报 `unisong96` 或字体找不到：说明用了 `pdflatex`，请用 `latexmk main.tex`（已强制 XeLaTeX）。
- `longtable` 警告要求重跑：正常，重新编译一次即可消除。
