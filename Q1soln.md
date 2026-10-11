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

### (b) Convolution Theorem (Fourier Transform)

By the convolution theorem:

$$
\mathcal{F}[f * g](k) = F(k)\,G(k)
$$

---

#### Fourier Transform of $T_a(x)$

We compute:

$$
T_a(k) = \int_{-a}^{a} e^{-ikx}\,dx
= \left[ \frac{e^{-ikx}}{-ik} \right]_{-a}^{a}
= \frac{e^{ika} - e^{-ika}}{ik}
= \frac{2\sin(ka)}{k}
$$

---

#### Convolution in Frequency Domain

Therefore,

$$
\mathcal{F}[T_a * T_a](k) = T_a(k)\,T_a(k)
= \left(\frac{2\sin(ka)}{k}\right)^2
= \frac{4\sin^2(ka)}{k^2}
$$

---

#### Direct Check by Integration

Let $g(x) = (T_a * T_a)(x)$.

Then,

$$
G(k) = \int_{-2a}^{2a} (2a - |x|)\,e^{-ikx}\,dx
$$

Splitting into cosine terms:

$$
G(k) = 2\int_{0}^{2a} (2a - x)\cos(kx)\,dx
$$

Evaluating gives:

$$
G(k) = \frac{4\sin^2(ka)}{k^2}
$$

---

### Final Result

Thus, both methods agree:

$$
(T_a * T_a)(x) =
\begin{cases}
2a - |x|, & |x| \leq 2a \\
0, & |x| > 2a
\end{cases}
$$

and

$$
\mathcal{F}[T_a * T_a](k) = \frac{4\sin^2(ka)}{k^2}
$$




