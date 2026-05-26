---
tags:
  - DFS
---
[D - Integer-duplicated Path](https://atcoder.jp/contests/abc448/tasks/abc448_d)

[[DFS]]

---
## 1WAの原因
個数を辞書で管理するとき、not in だったら1にして、そうでないなら`+=1`してた
で、そこで多分2つ以上あるやつの種類数を更新してなかったっぽい