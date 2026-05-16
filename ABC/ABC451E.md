---
tags:
  - 最小全域木
---
[E - Tree Distance](https://atcoder.jp/contests/abc451/tasks/abc451_e)

[[最小全域木]]

---
aを昇順にみて、最小全域木をつくって、それの各頂点同士の距離が等しいか確かめるだけ

俺のライブラリで、Diameter, LCAとかで距離出せます。

## 高速化
edgesをsortするとき、(w,u,v)のタプルをビットにしていれると、めっちゃ速くなります。
`w<<24|u<<12|v`
