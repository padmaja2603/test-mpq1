### Q7. Sequence of First-Order Reactions

We are given the sequence:

$$
A \xrightarrow{K_1} B \xrightarrow{K_2} C \xrightarrow{K_3} D
$$

with initial conditions:

$$
[A](0) = A_0, \quad [B](0) = [C](0) = 0
$$

---

#### Step 1: Differential Equations

$$
\frac{d[A]}{dt} = -K_1 [A]
$$

$$
\frac{d[B]}{dt} = K_1 [A] - K_2 [B]
$$

$$
\frac{d[C]}{dt} = K_2 [B] - K_3 [C]
$$

---

#### Step 2: Solve for $[A](t)$

Laplace transform:

$$
(s+K_1) A(s) = A_0
$$

Thus,

$$
A(s) = \frac{A_0}{s+K_1}
$$

Inverse Laplace:

$$
[A](t) = A_0 e^{-K_1 t}
$$

---

#### Step 3: Solve for $[B](t)$

Laplace transform:

$$
(s+K_2) B(s) = K_1 A(s)
$$

Substitute $A(s)$:

$$
B(s) = \frac{A_0 K_1}{(s+K_1)(s+K_2)}
$$

Partial fractions:

$$
B(s) = \frac{A_0 K_1}{K_2 - K_1} \left( \frac{1}{s+K_1} - \frac{1}{s+K_2} \right)
$$

Inverse Laplace:

$$
[B](t) = \frac{A_0 K_1}{K_2 - K_1} \left( e^{-K_1 t} - e^{-K_2 t} \right)
$$

---

#### Step 4: Solve for $[C](t)$

Laplace transform:

$$
(s+K_3) C(s) = K_2 B(s)
$$

Substitute $B(s)$:

$$
C(s) = \frac{A_0 K_1 K_2}{(s+K_1)(s+K_2)(s+K_3)}
$$

Partial fractions:

$$
C(s) = \frac{A_0 K_1 K_2}{(K_2-K_1)(K_3-K_1)} \cdot \frac{1}{s+K_1}
+ \frac{A_0 K_1 K_2}{(K_1-K_2)(K_3-K_2)} \cdot \frac{1}{s+K_2}
+ \frac{A_0 K_1 K_2}{(K_1-K_3)(K_2-K_3)} \cdot \frac{1}{s+K_3}
$$

Inverse Laplace:

$$
[C](t) =
\frac{A_0 K_1 K_2}{(K_2-K_1)(K_3-K_1)} e^{-K_1 t}
+ \frac{A_0 K_1 K_2}{(K_1-K_2)(K_3-K_2)} e^{-K_2 t}
+ \frac{A_0 K_1 K_2}{(K_1-K_3)(K_2-K_3)} e^{-K_3 t}
$$

---

###  Final Results

$$
[A](t) = A_0 e^{-K_1 t}
$$

$$
[B](t) = \frac{A_0 K_1}{K_2 - K_1} \left( e^{-K_1 t} - e^{-K_2 t} \right)
$$

$$
[C](t) =
\frac{A_0 K_1 K_2}{(K_2-K_1)(K_3-K_1)} e^{-K_1 t}
+ \frac{A_0 K_1 K_2}{(K_1-K_2)(K_3-K_2)} e^{-K_2 t}
+ \frac{A_0 K_1 K_2}{(K_1-K_3)(K_2-K_3)} e^{-K_3 t}
$$

---

> ✍️ **Added by:** Padmaja, 2026-10-12
