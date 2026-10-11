
# Q2 — Solving an Integral Equation Using Fourier Transforms

Solve the integral equation

$$
\int_{-\infty}^{\infty}
y(\xi)e^{-2|x-\xi|}\,d\xi
=e^{-x^2/4}
$$

## Solution

### Step 1: Identify the Convolution

The convolution of two functions $f(x)$ and $g(x)$ is defined as

$$
(f*g)(x)=\frac{1}{\sqrt{2\pi}}
\int_{-\infty}^{\infty}f(\xi)g(x-\xi)\,d\xi
$$

Using the normalized Fourier transform convention,

$$
\mathcal{F}\{f(x)\}
=\widetilde{f}(\omega)
=\frac{1}{\sqrt{2\pi}}
\int_{-\infty}^{\infty}f(x)e^{-i\omega x}\,dx
$$

the convolution theorem gives

$$
\mathcal{F}\{f*g\}(\omega)
=\sqrt{2\pi}\,\widetilde{f}(\omega)\widetilde{g}(\omega)
$$

Comparing the given integral equation with the convolution integral, we identify

$$
f(x)=y(x)
$$

and

$$
g(x)=e^{-2|x|}
$$

Therefore, the given equation can be written as

$$
\int_{-\infty}^{\infty}
y(\xi)e^{-2|x-\xi|}\,d\xi
=e^{-x^2/4}
$$

### Step 2: Apply the Fourier Transform

Let

$$
\mathcal{F}\{y(x)\}=Y(\omega)
$$

and

$$
\mathcal{F}\{g(x)\}=G(\omega)
$$

Taking the Fourier transform of both sides of the integral equation gives


$$
\sqrt{2\pi}\,Y(\omega)G(\omega)
=\mathcal{F}\{e^{-x^2/4}\}
$$

We now calculate the two required Fourier transforms.

### Step 3: Find the Fourier Transform of $g(x)=e^{-2|x|}$

We use the standard Fourier transform formula

$$
\mathcal{F}\{e^{-\alpha|x|}\}
=\frac{1}{\sqrt{2\pi}}
\frac{2\alpha}{\alpha^2+\omega^2}
$$

Putting $\alpha=2$, we obtain

$$
G(\omega)
=\frac{1}{\sqrt{2\pi}}
\frac{4}{4+\omega^2}
$$

Therefore,

$$
G(\omega)=\frac{4}{\sqrt{2\pi}(4+\omega^2)}
$$

### Step 4: Find the Fourier Transform of $e^{-x^2/4}$

We use the standard Gaussian Fourier transform formula

$$
\mathcal{F}\{e^{-\alpha x^2}\}
=\frac{1}{\sqrt{2\alpha}}
e^{-\omega^2/(4\alpha)}
$$

Putting $\alpha=\frac14$, we obtain

$$
\mathcal{F}\{e^{-x^2/4}\}
=\sqrt{2}\,e^{-\omega^2}
$$

Hence, the transformed integral equation becomes

$$
\sqrt{2\pi}\,Y(\omega)
\left[
\frac{4}{\sqrt{2\pi}(4+\omega^2)}
\right]
=\sqrt{2}\,e^{-\omega^2}
$$

Simplifying,

$$
Y(\omega)\frac{4}{4+\omega^2}
=\sqrt{2}\,e^{-\omega^2}
$$

Solving for $Y(\omega)$,

$$
Y(\omega)
=\frac{\sqrt{2}}{4}
e^{-\omega^2}(4+\omega^2)
$$

Therefore,

$$
Y(\omega)
=\frac{e^{-\omega^2}(4+\omega^2)}{2\sqrt{2}}
$$

### Step 5: Apply the Inverse Fourier Transform

The inverse Fourier transform is

$$
y(x)=\frac{1}{\sqrt{2\pi}}
\int_{-\infty}^{\infty}
Y(\omega)e^{i\omega x}\,d\omega
$$

Substituting the expression for $Y(\omega)$,

$$
y(x)=\frac{1}{2\sqrt{4\pi}}
\int_{-\infty}^{\infty}
e^{-\omega^2}(4+\omega^2)e^{i\omega x}\,d\omega
$$

Equivalently,

$$
y(x)=\frac{1}{4\sqrt{2\pi}}
\int_{-\infty}^{\infty}
e^{-\omega^2+i\omega x}
(4+\omega^2)\,d\omega
$$

This integral is the inverse Fourier transform representation of the solution.

## Final Answer

The Fourier transform of the unknown function is

$$
\boxed{
Y(\omega)=
\frac{e^{-\omega^2}(4+\omega^2)}{2\sqrt{2}}
}
$$

and the solution is given by

$$
\boxed{
y(x)=\frac{1}{\sqrt{2\pi}}
\int_{-\infty}^{\infty}
\frac{e^{-\omega^2}(4+\omega^2)}{2\sqrt{2}}
e^{i\omega x}\,d\omega
}
$$
