> ✍️ **Added by:** Your Name, 2026-10-12

## 1. Integral Transforms

An integral transform converts a function into another function using a kernel.

### General formula

$$
g(\alpha)=\int_a^b K(\alpha,t)f(t)\,dt
$$

Where:

- $f(t)$ = original function.
- $g(\alpha)$ = transformed function.
- $K(\alpha,t)$ = kernel of the transform.
- $a,b$ = limits of integration.

### Important properties

- **Linearity:**

$$
T[af+bg]=aT[f]+bT[g]
$$

- Integral transforms can simplify differential equations into algebraic equations.
- Fourier and Laplace transforms are important examples of integral transforms.

---

## 2. Fourier Series

A Fourier series represents a periodic function as a sum of sine and cosine functions.

### 2.1 General formula

For a function of period $2\pi$:

$$
f(x)=\frac{a_0}{2}+
\sum_{n=1}^{\infty}
\left(a_n\cos nx+b_n\sin nx\right)
$$

The Fourier coefficients are:

$$
a_0=\frac{1}{\pi}\int_{-\pi}^{\pi}f(x)\,dx
$$

$$
a_n=\frac{1}{\pi}\int_{-\pi}^{\pi}f(x)\cos nx\,dx
$$

$$
b_n=\frac{1}{\pi}\int_{-\pi}^{\pi}f(x)\sin nx\,dx
$$

### 2.2 Important symmetry properties

| Type of function | Condition | Fourier coefficients |
|---|---|---|
| Even | $f(-x)=f(x)$ | $b_n=0$; cosine series only |
| Odd | $f(-x)=-f(x)$ | $a_0=a_n=0$; sine series only |
| General | Neither even nor odd | Both sine and cosine terms |

For even functions, the coefficient integrals can be simplified:

$$
a_0=\frac{2}{\pi}\int_0^\pi f(x)\,dx
$$

$$
a_n=\frac{2}{\pi}\int_0^\pi f(x)\cos nx\,dx
$$

For odd functions:

$$
b_n=\frac{2}{\pi}\int_0^\pi f(x)\sin nx\,dx
$$

### 2.3 Fourier series for a function of period $2L$

$$
f(x)=\frac{a_0}{2}+
\sum_{n=1}^{\infty}
\left[
a_n\cos\left(\frac{n\pi x}{L}\right)
+b_n\sin\left(\frac{n\pi x}{L}\right)
\right]
$$

The coefficients are calculated over $[-L,L]$:

$$
a_0=\frac{1}{L}\int_{-L}^{L}f(x)\,dx
$$

$$
a_n=\frac{1}{L}\int_{-L}^{L}
f(x)\cos\left(\frac{n\pi x}{L}\right)\,dx
$$

$$
b_n=\frac{1}{L}\int_{-L}^{L}
f(x)\sin\left(\frac{n\pi x}{L}\right)\,dx
$$

### 2.4 Fourier series convergence

At a point of continuity, the Fourier series converges to $f(x)$.

At a jump discontinuity, it converges to the average of the left and right limits:

$$
S(x)=\frac{f(x^-)+f(x^+)}{2}
$$

---

## 3. Fourier Transform

The Fourier transform expresses a function in terms of its frequency components. It is useful in wave analysis and differential equations.

### 3.1 Definition

Using the convention in these notes:

$$
\boxed{
\hat f(k)=\frac{1}{\sqrt{2\pi}}
\int_{-\infty}^{\infty}f(x)e^{-ikx}\,dx
}
$$

### 3.2 Inverse Fourier transform

$$
\boxed{
f(x)=\frac{1}{\sqrt{2\pi}}
\int_{-\infty}^{\infty}\hat f(k)e^{ikx}\,dk
}
$$

Here, $k$ is the frequency variable in the transform representation.

### 3.3 Important properties

| Property | Fourier transform |
|---|---|
| Linearity | $\mathcal F[af+bg]=a\hat f+b\hat g$ |
| First derivative | $\mathcal F[f']=ik\hat f(k)$ |
| Second derivative | $\mathcal F[f'']=-k^2\hat f(k)$ |
| Multiplication by $x$ | $\mathcal F[xf]=i\dfrac{d\hat f}{dk}$ |
| Translation | $\mathcal F[f(x-a)]=e^{-ika}\hat f(k)$ |
| Convolution | $\mathcal F[f*g]=\sqrt{2\pi}\,\hat f(k)\hat g(k)$ |

### 3.4 Parseval's relation

The Fourier transform preserves the squared integral norm:

$$
\int_{-\infty}^{\infty} |f(x)|^2 \, dx
=
\int_{-\infty}^{\infty} |\hat{f}(k)|^2 \, dk
$$


### 3.5 Convolution theorem

The convolution of two functions is defined as

$$
(f*g)(x)=\int_{-\infty}^{\infty}f(x-y)g(y)\,dy
$$

Its Fourier transform is

$$
\boxed{
\mathcal F[f*g]
=\sqrt{2\pi}\,\hat f(k)\hat g(k)
}
$$

The important idea is that convolution in the original domain becomes multiplication in the Fourier domain.

### 3.6 Worked example: Fourier transform of a Gaussian

Consider

$$
f(x)=e^{-ax^2},\qquad a>0.
$$

Using the Gaussian integral,

$$
\int_{-\infty}^{\infty}e^{-ax^2-ikx}\,dx
=\sqrt{\frac{\pi}{a}}e^{-k^2/(4a)},
$$

the Fourier transform is

$$
\hat f(k)=\frac{1}{\sqrt{2\pi}}
\int_{-\infty}^{\infty}e^{-ax^2}e^{-ikx}\,dx.
$$

Substituting the Gaussian integral result,

$$
\hat f(k)=\frac{1}{\sqrt{2\pi}}
\sqrt{\frac{\pi}{a}}e^{-k^2/(4a)}.
$$

**Final answer**

$$
\boxed{
\hat f(k)=\frac{1}{\sqrt{2a}}
e^{-k^2/(4a)}
}
$$

Thus, the Fourier transform of a Gaussian is also a Gaussian.

---

## 4. Green's Functions

A Green's function is used to solve differential equations with a source term and specified boundary conditions.

### 4.1 Definition

Consider a linear differential equation:

$$
Lf(x)=g(x)
$$

The Green's function $G(x,x')$ satisfies

$$
\boxed{
L_xG(x,x')=\delta(x-x')
}
$$

where $\delta(x-x')$ is the Dirac delta function.

The solution can then be written as

$$
\boxed{
f(x)=\int G(x,x')g(x')\,dx'
}
$$

The integration limits depend on the domain of the problem.

### 4.2 Meaning of the Green's function

- It describes the response at $x$ due to a source placed at $x'$.
- It incorporates the relevant boundary conditions.
- It converts a differential-equation problem into an integral.

### 4.3 Green's function for a second-order equation

To construct a Green's function:

1. Solve the homogeneous differential equation for $x<x'$.
2. Solve it separately for $x>x'$.
3. Apply the boundary conditions.
4. Impose continuity of $G$ at $x=x'$, where appropriate.
5. Apply the derivative jump condition obtained by integrating the equation across $x=x'$.

The precise jump condition depends on the differential operator and the coefficient of its highest derivative.

### 4.4 Green's function for the wave equation

In three dimensions, a common form is

$$
\boxed{
\frac{1}{c^2}\frac{\partial^2G}{\partial t^2}
-\nabla^2G
=
\delta(\mathbf r-\mathbf r')\delta(t-t')
}
$$

The Green's function describes how a localized source produces a wave response.

The choice of retarded or advanced Green's function determines the time direction of the response.

### 4.5 Worked example: Green's function for a first-order operator

Consider

$$
\frac{dG(x,x')}{dx}=\delta(x-x').
$$

Using the defining property of the Dirac delta function, integrate from $-\infty$ to $x$:

$$
G(x,x')=\int_{-\infty}^{x}\delta(u-x')\,du.
$$

The integral is zero when $x<x'$ and one when $x>x'$. Therefore,

$$
\boxed{
G(x,x')=\Theta(x-x')
}
$$

where $\Theta$ is the Heaviside step function, with its value at the jump depending on convention.

This example illustrates how a Green's function can be constructed directly from the source term. More complicated differential operators require the appropriate boundary conditions.

---

## 5. Laplace Transform

The Laplace transform is particularly useful for solving differential equations with initial conditions.

### 5.1 Definition

For $t\geq 0$,

$$
\boxed{
F(s)=\mathcal L\{f(t)\}
=\int_0^\infty e^{-st}f(t)\,dt
}
$$

Here, $s$ is generally a complex variable.

### 5.2 Standard Laplace transforms

| Function $f(t)$ | Laplace transform |
|---|---|
| $1$ | $\dfrac{1}{s}$, $s>0$ |
| $t^n$ | $\dfrac{n!}{s^{n+1}}$, $s>0$ |
| $e^{at}$ | $\dfrac{1}{s-a}$, $s>a$ |
| $\sin(at)$ | $\dfrac{a}{s^2+a^2}$ |
| $\cos(at)$ | $\dfrac{s}{s^2+a^2}$ |
| $\sinh(at)$ | $\dfrac{a}{s^2-a^2}$, $s>|a|$ |
| $\cosh(at)$ | $\dfrac{s}{s^2-a^2}$, $s>|a|$ |

These standard results are essential for solving Laplace-transform problems quickly.

### 5.3 Important properties

**1. Linearity**

$$
\mathcal L\{af+bg\}=aF(s)+bG(s)
$$

**2. First derivative**

$$
\boxed{
\mathcal L\{f'(t)\}=sF(s)-f(0)
}
$$

**3. Second derivative**

$$
\boxed{
\mathcal L\{f''(t)\}
=s^2F(s)-sf(0)-f'(0)
}
$$

**4. Multiplication by an exponential**

$$
\mathcal L\{e^{at}f(t)\}=F(s-a)
$$

**5. Multiplication by $t$**

$$
\mathcal L\{tf(t)\}=-\frac{dF(s)}{ds}
$$

**6. Integration**

$$
\mathcal L\left\(\int_0^t f(u)\,du\right\)
=\frac{F(s)}{s}
$$

**7. Time delay**

For the unit step function $u(t-a)$,

$$
\boxed{
\mathcal L\{u(t-a)f(t-a)\}=e^{-as}F(s)
}
$$

### 5.4 Inverse Laplace transform

If

$$
F(s)=\mathcal L\{f(t)\},
$$

then

$$
\boxed{
f(t)=\mathcal L^{-1}\{F(s)\}
}
$$

The inverse transform recovers the original function from its Laplace-domain expression.

Common techniques include partial fractions, standard transform pairs, and inverse-transform formulas.

### 5.5 Worked example: Inverse Laplace transform using partial fractions

Find

$$
f(t)=\mathcal L^{-1}
\left\(\frac{1}{s(s+2)}\right\).
$$

**Step 1: Apply partial fractions**

Write

$$
\frac{1}{s(s+2)}
=\frac{A}{s}+\frac{B}{s+2}.
$$

Multiplying by $s(s+2)$ gives

$$
1=A(s+2)+Bs.
$$

Setting $s=0$ gives

$$
A=\frac12.
$$

Setting $s=-2$ gives

$$
B=-\frac12.
$$

Therefore,

$$
\frac{1}{s(s+2)}
=\frac{1}{2s}-\frac{1}{2(s+2)}.
$$

**Step 2: Apply standard inverse transforms**

Using

$$
\mathcal L^{-1}\left\(\frac1s\right\)=1
$$

and

$$
\mathcal L^{-1}\left\(\frac{1}{s+a}\right\)=e^{-at},
$$

we obtain

$$
f(t)=\frac12-\frac12e^{-2t}.
$$

**Final answer**

$$
\boxed{
f(t)=\frac12(1-e^{-2t})
}
$$

---

## 6. Solving Differential Equations Using Laplace Transforms

This is one of the most important applications covered in these notes.

### 6.1 General equation

Consider

$$
y''+ay'+by=g(t)
$$

with initial conditions

$$
y(0)=y_0,\qquad y'(0)=v_0.
$$

Let

$$
Y(s)=\mathcal L\{y(t)\},\qquad
G(s)=\mathcal L\{g(t)\}.
$$

Taking the Laplace transform of both sides gives

$$
s^2Y(s)-sy_0-v_0
+a[sY(s)-y_0]+bY(s)=G(s).
$$

Collecting the terms containing $Y(s)$,

$$
\boxed{
Y(s)=
\frac{G(s)+(s+a)y_0+v_0}
{s^2+as+b}
}
$$

Then calculate the inverse Laplace transform to obtain $y(t)$.


### 6.2 Worked example: Solve an initial-value problem

Solve

$$
y''+y=0,\qquad y(0)=0,\qquad y'(0)=1.
$$

**Step 1: Take the Laplace transform**

Let $Y(s)=\mathcal L\{y(t)\}$. Then

$$
\mathcal L\{y''\}=s^2Y(s)-sy(0)-y'(0).
$$

Substituting the initial conditions,

$$
s^2Y(s)-1+Y(s)=0.
$$

**Step 2: Solve for $Y(s)$**

$$
(s^2+1)Y(s)=1
$$

Therefore,

$$
Y(s)=\frac{1}{s^2+1}.
$$

**Step 3: Apply the inverse Laplace transform**

Using

$$
\mathcal L^{-1}\left\(\frac{a}{s^2+a^2}\right\)
=\sin(at),
$$

we obtain

$$
\boxed{y(t)=\sin t}.
$$

**Step 4: Check the initial conditions**

$$
y(0)=\sin 0=0
$$

$$
y'(t)=\cos t,\qquad y'(0)=1.
$$

Both initial conditions are satisfied.

---

## 7. Laplace Convolution Theorem

The convolution theorem connects multiplication in the transform domain with convolution in the time domain.

### 7.1 Definition

$$
(f*g)(t)=\int_0^t f(t-u)g(u)\,du
$$

### 7.2 Convolution theorem

$$
\boxed{
\mathcal L\{f*g\}=F(s)G(s)
}
$$

The inverse transform is

$$
\boxed{
\mathcal L^{-1}\{F(s)G(s)\}
=\int_0^t f(t-u)g(u)\,du
}
$$

This is useful when a product of Laplace transforms is difficult to invert directly.

### 7.3 Worked example: Convolution of two exponential functions

Let

$$
f(t)=1,\qquad g(t)=e^{-t}.
$$

Their convolution is

$$
(f*g)(t)=\int_0^t f(t-u)g(u)\,du.
$$

Substituting the functions,

$$
(f*g)(t)=\int_0^t e^{-u}\,du.
$$

Integrating,

$$
(f*g)(t)=\left[-e^{-u}\right]_0^t.
$$

Therefore,

$$
\boxed{(f*g)(t)=1-e^{-t}}
$$

Check using Laplace transforms:

$$
F(s)=\frac1s,\qquad G(s)=\frac{1}{s+1}.
$$

Hence,

$$
\mathcal L^{-1}\left\(\frac{1}{s(s+1)}\right\)
=1-e^{-t}.
$$

Both methods give the same result.

---


