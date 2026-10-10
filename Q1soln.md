## Q1. Convolution of Rectangular Pulse

Let $T_a(x)$ be a rectangular pulse of height $1$:



\[
T_a(x) =
\begin{cases}
1, & |x| < a \\
0, & |x| \geq a
\end{cases}
\]



---

### (a) Standard Convolution Form

By definition,


\[
(T_a * T_a)(x) = \int_{-\infty}^{\infty} T_a(y)\,T_a(x-y)\,dy
\]



This corresponds to sliding one rectangle by $x$ and computing the overlap.

- For $|x| > 2a$: no overlap, so $(T_a * T_a)(x) = 0$.
- For $|x| \leq 2a$: overlap length is $2a - |x|$.

Thus,


\[
(T_a * T_a)(x) =
\begin{cases}
2a - |x|, & |x| \leq 2a \\
0, & |x| > 2a
\end{cases}
\]



This is a **triangular pulse** of base $[-2a, 2a]$ and height $2a$.

---

### (b) Convolution Theorem (Fourier Transform)

We know:


\[
\mathcal{F}[T_a(x)] = \int_{-a}^{a} e^{-ikx}\,dx
= \frac{2\sin(ka)}{k}
\]



Therefore,


\[
\mathcal{F}[T_a * T_a](k) = \left(\frac{2\sin(ka)}{k}\right)^2
= \frac{4\sin^2(ka)}{k^2}
\]



Inverse Fourier transform gives back the triangular pulse:


\[
(T_a * T_a)(x) = 2a - |x|, \quad |x| \leq 2a
\]


and $0$ otherwise.
