---
tags:
  - k番目
---
[E - A += v](https://atcoder.jp/contests/abc449/tasks/abc449_e)

---
同じ回数のやつをまとめたい気がするが、sortしとけばwhile文でどうとでもなる。
```python
cnt = cnts[-1]
while cnts and cnts[-1] == cnt:
	cnt = cnts.pop()
```
こうしとけば、同じカウントのやつだけとりだせる