---
tags:
  - 頂点倍化
  - サイクル検出
---
[E - Endless Holidays](https://atcoder.jp/contests/abc456/tasks/abc456_e)

---
$i$ 曜日に頂点 $v$ にいるというのを１つの点とみなせば、$NW$ 点のグラフになる。

各辺 $uv$ について、
- $s_{u,i}, s_{v,i+1}$ が〇なら $(u,i) \rightarrow (v,i+1)$ へ
- $s_{v,i}, s_{u,i+1}$ が〇なら $(v,i) \rightarrow (u,i+1)$ へ
有向辺をはる。

あとはサイクルがあるならOK