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
サイズに着目すると、区間加算区間和取得になるので、長さも追加しておきましょう。
- $size=s_x+fl_x$

コストはかなりめんどい。手元で計算して法則を見つけましょう。
$$
(a+f)(b+f)\rightarrow ab+(a+b)f+f^2
$$
$$
\begin{align*}
(a+f)(b+f)+(b+f)(c+f)+(c+f)(a+f)&=ab+(a+b)f+f^2\\
& +bc+(b+c)f+f^2\\
& +ca+(c+a)f+f^2\\
&=ab+bc+ca+2(a+b+c)f+3f^2
\end{align*}
$$
コストは、異なる２を選んで掛けた和でしたよね。
$f$ の項は、サイズの総和に係数がかかってるみたいです。$a$ は $a$ 以外の $n-1$ 個と掛けられるので、$n-1$ 回出てきます。したがって、
$$
(l_x-1)s_xf
$$
$f^2$ の項は、$n$ 個から異なる2を取り出す場合の数と等しいので、
$$
\binom{l_x}{2}f^2
$$
まとめると、
- $size=s_x+fl_x$
- $cost=c_x+(l_x-1)s_xf+\binom{l_x}{2}f^2$

### composition
定数の区間加算なので、
$composition(g,f)=g+f$