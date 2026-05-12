---
tags:
  - 二分探索
---
[D - No-Subsequence Substring](https://atcoder.jp/contests/abc452/tasks/abc452_d)

---
lを固定して、最初にTが部分列として含まれるようになるrの位置を求める。
文字ごとにindexのリストをもって置き、二分探索でi文字目以降初めて現れる文字を見つければいい

まあi文字目以降に文字cが初めて現れる位置は、26文字分のindexをもっておき、後ろからやるとでますけど

なんかあんま良くわからんかったけど、DPでもできる