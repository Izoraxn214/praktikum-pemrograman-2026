# Modul 3 - Trigonometri

1. Problem Statement
Membuat Program untuk menghitung nilai sin dan cos dengan pendekatan deret Mc Laurin

## 2. Mathematical Equation

### a. Deret Maclaurin untuk Sinus

$$
\sin x = \sum_{n=0}^{\infty} \frac{(-1)^n}{(2n+1)!} x^{2n+1} = x - \frac{x^3}{3!} + \frac{x^5}{5!} - \frac{x^7}{7!} + \dots
$$

### b. Deret Maclaurin untuk Cosinus

$$
\cos x = \sum_{n=0}^{\infty} \frac{(-1)^n}{(2n)!} x^{2n} = 1 - \frac{x^2}{2!} + \frac{x^4}{4!} - \frac{x^6}{6!} + \dots
$$

### c. Rumus Relative Error ($E_r$)

$$
E_r = \left| \frac{x_{\text{true}} - x_{\text{approx}}}{x_{\text{true}}} \right| \times 100\%
$$

Keterangan:
- $x_{\text{true}}$ : nilai eksak (misalnya dari fungsi `sin()` / `cos()` bawaan)
- $x_{\text{approx}}$ : nilai hampiran dari hasil penjumlahan deret Maclaurin
