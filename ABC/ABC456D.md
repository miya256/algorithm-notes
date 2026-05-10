---
tags:
  - DP
  - 部分列
---
[D - Not Adjacent 2](https://atcoder.jp/contests/abc456/tasks/abc456_d)

---

- 文字は数字の配列に変換しておくといい
- **空文字で終わる場合** を後ろにつけておくと、実装が楽
- 最後に合計するときに含めないようにだけ注意
```python
mod = 998244353
s = input()
s = [ord(si) - ord("a") for si in s]

# i番目まで選ぶかどうか決め、最後の文字がjである場合が、何通りか
dp = [0, 0, 0, 1]  # 空文字である場合が1
for i in range(len(s)):
    ndp = dp[:]
    k = s[i]
    for j in range(4):
        if j != k:
            ndp[k] += dp[j]
    ndp[k] %= mod
    dp = ndp
print(sum(dp[:-1]) % mod)
```