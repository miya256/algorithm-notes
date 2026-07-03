---
tags:
  - ソート
---
[[ソート]]

[C - Not Covered Points](https://atcoder.jp/contests/abc462/tasks/abc462_c)

---
$X_i\lt X$ かつ $Y_i\lt Y$ である $i$ が存在してはいけない

$X$ の昇順にみる。$i$ 番目が条件を満たすかどうかは、
- $j\gt i$ である $j$ については、$X_j \ge X_i$ なので内部にないことが確定している
- $j\lt i$ である $j$ について、$Y_j\ge Y_i$ であれば内部にないので、
今まで見た中で $Y$ の最小が $Y_i$ 以上なら内部にない