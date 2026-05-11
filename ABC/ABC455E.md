---
tags:
  - 包除原理
---
[E - Unbalanced ABC Substrings](https://atcoder.jp/contests/abc455/tasks/abc455_e)

---
出現回数が等しいやつを数えよう

先頭からi番目までに含まれる a, b, cの個数を $a_i,b_i,c_i$ とすると
## 2つの場合
$$
a_r-a_l=b_r-b_l\iff a_l-b_l=a_r-b_r
$$
を満たす $l,r$ の組の個数が答え。
なので、
```python
ans = 0
cnt = {0: 1}
a_cnt = b_cnt = 0
for i in range(n):
	if s[i] == "a": a_cnt += 1
	if s[i] == "b": b_cnt += 1
	
	ans += cnt[a_cnt - b_cnt]
	cnt[a_cnt - b_cnt] += 1
```

## 3つの場合
$$
\begin{align*}
a_r-a_l=b_r-b_l=c_r-c_l&\iff (a_l-b_l=a_r-b_r)\cap(b_l-c_l=b_r-c_r)\cap(c_l-a_l=c_r-a_r)\\
&\iff (a_l-b_l,b_l-c_l,c_l-a_l)=(a_r-b_r,b_r-c_r,c_r-a_r)
\end{align*}
$$
さっきの２つのやつを、同時に満たせばいいので、タプルにすればいいだけ