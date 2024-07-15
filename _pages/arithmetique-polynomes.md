---
layout: default
title: Arithmétique des polynômes
permalink: arithmetique-des-polynomes
redirect_from:
  - arithmétique-des-polynômes
---

---

<h3 id="cn-racines-rationnelles-polynomes-entiers">
  <a href="#cn-racines-rationnelles-polynomes-entiers" class="header">
  Racines rationnelles de polynômes entiers (condition nécessaire)</a>
</h3>

Soit $P = a_0 + a_1X + \ldots + a_nX^n\in\mathbb{Z}[X]$ (avec $a_n\neq 0$).<br>
On suppose que $P$ admet une racine rationnelle $\displaystyle\frac{p}{q}$ avec $p\wedge q = 1$ (fraction irréductible).<br>
Montrer que $p\mid a_0$ et $q\mid a_n$.

<details>
  <summary><b>Indications</b></summary>
    Écrire $\displaystyle P\left(\frac{p}{q}\right) = 0$ et développer et utiliser le lemme de Gauss.
</details>

<details>
  <summary><b>Solution</b></summary>
    $$\begin{align*}
    P\left(\frac{p}{q}\right) = 0 &\iff a_0 + a_1\frac{p}{q} + \ldots + a_n\left(\frac{p}{q}\right)^n = 0\\
    &\iff a_0q^n + a_1pq^{n-1} + \ldots + a_np^n = 0\\
    &\iff a_0q^n = -p(a_1q^{n-1} + \ldots + a_np^{n-1})\\
    &\implies p\mid a_0q^n\\
    &\iff p\mid a_0 \quad \text{(d'après le lemme de Gauss)}.
    \end{align*}$$
    De même, on a :
    $$\begin{align*}
    P\left(\frac{p}{q}\right) = 0 &\iff a_0q^n + a_1pq^{n-1} + \ldots + a_np^n = 0\\
    &\iff a_np^n = -q(a_0q^{n-1} + \ldots + a_{n-1}p^{n-1})\\
    &\implies q\mid a_np^n\\
    &\iff q\mid a_n \quad \text{(d'après le lemme de Gauss)}.
    \end{align*}$$
    Donc $\displaystyle P\left(\frac{p}{q}\right) = 0 \implies p\mid a_0$ et $q\mid a_n$.
</details>

---
