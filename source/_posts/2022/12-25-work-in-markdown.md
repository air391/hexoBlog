---
title: pandoc与markdown协同工作
tags: 
 - markdown
 - pandoc
categories: 笔记
date: 2022-12-25 22:15:41
---


## 直接到pdf

```bash
pandoc --pdf-engine=xelatex -V CJKmainfont="STSong" -f markdown-implicit_figures source.md -o target.pdf
```

### 中文

参考[文章](https://jdhao.github.io/2017/12/10/pandoc-markdown-with-chinese/)

1. 找到系统支持中文字体`fc-list :lang=zh`
2. 添加命令`--pdf-engine=xelatex -V CJKmainfont="STSong"`即可

## 图片位置

参考[stack overflow](https://stackoverflow.com/questions/49482221/pandoc-markdown-to-pdf-image-position)
固定图片位置`-f markdown-implicit_figures`
