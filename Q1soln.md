
# Q1 — Convolution of Two Rectangular Pulses

Define the rectangular pulse as follows:

$$
\Pi_a(x)=1 \quad \text{for } |x|<a
$$

$$
\Pi_a(x)=0 \quad \text{for } |x|\geq a
$$

We need to find the convolution $(\Pi_a * \Pi_a)(x)$ and its Fourier transform.

## (a) Convolution of the Rectangular Pulses

By definition, the convolution is

$$
(\Pi_a * \Pi_a)(x)
=\int_{-\infty}^{\infty}\Pi_a(y)\Pi_a(x-y)\,dy
$$

The integrand equals $1$ where the two rectangular pulses overlap and $0$ elsewhere. Therefore, the convolution equals the length of their overlap.

### Case 1: $|x|<2a$

For $x\geq 0$, the overlap extends from $x-a$ to $a$. Its length is

$$
a-(x-a)=2a-x
$$

For $x<0$, the overlap length is $2a+x$.

Combining both cases, the overlap length is $2a-|x|$.

### Case 2: $|x|\geq 2a$

The pulses do not overlap over an interval of positive length. Therefore,

$$
(\Pi_a * \Pi_a)(x)=0
$$

Hence, the convolution is described by

$$
(\Pi_a * \Pi_a)(x)=2a-|x|
\quad \text{for } |x|<2a
$$

and

$$
(\Pi_a * \Pi_a)(x)=0
\quad \text{for } |x|\geq 2a
$$

This is a triangular pulse with maximum value $2a$ at $x=0$ and zeros at $x=\pm 2a$.

## (b) Fourier Transform

We use the Fourier transform convention

$$
\mathcal{F}\{f\}(k)=\widetilde{f}(k)
=\int_{-\infty}^{\infty}f(x)e^{-ikx}\,dx
$$

The convolution theorem states that

$$
\mathcal{F}\{f*g\}(k)
=\widetilde{f}(k)\widetilde{g}(k)
$$

### Method 1: Using the Convolution Theorem

First, calculate the Fourier transform of the rectangular pulse:

$$
\widetilde{\Pi}_a(k)
=\int_{-\infty}^{\infty}\Pi_a(x)e^{-ikx}\,dx
$$

Since $\Pi_a(x)=1$ for $-a<x<a$ and zero elsewhere,

$$
\widetilde{\Pi}_a(k)=\int_{-a}^{a}e^{-ikx}\,dx
$$

Integrating,

$$
\widetilde{\Pi}_a(k)
=\left[\frac{e^{-ikx}}{-ik}\right]_{-a}^{a}
$$

Therefore,

$$
\widetilde{\Pi}_a(k)
=\frac{e^{ika}-e^{-ika}}{ik}
$$

Using $e^{i\theta}-e^{-i\theta}=2i\sin\theta$,

$$
\widetilde{\Pi}_a(k)=\frac{2\sin(ka)}{k}
$$

Since the convolution contains two identical rectangular pulses,

$$
\mathcal{F}\{\Pi_a*\Pi_a\}(k)
=\widetilde{\Pi}_a(k)\widetilde{\Pi}_a(k)
$$

Substituting the Fourier transform,

$$
\mathcal{F}\{\Pi_a*\Pi_a\}(k)
=\left(\frac{2\sin(ka)}{k}\right)^2
$$

Hence,

$$
\mathcal{F}\{\Pi_a*\Pi_a\}(k)
=\frac{4\sin^2(ka)}{k^2}
$$

This expression is valid for $k\neq 0$. At $k=0$, taking the limit gives

$$
\lim_{k\to 0}\frac{4\sin^2(ka)}{k^2}=4a^2
$$

### Method 2: Direct Fourier Transform of the Triangular Pulse

From part (a), the triangular pulse is

$$
g(x)=2a-|x| \quad \text{for } |x|<2a
$$

and

$$
g(x)=0 \quad \text{for } |x|\geq 2a
$$

Its Fourier transform is

$$
\widetilde{g}(k)
=\int_{-2a}^{2a}(2a-|x|)e^{-ikx}\,dx
$$

Since $g(x)$ is even, the sine part integrates to zero. Thus,

$$
\widetilde{g}(k)
=2\int_0^{2a}(2a-x)\cos(kx)\,dx
$$

Integrating by parts,

$$
\int_0^{2a}(2a-x)\cos(kx)\,dx
=\left[\frac{(2a-x)\sin(kx)}{k}\right]_0^{2a}
+\frac{1}{k}\int_0^{2a}\sin(kx)\,dx
$$

Evaluating the integrals gives

$$
\int_0^{2a}(2a-x)\cos(kx)\,dx
=\frac{1-\cos(2ka)}{k^2}
$$

Therefore,

$$
\widetilde{g}(k)
=\frac{2[1-\cos(2ka)]}{k^2}
$$

Using $1-\cos(2\theta)=2\sin^2\theta$,

$$
\widetilde{g}(k)=\frac{4\sin^2(ka)}{k^2}
$$

This agrees with the result obtained using the convolution theorem.

## Final Results

The convolution is

$$
(\Pi_a*\Pi_a)(x)=2a-|x|
\quad \text{for } |x|<2a
$$

and

$$
(\Pi_a*\Pi_a)(x)=0
\quad \text{for } |x|\geq 2a
$$

Its Fourier transform is

$$
\mathcal{F}\{\Pi_a*\Pi_a\}(k)
=\frac{4\sin^2(ka)}{k^2}
$$

with the value at $k=0$ given by

$$
\widetilde{g}(0)=4a^2
$$








