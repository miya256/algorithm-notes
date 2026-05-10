---
tags:
  - k番目
---
[C - Long Sequence](https://atcoder.jp/contests/abc457/tasks/abc457_c)

---
- **kを0-indexedにする**
- $i$ 番目のかたまりの長さ $l_i×c_i$ が、$l_i×c_i\le k$ だったらそのかたまりに含まれないので引く
（$l_i×c_i=k$でも引く）