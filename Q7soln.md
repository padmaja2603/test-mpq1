### Q7. Solution using Fourier Transform

We are given the differential equation:

$$
- D \frac{d^2 \Phi(x)}{dx^2} + K^2 D \,\Phi(x) = Q \,\delta(x - x_0)
$$

---

#### Step 1: Fourier Transform

Taking Fourier transform:

$$
- D (ik)^2 \Phi(k) + K^2 D \,\Phi(k) = Q e^{-ikx_0}
$$

Simplify:

$$
D (k^2 + K^2)\,\Phi(k) = Q e^{-ikx_0}
$$

Thus,

$$
\Phi(k) = \frac{Q e^{-ikx_0}}{D (k^2 + K^2)}
$$

---

#### Step 2: Inverse Fourier Transform

Now, applying inverse Fourier transform:

$$
\Phi(x) = \frac{1}{2\pi} \int_{-\infty}^{\infty} \Phi(k)\,e^{ikx}\,dk
$$

Substitute $\Phi(k)$:

$$
\Phi(x) = \frac{Q}{2\pi D} \int_{-\infty}^{\infty} \frac{e^{ik(x - x_0)}}{k^2 + K^2}\,dk
$$

---

#### Step 3: Evaluate Integral

Using complex analysis:

$$
\int_{-\infty}^{\infty} \frac{e^{ik(x - x_0)}}{k^2 + K^2}\,dk
= \pi \frac{e^{-K|x - x_0|}}{K}
$$

Therefore,

$$
\Phi(x) = \frac{Q}{2KD}\,e^{-K|x - x_0|}
$$

---

#### Step 4: Identify Green’s Function

The Green’s function $G(x - x')$ satisfies:

$$
- D \frac{d^2 G(x - x')}{dx^2} + K^2 D\,G(x - x') = \delta(x - x')
$$

Solution:

$$
G(x - x') =
