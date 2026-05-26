---
tags:
---
[D - Reconstruct Chocolate](https://atcoder.jp/contests/abc445/tasks/abc445_d)

[[カテゴリー未定]]

---
長方形を並べていくことを考える。
ここで重要なのが、空いているスペースの縦または横に一致する長さのものが１つ以上あるということ。それを選んで左上に置いていく
offset変数を管理しておくと、置く位置は迷わず実装できそう

あとSortedSetいらなそう。大きいほうからみていけばいいっぽい？