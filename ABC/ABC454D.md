---
tags:
  - 括弧列
---
[D - (xx)](https://atcoder.jp/contests/abc454/tasks/abc454_d)

[[括弧列]]

---
## コンテスト中にバグらせた理由
`)` が来た時に、popする条件が、`x==2' だけにしていた。
**`stack[-1] == ")"` という条件も必要**
あほすぎる

