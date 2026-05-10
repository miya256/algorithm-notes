---
tags:
  - 遅延セグメント木
  - LazySegmentTree
---
[F - Merge Slimes 2](https://atcoder.jp/contests/abc455/tasks/abc455_f)

---
とりあえず、手元で計算してみると、マージ順は関係ないことがわかります。
サイズ $a,b,c$ とすると、
- $ab\rightarrow (a+b)c: ab+bc+ca$ 
- $bc\rightarrow a(b+c): ab+bc+ca$ 

## モノイドの設計
### op
コストの合計を出したいです。コストの計算にはサイズが必要なのでサイズも持っておきます。
コストを $c$、サイズを $s$ と置きます。
- $cost = c_x+c_y+s_xs_y$ 
- $size=s_x+s_y$
### mapping
サイズに着目すると、くかんかさｎ
### composition
定数の区間加算なので、
$composition(g,f)=g+f$