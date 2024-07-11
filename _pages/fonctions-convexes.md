---
layout: default
title: Fonctions convexes
permalink: fonctions-convexes
---

---

<h3 id="inegalite-de-jensen">
  <a href="#inegalite-de-jensen" class="header">
  Inégalité de Jensen</a>
</h3>

Soit $\ f:I\to\mathbb{R}$ une fonction convexe sur un intervalle $I$. <br>
Soit $n\in\mathbb{N}^*$. Soient $\lambda\_1,\dots,\lambda_n\in\mathbb{R}\_+$ tels que $\displaystyle \sum_{i=1}^n \lambda_i = 1$ et $x_1,\dots,x_n\in I$.<br>
Montrer l'inégalité de Jensen :

$$f\left(\sum_{i=1}^n \lambda_i x_i\right) \leq \sum_{i=1}^n \lambda_i f(x_i).$$

<details>
  <summary><b>Indications</b></summary>
    Faire une récurrence.<br>
    Poser $\displaystyle \lambda = \sum_{i=1}^n \lambda_i$ et $\displaystyle x = \frac{\lambda_1 x_1 + \dots + \lambda_n x_n}{\lambda}$ et montrer le résultat pour $n+1$.
</details>

<details>
  <summary><b>Solution</b></summary>
    Montrons le résultat par récurrence sur $n$.
    Le cas $n=1$ est un cas d'égalité. Le cas $n=2$ découle de la convexité de $f$.<br>
    Supposons que l'inégalité de Jensen soit vraie pour un certain $n\in\mathbb{N}^*$.<br>
    Soient $x_1,\dots,x_{n+1}\in I$ et $\lambda_1,\dots,\lambda_{n+1}\in\mathbb{R}_+$ tels que $\lambda_1+\dots+\lambda_{n+1}=1$.<br>
    Posons $\displaystyle \lambda = \lambda_1+\dots+\lambda_n\geq 0$. On a $\lambda + \lambda_{n+1} = 1$.<br>
    1er cas : $\lambda = 0$. Alors $\lambda_{n+1} = 1$ et $\lambda_1 = \dots = \lambda_n = 0$. Il y a donc égalité dans l'inégalité de Jensen.<br>
    2ème cas : $\lambda > 0$. On a alors
    $$\sum_{i=1}^{n+1} \lambda_i x_i = \lambda x + \lambda_{n+1} x_{n+1}$$
    avec
    $$x = \frac{\lambda_1 x_1 + \dots + \lambda_n x_n}{\lambda}\in I \quad \text{(barycentre)}.$$
    Par convexité de $f$ sur $I$, on a
    $$f\left(\sum_{i=1}^{n+1} \lambda_i x_i\right) = f(\lambda x + \lambda_{n+1} x_{n+1}) \leq \lambda f(x) + \lambda_{n+1} f(x_{n+1}).$$
    Par hypothèse de récurrence appliquée à $x_1,\dots,x_n$ et $\displaystyle \frac{\lambda_1}{\lambda},\dots,\frac{\lambda_n}{\lambda}$, on a
    $$f(x) = f\left(\sum_{i=1}^n \frac{\lambda_i}{\lambda} x_i\right) \leq \sum_{i=1}^n \frac{\lambda_i}{\lambda} f(x_i).$$
    Ainsi,
    $$f\left(\sum_{i=1}^{n+1} \lambda_i x_i\right) \leq \lambda f(x) + \lambda_{n+1} f(x_{n+1}) \leq \sum_{i=1}^{n+1} \lambda_i f(x_i).$$
    Ce qui conclut la preuve par récurrence.
</details>

---
