## 概要
重みが0である辺があってもよい  
**壁を破壊しながら移動する問題でよく使う**

## 計算量
頂点数 $N$ 、辺数 $M$ のグラフにおいて、
$$O(N+M)$$
## 実装
- 基本はBFSと同じ
- 唯一の違いは、隣接頂点をqueueに入れるときのみ、重みが0なら左側にいれる

[実装 : bfs01.py](https://github.com/miya256/atcoder_lib_py/blob/main/library/graph/search/bfs01.py)

[[BFS]]
