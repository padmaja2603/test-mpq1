
# Q4 — Inverse Laplace Transform Using Partial Fractions and Convolution Theorem

Find the inverse Laplace transform of

$$
F(s)=\frac{1}{(s+a)^2(s+b)}
$$

## Method 1: Partial Fractions

Write the given function in partial fraction form:

$$
\frac{1}{(s+a)^2(s+b)}
=\frac{A}{s+a}+\frac{B}{(s+a)^2}+\frac{C}{s+b}
$$

Multiplying both sides by $(s+a)^2(s+b)$ gives

$$
1=A(s+a)(s+b)+B(s+b)+C(s+a)^2
$$

### Step 1: Find $B$

Putting $s=-a$,

$$
1=B(b-a)
$$

Therefore,

$$
B=\frac{1}{b-a}
$$

### Step 2: Find $C$

Putting $s=-b$,

$$
1=C(a-b)^2
$$

Therefore,

$$
C=\frac{1}{(a-b)^2}
$$

### Step 3: Find $A$

Comparing the coefficients of $s^2$ gives

$$
A+C=0
$$

Therefore,

$$
A=-C=-\frac{1}{(a-b)^2}
$$

Hence, the partial fraction decomposition is

$$
\frac{1}{(s+a)^2(s+b)}
=-\frac{1}{(a-b)^2(s+a)}
+\frac{1}{(b-a)(s+a)^2}
+\frac{1}{(a-b)^2(s+b)}
$$

### Step 4: Take the Inverse Laplace Transform

We use the standard results

$$
\mathcal{L}^{-1}\left\{\frac{1}{s+a}\right\}=e^{-at}
$$

$$
\mathcal{L}^{-1}\left\{\frac{1}{(s+a)^2}\right\}=te^{-at}
$$

$$
\mathcal{L}^{-1}\left\{\frac{1}{s+b}\right\}=e^{-bt}
$$


Applying the inverse Laplace transform term by term,

$$
f(t)=-\frac{e^{-at}}{(a-b)^2}
+\frac{te^{-at}}{b-a}
+\frac{e^{-bt}}{(a-b)^2}
$$

Therefore,

$$
\boxed{
f(t)=\frac{te^{-at}}{b-a}
-\frac{e^{-at}}{(a-b)^2}
+\frac{e^{-bt}}{(a-b)^2}
}
$$

## Method 2: Using the Convolution Theorem

The convolution theorem for inverse Laplace transforms states that

$$
\mathcal{L}^{-1}\{F_1(s)F_2(s)\}
=(f_1*f_2)(t)
$$

where

$$
(f_1*f_2)(t)=\int_0^t f_1(\tau)f_2(t-\tau)\,d\tau
$$

Rewrite the given function as

$$
F(s)=\frac{1}{(s+a)^2}\frac{1}{s+b}
$$

From the standard inverse Laplace transforms,

$$
\mathcal{L}^{-1}\left\{\frac{1}{(s+a)^2}\right\}
=te^{-at}
$$

and

$$
\mathcal{L}^{-1}\left\{\frac{1}{s+b}\right\}
=e^{-bt}
$$

Therefore, by the convolution theorem,

$$
f(t)=\int_0^t \tau e^{-a\tau}e^{-b(t-\tau)}\,d\tau
$$

Taking $e^{-bt}$ outside the integral,

$$
f(t)=e^{-bt}\int_0^t \tau e^{(b-a)\tau}\,d\tau
$$

### Step 1: Evaluate the Integral

Using integration by parts,

$$
\int \tau e^{(b-a)\tau}\,d\tau
=\frac{\tau e^{(b-a)\tau}}{b-a}
-\frac{e^{(b-a)\tau}}{(b-a)^2}
$$

Evaluating between $0$ and $t$,

$$
\int_0^t \tau e^{(b-a)\tau}\,d\tau
=\frac{te^{(b-a)t}}{b-a}
-\frac{e^{(b-a)t}}{(b-a)^2}
+\frac{1}{(b-a)^2}
$$

Substituting this result into the expression for $f(t)$,

$$
f(t)=e^{-bt}
\left[
\frac{te^{(b-a)t}}{b-a}
-\frac{e^{(b-a)t}}{(b-a)^2}
+\frac{1}{(b-a)^2}
\right]
$$

Using $e^{-bt}e^{(b-a)t}=e^{-at}$,

$$
f(t)=\frac{te^{-at}}{b-a}
-\frac{e^{-at}}{(b-a)^2}
+\frac{e^{-bt}}{(b-a)^2}
$$

Since $(a-b)^2=(b-a)^2$, this is equivalent to the result obtained using partial fractions.

## Final Answer

For $a\neq b$,

$$
\boxed{
\mathcal{L}^{-1}\left\{
\frac{1}{(s+a)^2(s+b)}
\right\}
=
\frac{te^{-at}}{b-a}
+\frac{e^{-bt}-e^{-at}}{(b-a)^2}
}
$$
