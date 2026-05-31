---
tags:
  - GCD
  - mod
---
[E - x + y ≡ x + y](https://atcoder.jp/contests/abc460/tasks/abc460_e)

[[最大公約数（GCD）]]

---
桁数ごとに見ていく
$y$ が $k$ 桁の場合、
$$
\begin{align*}
x\cdot 10^k+y&\equiv x+y\pmod M\\
\iff(10^k-1)x&\equiv 0\pmod M
\end{align*}
$$
$(10^k-1)x$ が $M$ の倍数になるような $x$ を求める。
$(10^k-1)$ が $M$ の倍数になるために、足りない素因数を含む $x$ であればいい。
足りてる素因数は、 $\gcd((10^k-1)x, M)$ なので、足りない素因数は $M/gcd$ 。
よって、$x$ は $n$ 以下の $M/gcd$ の倍数