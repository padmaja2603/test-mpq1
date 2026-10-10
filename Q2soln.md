## Q2. Convolution Theorem Application

We want to solve using the convolution theorem:

$$
(f * g)(x) = \int_{-\infty}^{\infty} f(y)\,g(x-y)\,dy
= \mathcal{F}^{-1}\big[ F(k)\,G(k) \big]
$$

---

### Fourier Transform of $T_a(x)$

By definition,

$$
\mathcal{F}[T_a(x)] = \int_{-a}^{a} e^{-ikx}\,dx
= \frac{2\sin(ka)}{k}
$$

So,

$$
T_a(k) = \frac{2\sin(ka)}{k}
$$

---

### Convolution in Frequency Domain

By the convolution theorem,

$$
\mathcal{F}[T_a * T_a](k) = T_a(k)\,T_a(k)
= \left(\frac{2\sin(ka)}{k}\right)^2
= \frac{4\sin^2(ka)}{k^2}
$$

---

### Direct Check by Integration

We know from the overlap method:

$$
(T_a * T_a)(x) =
\begin{cases}
2a - |x|, & |x| \leq 2a \\
0, & |x| > 2a
\end{cases}
$$

---

### Fourier Transform of the Triangular Pulse

Let $g(x) = (T_a * T_a)(x)$.

Then,

$$
G(k) = \int_{-2a}^{2a} (2a - |x|)\,e^{-ikx}\,dx
$$

Splitting into cosine and sine parts:

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
