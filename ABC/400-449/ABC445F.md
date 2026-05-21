---
tags:
  - 行列累乗
---
[F - Exactly K Steps 2](https://atcoder.jp/contests/abc445/tasks/abc445_f)

[[行列累乗]]

---
まあ遷移回数から見て、行列累乗が思い浮かびます

しかし、遷移が
$$
dp_{n+1}[v]=\min_u dp_n[u] + C[u][v]
$$
これは、普段の行列の和が min に、積が和になったものです。
min-plus半環 とかいうらしい

まあそういう演算に直して行列累乗しましょう