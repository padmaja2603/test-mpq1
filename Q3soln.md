
# Q3 — Laplace Transform Properties

Given,

$$
\mathcal{L}\{e^{kt}\}=\frac{1}{s-k}, \qquad s>k
$$

Let

$$
\mathcal{L}\{f(t)\}=F(s)
$$

The differentiation property of the Laplace transform is

$$
\mathcal{L}\{tf(t)\}=-\frac{d}{ds}F(s)
$$

More generally,

$$
\mathcal{L}\{t^n f(t)\}=(-1)^n\frac{d^n}{ds^n}F(s)
$$

## (i) Find $\mathcal{L}\{te^{kt}\}$

We know that

$$
\mathcal{L}\{e^{kt}\}=\frac{1}{s-k}
$$

Using the differentiation property,

$$
\mathcal{L}\{te^{kt}\}
=-\frac{d}{ds}\mathcal{L}\{e^{kt}\}
$$

Substituting the known transform,

$$
\mathcal{L}\{te^{kt}\}
=-\frac{d}{ds}\frac{1}{s-k}
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

## (ii) Find $\mathcal{L}\{\sin kt\}$

Using Euler's identity,

$$
\sin kt=\frac{e^{ikt}-e^{-ikt}}{2i}
$$

Taking the Laplace transform of both sides,

$$
\mathcal{L}\{\sin kt\}
=\frac{1}{2i}\left[
\mathcal{L}\{e^{ikt}\}
-\mathcal{L}\{e^{-ikt}\}
\right]
$$

Using the formula

$$
\mathcal{L}\{e^{at}\}=\frac{1}{s-a}
$$

we obtain

$$
\mathcal{L}\{e^{ikt}\}=\frac{1}{s-ik}
$$

and

$$
\mathcal{L}\{e^{-ikt}\}=\frac{1}{s+ik}
$$

Therefore,

$$
\mathcal{L}\{\sin kt\}
=\frac{1}{2i}\left[
\frac{1}{s-ik}-\frac{1}{s+ik}
\right]
$$

Taking a common denominator,

$$
\mathcal{L}\{\sin kt\}
=\frac{1}{2i}
\frac{(s+ik)-(s-ik)}{(s-ik)(s+ik)}
$$

Simplifying the numerator and denominator,

$$
\mathcal{L}\{\sin kt\}
=\frac{1}{2i}\frac{2ik}{s^2+k^2}
$$

Hence,

$$
\boxed{\mathcal{L}\{\sin kt\}=\frac{k}{s^2+k^2}}
$$

## (iii) Find $\mathcal{L}\{t\sin kt\}$

Using the differentiation property,

$$
\mathcal{L}\{t\sin kt\}
=-\frac{d}{ds}\mathcal{L}\{\sin kt\}
$$

From part (ii),

$$
\mathcal{L}\{\sin kt\}=\frac{k}{s^2+k^2}
$$

Substituting,

$$
\mathcal{L}\{t\sin kt\}
=-\frac{d}{ds}\frac{k}{s^2+k^2}
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

The three required Laplace transforms are

$$
\boxed{\mathcal{L}\{te^{kt}\}=\frac{1}{(s-k)^2}}
$$

$$
\boxed{\mathcal{L}\{\sin kt\}=\frac{k}{s^2+k^2}}
$$

$$
\boxed{\mathcal{L}\{t\sin kt\}=\frac{2ks}{(s^2+k^2)^2}}
$$



