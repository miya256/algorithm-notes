## 概要
幅優先探索  

辺の重みがすべて1のとき、最短経路を求められる。

## 計算量
頂点数$N$、辺数$M$のグラフにおいて、
$$O(N+M)$$
## 実装
- はじめに始点をqueueに入れる（複数始点があってもよい）
- queueから取り出したときにvisited判定にする
[実装 : bfs.py](https://github.com/miya256/atcoder_lib_py/blob/main/library/graph/search/bfs.py)