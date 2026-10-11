# Q1 --- Convolution of Two Rectangular Pulses

Let the rectangular pulse of height (1) be defined by

\[ `\Pi`{=tex}\_a(x)=
```{=tex}
\begin{cases}
1, & |x|<a,\\
0, & |x|\ge a.
\end{cases}
```
\]

We want to find the convolution ((`\Pi`{=tex}\_a \* `\Pi`{=tex}\_a)(x))
and its Fourier transform.

## (a) Convolution of the rectangular pulses

By definition, the convolution of two functions is

\[ (`\Pi`{=tex}\_a \* `\Pi`{=tex}*a)(x)
=`\int`{=tex}*{-`\infty`{=tex}}\^{`\infty`{=tex}}`\Pi`{=tex}\_a(y),`\Pi`{=tex}\_a(x-y),dy.
\]

Each rectangular pulse has height (1) and is nonzero over an interval of
width (2a). When one pulse is shifted by (x), the integrand equals (1)
where the two pulses overlap and (0) elsewhere. Thus, the convolution
equals the **length of the overlap**.

### Case 1: (\|x\|\<2a)

The two pulses overlap. The overlap length is

\[ 2a-\|x\|. \]

For example, if (x`\ge 0`{=tex}), the overlap is from (x-a) to (a), so
its length is

\[ a-(x-a)=2a-x. \]

If (x\<0), the overlap length is (2a+x). Combining both cases gives
(2a-\|x\|).

### Case 2: (\|x\|`\ge `{=tex}2a)

The pulses do not overlap (apart from a possible single endpoint, which
has zero length). Therefore,

\[ (`\Pi`{=tex}\_a \* `\Pi`{=tex}\_a)(x)=0. \]

Hence,

\[ `\boxed{
(\Pi_a * \Pi_a)(x)=
\begin{cases}
2a-|x|, & |x|<2a,\\
0, & |x|\ge 2a.
\end{cases}
}`{=tex} \]

This is a triangular pulse with its maximum value (2a) at (x=0), and
zeros at (x=`\pm `{=tex}2a).

## (b) Fourier transform

Use the Fourier transform convention

\[ `\mathcal{F}`{=tex}{f}(k)=`\widetilde `{=tex}f(k)
=`\int`{=tex}\_{-`\infty`{=tex}}^{`\infty`{=tex}}f(x)e^{-ikx},dx. \]

With this convention, the convolution theorem states that

\[ `\mathcal{F}`{=tex}{f\*g}(k)
=`\widetilde `{=tex}f(k),`\widetilde `{=tex}g(k). \]

### Method 1: Use the convolution theorem

First, calculate the Fourier transform of the rectangular pulse:

\[
```{=tex}
\begin{aligned}
\widetilde{\Pi}_a(k)
&=\int_{-\infty}^{\infty}\Pi_a(x)e^{-ikx}\,dx\\
&=\int_{-a}^{a}e^{-ikx}\,dx\\
&=\left[\frac{e^{-ikx}}{-ik}\right]_{-a}^{a}\\
&=\frac{e^{ika}-e^{-ika}}{ik}\\
&=\frac{2\sin(ka)}{k}.
\end{aligned}
```
\]

Since the convolution contains two identical rectangular pulses,

\[
```{=tex}
\begin{aligned}
\mathcal{F}\{\Pi_a*\Pi_a\}(k)
&=\widetilde{\Pi}_a(k)\,\widetilde{\Pi}_a(k)\\
&=\left(\frac{2\sin(ka)}{k}\right)^2.
\end{aligned}
```
\]

Therefore,

\[ `\boxed{
\mathcal{F}\{\Pi_a*\Pi_a\}(k)
=\frac{4\sin^2(ka)}{k^2}
}`{=tex} \]

for (k`\ne 0`{=tex}). At (k=0), the value is obtained by taking the
limit:

\[ `\lim`{=tex}\_{k`\to0`{=tex}}`\frac{4\sin^2(ka)}{k^2}`{=tex}=4a\^2.
\]

### Method 2: Verify by directly transforming the triangular pulse

From part (a), let

\[ g(x)=(`\Pi`{=tex}\_a\*`\Pi`{=tex}\_a)(x)=
```{=tex}
\begin{cases}
2a-|x|, & |x|<2a,\\
0, & |x|\ge 2a.
\end{cases}
```
\]

Its Fourier transform is

\[ `\widetilde `{=tex}g(k)
=`\int`{=tex}\_{-2a}^{2a}(2a-\|x\|)e^{-ikx},dx. \]

Because (g(x)) is even, the sine part of
(e\^{-ikx}=`\cos`{=tex}(kx)-i`\sin`{=tex}(kx)) integrates to zero.
Hence,

\[
```{=tex}
\begin{aligned}
\widetilde g(k)
&=2\int_0^{2a}(2a-x)\cos(kx)\,dx.
\end{aligned}
```
\]

Integrating by parts,

\[
```{=tex}
\begin{aligned}
\int_0^{2a}(2a-x)\cos(kx)\,dx
&=\left[\frac{(2a-x)\sin(kx)}{k}\right]_0^{2a}
+\frac{1}{k}\int_0^{2a}\sin(kx)\,dx\\
&=\frac{1-\cos(2ka)}{k^2}.
\end{aligned}
```
\]

Therefore,

\[
```{=tex}
\begin{aligned}
\widetilde g(k)
&=\frac{2[1-\cos(2ka)]}{k^2}\\
&=\frac{4\sin^2(ka)}{k^2},
\end{aligned}
```
\]

where (1-`\cos`{=tex}(2`\theta`{=tex})=2`\sin`{=tex}\^2`\theta`{=tex})
has been used.

This agrees with the result obtained from the convolution theorem.

## Final results

\[ `\boxed{
(\Pi_a*\Pi_a)(x)=
\begin{cases}
2a-|x|, & |x|<2a,\\
0, & |x|\ge 2a
\end{cases}
}`{=tex} \]

and

\[ `\boxed{
\mathcal{F}\{\Pi_a*\Pi_a\}(k)
=\frac{4\sin^2(ka)}{k^2}
}`{=tex} \]

with the continuous value at (k=0) given by (4a\^2).






