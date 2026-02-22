## BFS（幅優先探索）

辺の重みがすべて1のとき、最短経路を求められる。

### 実装ポイント
- はじめに始点をqueueに入れる（複数始点があってもよい）
- queueから取り出したときにvisited判定にする
[実装](https://github.com/miya256/atcoder_lib_py/blob/main/library/graph/search/bfs.py)

## 01-BFS
重みが0である辺があってもよい  
**壁を破壊
### 実装ポイント
- 基本はBFSと同じ
- 唯一の違いは、隣接頂点をqueueに入れるときのみ、重みが0なら左側にいれる
