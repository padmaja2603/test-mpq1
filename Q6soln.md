
# Q6 — Damped Harmonic Oscillator Using Laplace Transforms

## Given

The equation of motion is

$$
m\ddot{x}+b\dot{x}+kx=P\delta(t)
$$

with initial conditions

$$
x(0)=0,\qquad \dot{x}(0)=0
$$

Taking the Laplace transform of both sides,

$$
m\mathcal{L}\{\ddot{x}(t)\}
+b\mathcal{L}\{\dot{x}(t)\}
+k\mathcal{L}\{x(t)\}
=P\mathcal{L}\{\delta(t)\}
$$

## Step 1: Apply the Laplace Transform Properties

The Laplace transform of the first derivative is

$$
\mathcal{L}\{\dot{x}(t)\}
=sX(s)-x(0)
$$

Using $x(0)=0$,

$$
\mathcal{L}\{\dot{x}(t)\}=sX(s)
$$

The Laplace transform of the second derivative is

$$
\mathcal{L}\{\ddot{x}(t)\}
=s^2X(s)-sx(0)-\dot{x}(0)
$$

Using the initial conditions,

$$
\mathcal{L}\{\ddot{x}(t)\}=s^2X(s)
$$

where

$$
X(s)=\mathcal{L}\{x(t)\}
$$

The Laplace transform of the Dirac delta function is

$$
\mathcal{L}\{\delta(t)\}
=\int_0^\infty \delta(t)e^{-st}\,dt=1
$$

Therefore, the transformed equation becomes

$$
ms^2X(s)+bsX(s)+kX(s)=P
$$

Taking $X(s)$ common,

$$
X(s)(ms^2+bs+k)=P
$$

Hence,

$$
X(s)=\frac{P}{ms^2+bs+k}
$$

Dividing the numerator and denominator by $m$,

$$
X(s)=\frac{P/m}{s^2+\frac{b}{m}s+\frac{k}{m}}
$$

## Step 2: Complete the Square

Completing the square in the denominator,

$$
s^2+\frac{b}{m}s
=\left(s+\frac{b}{2m}\right)^2-\frac{b^2}{4m^2}
$$

Therefore,

$$
X(s)=
\frac{P/m}
{\left(s+\frac{b}{2m}\right)^2
+\frac{k}{m}-\frac{b^2}{4m^2}}
$$

Define

$$
\omega_1^2=\frac{k}{m}-\frac{b^2}{4m^2}
$$

Thus,

$$
X(s)=
\frac{P/m}
{\left(s+\frac{b}{2m}\right)^2+\omega_1^2}
$$

The solution depends on whether $\omega_1^2$ is positive, zero, or negative.

## Step 3: Underdamped Case

For underdamping,

$$
b^2<4km
$$

Therefore,

$$
\omega_1^2=\frac{k}{m}-\frac{b^2}{4m^2}>0
$$

Taking the inverse Laplace transform,

$$
x(t)=\frac{P}{m}
\mathcal{L}^{-1}
\left\(
\frac{1}
{\left(s+\frac{b}{2m}\right)^2+\omega_1^2}
\right\)
$$

We use the standard inverse Laplace transform formula

$$
\mathcal{L}^{-1}
\left\(
\frac{\omega}{(s+a)^2+\omega^2}
\right\)\right)
=e^{-at}\sin(\omega t)
$$

Therefore,

$$
\boxed{
x(t)=\frac{P}{m\omega_1}
e^{-\frac{bt}{2m}}\sin(\omega_1t)
}
$$

where

$$
\omega_1=\sqrt{\frac{k}{m}-\frac{b^2}{4m^2}}
$$

## Step 4: Critically Damped Case

For critical damping,

$$
b^2=4km
$$

Therefore,

$$
\frac{b^2}{4m^2}=\frac{k}{m}
$$

and hence

$$
\omega_1^2=0
$$

The transformed function becomes

$$
X(s)=
\frac{P/m}{\left(s+\frac{b}{2m}\right)^2}
$$

Taking the inverse Laplace transform,

$$
x(t)=\frac{P}{m}
\mathcal{L}^{-1}
\left\{
\frac{1}{\left(s+\frac{b}{2m}\right)^2}
\right\}
$$

Using

$$
\mathcal{L}^{-1}
\left\{
\frac{1}{(s+a)^2}
\right\}
=te^{-at}
$$

we obtain

$$
\boxed{
x(t)=\frac{P}{m}te^{-\frac{bt}{2m}}
}
$$

This result can also be obtained by taking the limit $\omega_1\to 0$ in the underdamped solution, using

$$
\lim_{\omega_1\to 0}
\frac{\sin(\omega_1t)}{\omega_1}=t
$$

## Step 5: Overdamped Case

For overdamping,

$$
b^2>4km
$$

Therefore,

$$
\omega_1^2=\frac{k}{m}-\frac{b^2}{4m^2}<0
$$

Define the positive real quantity

$$
\lambda=\sqrt{\frac{b^2}{4m^2}-\frac{k}{m}}
$$

Then

$$
\omega_1^2=-\lambda^2
$$

The transformed function becomes

$$
X(s)=
\frac{P/m}
{\left(s+\frac{b}{2m}\right)^2-\lambda^2}
$$

Using the standard inverse Laplace transform

$$
\mathcal{L}^{-1}
\left\{
\frac{1}{(s+a)^2-\lambda^2}
\right\}
=\frac{1}{\lambda}e^{-at}\sinh(\lambda t)
$$

we obtain

$$
\boxed{
x(t)=\frac{P}{m\lambda}
e^{-\frac{bt}{2m}}\sinh(\lambda t)
}
$$

where

$$
\lambda=\sqrt{\frac{b^2}{4m^2}-\frac{k}{m}}
$$

Using the hyperbolic identity

$$
\sinh(\lambda t)=\frac{e^{\lambda t}-e^{-\lambda t}}{2}
$$

the overdamped solution can also be written as

$$
x(t)=\frac{P}{2m\lambda}
\left[
e^{-\left(\frac{b}{2m}-\lambda\right)t}
-e^{-\left(\frac{b}{2m}+\lambda\right)t}
\right]
$$

## Final Results

**Underdamped case:** $b^2<4km$

$$
\boxed{
x(t)=\frac{P}{m\omega_1}
e^{-\frac{bt}{2m}}\sin(\omega_1t)
}
$$

where

$$
\omega_1=\sqrt{\frac{k}{m}-\frac{b^2}{4m^2}}
$$

**Critically damped case:** $b^2=4km$

$$
\boxed{
x(t)=\frac{P}{m}te^{-\frac{bt}{2m}}
}
$$

**Overdamped case:** $b^2>4km$

$$
\boxed{
x(t)=\frac{P}{m\lambda}
e^{-\frac{bt}{2m}}\sinh(\lambda t)
}
$$

where

$$
\lambda=\sqrt{\frac{b^2}{4m^2}-\frac{k}{m}}
$$
