---
title: "【LaTeX】Tabular：横幅指定して中央揃え"
emoji: "📈"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: [LaTeX, Tabular]
published: true
---
# 今回の目標
　表を出力するとき，表の横幅を`p{length}`で定めることが一般的であるが，この時左寄せになる．
- 幅を指定する
- 中央そろえ
## ソースコード
- `array`パッケージを読み込む必要があります．
```tex
\documentclass{standalone}
\usepackage{array}
\begin{document}
\begin{tabular}{|p{5em}|>{\centering}p{5em}|>{\raggedleft}p{5em}|}
  left & center & right 
\end{tabular}
\end{document}
```
## 出力結果
![](/images/ddbc21b7e68b0e/fig1.png)*図1*

# 参考
- 美文書本［p.147］
