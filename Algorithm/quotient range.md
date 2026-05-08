## 概要
$$
\left\lfloor\frac{n}{i}\right\rfloor = k
$$
を満たすiの区間を求める。
$i>\sqrt{n}$ のとき、$k<\sqrt{n}$ であるので、 $k$ は $2\sqrt{n}$ 種類しかない。$O(\sqrt{n})$ で求められる。

## 方法
$$
\begin{align*}
\left\lfloor\frac{n}{i}​\right\rfloor=k​&\iff k\le\frac{n}{i}\lt k+1\\
&\iff \frac{n}{k+1}\lt i\le\frac{n}{k}\\
&\iff \left\lfloor\frac{n}{k+1}​\right\rfloor+1\le i\le\left\lfloor\frac{n}{k}​\right\rfloor
\end{align*}
$$
## 関連
$$
\sum_{i=1}^n\left\lfloor\frac{n}{i}\right\rfloor
$$
これを求められる。

実は、
$$
\sum_{i=1}^{n} \left\lfloor \frac{n}{i} \right\rfloor=
2 \sum_{i^2 \le n} \left\lfloor \frac{n}{i} \right\rfloor-
\left\lfloor \sqrt{n} \right\rfloor^2
$$
なので、総和だけなら
```python
rn = math.isqrt(n) # 内部で小数を使ってないので誤差なし
ans = 0
for i in range(1, rn + 1):
    ans += n // i
ans = 2 * ans - rn * rn
```