---
tags:
  - DP
  - 桁DP
---
上から $i$ 桁目まで見たとき、$N$ 以下であることが確定しているかをフラグに持つ

## 状態
### M の倍数であるもの
$\bmod M$ の値を状態にもつ
### 0-9 のどれを含んでいるか
$2^{10}$ 通りの集合のパターンを状態に持つ

## 初期状態
$N$ 以下であることが確定していないほうを 1通りとする

## 遷移
上の桁から見ていく。$i$ 番目の桁を $n_i$ とする
次の桁の数字 $d$ を 0 から 9 まで回す

### N以下であることが確定しているかフラグ
#### $d\lt n_i$ のとき
```
ndp[1] += dp[0]
ndp[1] += dp[1]
```
#### $d=n_i$ のとき
```
ndp[0] += dp[0]
ndp[1] += dp[1]
```
#### $d\gt n_i$ のとき
```
ndp[1] += dp[1]
```
### mod の値
```
ndp[(10*r+d) % m] += dp[r]
```
### 集合
```
if s == 0 and d == 0:
	ndp[s] += dp[s]
else:
	ndp[s|1<<d] += dp[s]
```

## 実装例
```python
# n以下であることが確定して いる/いない
# mで割った余りがr
# 0-9で出現した数字の集合がs
# のときの通り数

n = input() # intに収まらないくらい大きい場合は文字列で受け取ればいい

dp = [[[0] * (1<<10) for _ in range(m)] for _ in range(2)]
dp[0][0][0] = 1

for i in range(len(n)):
	ndp = [[[0] * (1<<10) for _ in range(m)] for _ in range(2)]
	for r in range(m):
		for s in range(1<<10):
			for d in range(10):
				ni = int(n[i])
				nr = (10 * r + d) % m
				ns = 0 if s==d==0 else s|1<<d 
				
				if d < ni:
					ndp[1][nr][ns] += dp[0][r][s]
					ndp[1][nr][ns] += dp[1][r][s]
				elif d == ni:
					ndp[0][nr][ns] += dp[0][r][s]
					ndp[1][nr][ns] += dp[1][r][s]
				else:
					ndp[1][nr][ns] += dp[1][r][s]
	dp = ndp
```