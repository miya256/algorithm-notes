---
tags:
  - 部分列DP
---
---
## 状態
$$
dp[i]=i番目までみて、iが一番最後の文字に使われる部分列の種類数
$$
## 遷移
**1-indexed**です。
$k\lt i$ で $S[i]=S[k]$ である最大の整数とします。同じ文字がない場合は $k=0$ とします。
$$
dp[i]=\sum_{j=k}^{i-1}dp[j]
$$

### なぜ
$S[i],S[k]$ の文字を文字$C$ とします。
$k$ 番目より前の文字で終わる部分列について、次に$C$ がくる場合、$S[k]$ で数えてるから。もし、$S[i]$ でも数えてしまったら、$S[k]$ が来る場合と $S[i]$ が来る場合でどっちも $C$ で同じ文字なので重複する。
$k$ 番目も足すのは、$S[k]$ の次に $S[i]$ がきて、$CC$ と連続する場合を数えるためです。
## 実装
以下のように愚直に実装した場合、文字の種類数を $\sigma$ とすると
$$
O(\sigma |S|)
$$

文字の種類数が多いなら累積和を使おう。
- sum_dpも管理
- 最後に文字 $c$ が出てきたindexを記録

### 愚直版
```python
s = input()
s = "." + s # 1-indexedにしたい
n = len(s)

dp = [1] + [0] * n # dp[0]=1とします（空文字を1種類と数えている）
for i in range(1,n+1):
	for j in range(i-1, -1, -1):
		dp[i] += dp[j]
		if s[j] == s[i]:
			break
			
ans = sum(dp[1:]) # 空文字はカウントしない場合
```

### 累積和版
[Library Checker](https://judge.yosupo.jp/submission/374731)

```python
n = int(input())
a = list(map(int,input().split()))
mod = 998244353

a = [-1] + a
dp = [1] + [0] * n
sum_dp = [0,1]
idx = {} # 最後にkがでてきたindex、ない場合は0

for i in range(1,n+1):
    k = idx.get(a[i], 0)
    dp[i] = sum_dp[i] - sum_dp[k]
    dp[i] %= mod
    sum_dp.append((sum_dp[-1] + dp[i]) % mod)
    idx[a[i]] = i

print(sum(dp[1:]) % mod)
```
