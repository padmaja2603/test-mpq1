
# Q3 — Laplace Transforms Using Differentiation and Shift Properties

Starting from the given result

$$
\mathcal{L}\{e^{kt}\}=\frac{1}{s-k}
$$

and using the differentiation and shift properties of the Laplace transform, we obtain the following transforms without evaluating any transform integral directly.

## (a) Find $\mathcal{L}\{te^{kt}\}$

The differentiation property of the Laplace transform is

$$
\mathcal{L}\{tf(t)\}
=-\frac{d}{ds}\mathcal{L}\{f(t)\}
$$

Taking $f(t)=e^{kt}$, we get

$$
\mathcal{L}\{te^{kt}\}
=-\frac{d}{ds}\mathcal{L}\{e^{kt}\}
$$

Substituting the given transform,

$$
\mathcal{L}\{te^{kt}\}
=-\frac{d}{ds}\left(\frac{1}{s-k}\right)
$$

Differentiating with respect to $s$,

$$
\mathcal{L}\{te^{kt}\}
=-\left(-\frac{1}{(s-k)^2}\right)
$$

Therefore,

$$
\boxed{\mathcal{L}\{te^{kt}\}=\frac{1}{(s-k)^2}}
$$

## (b) Find $\mathcal{L}\{\sin kt\}$

Using Euler's identity,

$$
e^{ikt}=\cos kt+i\sin kt
$$

The given Laplace transform formula can be extended to a complex exponent:

$$
\mathcal{L}\{e^{ikt}\}=\frac{1}{s-ik}
$$

Multiplying the numerator and denominator by $s+ik$,

$$
\mathcal{L}\{e^{ikt}\}
=\frac{s+ik}{s^2+k^2}
$$

Therefore,

$$
\mathcal{L}\{e^{ikt}\}
=\frac{s}{s^2+k^2}
+i\frac{k}{s^2+k^2}
$$

Comparing the imaginary parts gives

$$
\boxed{\mathcal{L}\{\sin kt\}=\frac{k}{s^2+k^2}}
$$

## (c) Find $\mathcal{L}\{t\sin kt\}$

Using the differentiation property,

$$
\mathcal{L}\{tf(t)\}
=-\frac{d}{ds}\mathcal{L}\{f(t)\}
$$

Taking $f(t)=\sin kt$, we obtain

$$
\mathcal{L}\{t\sin kt\}
=-\frac{d}{ds}\mathcal{L}\{\sin kt\}
$$

From part (b),

$$
\mathcal{L}\{t\sin kt\}
=-\frac{d}{ds}\left(\frac{k}{s^2+k^2}\right)
$$

Differentiating with respect to $s$,

$$
\mathcal{L}\{t\sin kt\}
=-k\left(-\frac{2s}{(s^2+k^2)^2}\right)
$$

Therefore,

$$
\boxed{\mathcal{L}\{t\sin kt\}=\frac{2ks}{(s^2+k^2)^2}}
$$

## Final Results

The required Laplace transforms are

$$
\boxed{\mathcal{L}\{te^{kt}\}=\frac{1}{(s-k)^2}}
$$

$$
\boxed{\mathcal{L}\{\sin kt\}=\frac{k}{s^2+k^2}}
$$

$$
\boxed{\mathcal{L}\{t\sin kt\}=\frac{2ks}{(s^2+k^2)^2}}
$$
