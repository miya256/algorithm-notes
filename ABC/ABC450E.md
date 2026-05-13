---
tags:
  - 実は小さい
  - k番目
  - 区間和
---
[E - Fibonacci String](https://atcoder.jp/contests/abc450/tasks/abc450_e)

---
10^18 ってでかいけど、i-1番目がi番目のprefixになっているので、実際にはS_60 程度

差分を出しましょうf(r)-f(l)

こういうK番目みたいなのは、**再帰**でやるとよい
うーん、なんだろう。