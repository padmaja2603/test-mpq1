
# Q1 — Convolution of Two Rectangular Pulses

Define the rectangular pulse

$$
\Pi_a(x)=
\begin{array}{ll}
1, & |x|<a,\\
0, & |x|\geq a.
\end{array}
$$

We find the convolution $(\Pi_a * \Pi_a)(x)$ and its Fourier transform.

## (a) Convolution of the Rectangular Pulses

By definition, the convolution is

$$
(\Pi_a * \Pi_a)(x)
=\int_{-\infty}^{\infty}
\Pi_a(y)\Pi_a(x-y)\,dy.
$$

The integrand equals $1$ where the two rectangular pulses overlap and $0$ elsewhere. Therefore, the convolution equals the length of their overlap.

### Case 1: $|x|<2a$

The two pulses overlap.

For $x\geq 0$, the overlap extends from $x-a$ to $a$. Hence, its length is

$$
a-(x-a)=2a-x.
$$

For $x<0$, the overlap length is $2a+x$.

Combining both cases, the overlap length is $2a-|x|$.

### Case 2: $|x|\geq 2a$

The pulses do not overlap over an interval of positive length. Therefore,

$$
(\Pi_a * \Pi_a)(x)=0.
$$

Hence, the convolution is

$$
\boxed{
(\Pi_a * \Pi_a)(x)=
\begin{cases}
2a-|x|, & |x|<2a,\\
0, & |x|\geq 2a.
\end{cases}
}
$$

This is a triangular pulse with maximum value $2a$ at $x=0$ and zeros at $x=\pm 2a$.

## (b) Fourier Transform

Use the Fourier transform convention

$$
\mathcal{F}\{f\}(k)
=\widetilde{f}(k)
=\int_{-\infty}^{\infty}f(x)e^{-ikx}\,dx.
$$

The convolution theorem states that

$$
\mathcal{F}\{f*g\}(k)
=\widetilde{f}(k)\widetilde{g}(k).
$$

### Method 1: Using the Convolution Theorem

First, calculate the Fourier transform of the rectangular pulse:

$$
\begin{aligned}
\widetilde{\Pi}_a(k)
&=\int_{-\infty}^{\infty}\Pi_a(x)e^{-ikx}\,dx\\
&=\int_{-a}^{a}e^{-ikx}\,dx\\
&=\left[\frac{e^{-ikx}}{-ik}\right]_{-a}^{a}\\
&=\frac{e^{ika}-e^{-ika}}{ik}\\
&=\frac{2\sin(ka)}{k}.
\end{aligned}
$$

Since the convolution contains two identical rectangular pulses,

$$
\begin{aligned}
\mathcal{F}\{\Pi_a*\Pi_a\}(k)
&=\widetilde{\Pi}_a(k)\widetilde{\Pi}_a(k)\\
&=\left(\frac{2\sin(ka)}{k}\right)^2.
\end{aligned}
$$

Therefore,

$$
\boxed{
\mathcal{F}\{\Pi_a*\Pi_a\}(k)
=\frac{4\sin^2(ka)}{k^2}
}
$$

for $k\neq 0$.

At $k=0$, taking the limit gives

$$
\lim_{k\to 0}\frac{4\sin^2(ka)}{k^2}
=4a^2.
$$

### Method 2: Direct Fourier Transform of the Triangular Pulse

From part (a), define

$$
g(x)=(\Pi_a*\Pi_a)(x)=
\begin{cases}
2a-|x|, & |x|<2a,\\
0, & |x|\geq 2a.
\end{cases}
$$

Its Fourier transform is

$$
\widetilde{g}(k)
=\int_{-2a}^{2a}(2a-|x|)e^{-ikx}\,dx.
$$

Since $g(x)$ is even, the sine part of the exponential integrates to zero. Thus,

$$
\widetilde{g}(k)
=2\int_0^{2a}(2a-x)\cos(kx)\,dx.
$$

Integrating by parts,

$$
\begin{aligned}
\int_0^{2a}(2a-x)\cos(kx)\,dx
&=\left[\frac{(2a-x)\sin(kx)}{k}\right]_0^{2a}\\
&\quad+\frac{1}{k}\int_0^{2a}\sin(kx)\,dx\\
&=\frac{1-\cos(2ka)}{k^2}.
\end{aligned}
$$

Therefore,

$$
\begin{aligned}
\widetilde{g}(k)
&=\frac{2[1-\cos(2ka)]}{k^2}\\
&=\frac{4\sin^2(ka)}{k^2},
\end{aligned}
$$

where we used the identity

$$
1-\cos(2\theta)=2\sin^2\theta.
$$

This agrees with the result obtained using the convolution theorem.

## Final Results

The convolution is

$$
\boxed{
(\Pi_a*\Pi_a)(x)=
\begin{cases}
2a-|x|, & |x|<2a,\\
0, & |x|\geq 2a.
\end{cases}
}
$$

Its Fourier transform is

$$
\boxed{
\mathcal{F}\{\Pi_a*\Pi_a\}(k)
=\frac{4\sin^2(ka)}{k^2}
}
$$

with the value at $k=0$ defined by continuity as

$$
\boxed{\widetilde{g}(0)=4a^2.}
$$







