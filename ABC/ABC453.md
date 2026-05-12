---
tags:
  - BFS
  - 頂点倍化
---
[D - Go Straight](https://atcoder.jp/contests/abc453/tasks/abc453_d)

---
## 注意点
てきとうにかくとTLEする

## 配列の1次元化
indexerのライブラリをつくったので、それ使おう。
`v = flat(i,j)` みたいにすると、頂点っぽく扱える。
戻すときは、`i,j = unflat(v)`
## visitedのタイミング
普通のBFS, DFSに限り、visitedタイミングはenqueue時のほうが速い。
でもダイクストラや01BFSは違うから困るね。
配列の1次元化をすれば十分速くなるので、pop時visitedでいいと思う。

## 始点探し
最近知ったんだが、二重ループのbreak方法
```python
for i in range(h):
	for j in range(w):
		if ...:
			break
	else:
		continue
	break
```
forが最後まで行ったら、elseでcontinue。そうでなければelseに行かないので、breakされる。