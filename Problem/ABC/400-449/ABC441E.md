---
tags:
---
[E - A > B substring](https://atcoder.jp/contests/abc441/tasks/abc441_e)

[[式変形して添え字をそろえる]]

---
$$
A_r-A_l>B_r-B_l\iff A_l-B_l<A_r-B_r
$$
なので、rを順に見ていって、$A_l-B_l$ が $A_r-B_r$ より小さくなる $l$ の個数を足せばいい
BITとかで