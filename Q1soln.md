## Q1. Convolution of Rectangular Pulse

Let $T_a(x)$ be a rectangular pulse of height $1$:

$$
T_a(x) =
\begin{cases}
1, & |x| < a \\
0, & |x| \geq a
\end{cases}
$$

---

### (a) Standard Convolution Form

By definition,

$$
(T_a * T_a)(x) = \int_{-\infty}^{\infty} T_a(y)\,T_a(x-y)\,dy
$$

---

### Overlap Analysis

- For $|x| > 2a$: no overlap, so $(T_a * T_a)(x) = 0$.
- For $|x| \leq 2a$: overlap length is $2a - |x|$.

Thus,

$$
(T_a * T_a)(x) =
\begin{cases}
2a - |x|, & |x| \leq 2a \\
0, & |x| > 2a
\end{cases}
$$

---

### Result

This is a **triangular pulse** of base $[-2a, 2a]$ and maximum height $2a$.


