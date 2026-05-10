---
tags:
  - ポインタ
---
[D - Card Pile Query](https://atcoder.jp/contests/abc455/tasks/abc455_d)

---
前と後のポインタを持っておけばいい

## 更新順（aよりあとをbにくっつける）
- `a.prev.next = None`
- `b.next = a`
- `a.prev = b`