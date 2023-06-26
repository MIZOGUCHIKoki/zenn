---
title: "【LaTeX】Chapterページにページスタイルを適用する"
emoji: "📃"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: [LaTeX]
published: true
---
# 今回の目標
　`\chapter{hoge}`を定義したページに，あらかじめ定義した（された）ページスタイルを適用する．
## ソースコードと出力結果
　プリアンブルに以下のコードを適用する．今回適用するページスタイルは`fancy`とする．
プリアンブルに以下のコードを挿入し，`chapter`を再定義する．
```tex
\makeatletter
\renewcommand{\chapter}{%
  \if@openright\cleardoublepage\else\clearpage\fi
  \global\@topnum\z@
  \secdef\@chapter\@schapter}
\makeatother
\begin{document
```
- 適用前
```tex
\documentclass{jsreport}
\usepackage{fancyhdr}
\pagestyle{fancy}
\begin{document}
\chapter{例}
aa
\clearpage
aa
\end{document}
```
![](/images/fbee702a19bc9e/bf_1.png)![](/images/fbee702a19bc9e/bf_2.png)

- 適用後
```tex
\documentclass{jsreport}
\usepackage{fancyhdr}
\pagestyle{fancy}
\makeatletter
\renewcommand{\chapter}{%
  \if@openright\cleardoublepage\else\clearpage\fi
  \global\@topnum\z@
  \secdef\@chapter\@schapter}
\makeatother
\begin{document}
\chapter{例}
aa
\clearpage
aa
\end{document}
```
![](/images/fbee702a19bc9e/af_1.png)![](/images/fbee702a19bc9e/af_2.png)
