---
tags:
  - Aho-Corasick
  - 行列累乗
---
[F - Critical Misread](https://atcoder.jp/contests/abc458/tasks/abc458_f)

[[Aho-Crasick]]
[[行列累乗]]
[[オートマトン]]

---
末尾10文字をもつってのはできないので、Trie木でどのノードにいるかを状態に持つ
遷移だが、Trie木だとできないので、AhoCorasickが必要になる。
AhoCorasickのオートマトンで、オートマトンのどのノードにいるかを状態、遷移をそのままDPの遷移とすることで、DPできる。

今回含んではいけない文字列があるので、遷移した後の状態が含んではいけない文字列ならその行は0になるようにする