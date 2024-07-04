---
layout: default
title: Dénombrabilité
permalink: denombrabilite
redirect_from:
  - dénombrabilité
---

---

<h3 id="denombrabilite-nombres-algebriques">
  <a href="#denombrabilite-nombres-algebriques" class="header">
  Dénombrabilité des nombres algébriques</a>
</h3>

Un nombre complexe $x$ est dit **algébrique** s'il est racine d'un polynôme non nul à coefficients rationnels, i.e.

$$x \text{ est un nombre algébrique} \iff \exists P\in\mathbb{Q}[X]\setminus\{0\},\ P(x) = 0.$$

Montrer que l'ensemble des nombres algébriques est dénombrable.

<details>
  <summary><b>Indications</b></summary>
    Toute union dénombrable d'ensembles dénombrables est dénombrable.
</details>

<details>
  <summary><b>Solution</b></summary>
    Soit $A$ l'ensemble des nombres algébriques. On a :
    $$A = \bigcup_{P\in\mathbb{Q}[X]\setminus\{0\}} \{x\in\mathbb{C}\mid P(x) = 0\}.$$
    Or, pour tout $P\in\mathbb{Q}[X]\setminus\{0\}$ fixé, l'ensemble des racines $\{x\in\mathbb{C}\mid P(x) = 0\}$ est fini.<br><br>
    De plus, l'ensemble $\mathbb{Q}[X]\setminus\{0\}$ est dénombrable.<br>
    En effet, on a $\displaystyle \mathbb{Q}[X] = \bigcup_{n\in\mathbb{N}} \mathbb{Q}_n[X]$, où $\mathbb{Q}_n[X]$ est l'ensemble des polynômes de $\mathbb Q[X]$ de degré au plus $n$.<br>
    Or, $\mathbb{Q}_n[X]$ est équipotent à $\mathbb{Q}^{n+1}$ (via la bijection $(a_0,\ldots,a_n)\in\mathbb{Q}^{n+1} \mapsto a_0 + a_1X + \ldots + a_nX^n\in\mathbb{Q}_n[X]$) qui est bien dénombrable comme produit cartésien d'ensembles dénombrables.<br>
    Donc $\mathbb{Q}[X]$ est dénombrable comme union dénombrable d'ensembles dénombrables.<br><br>
    Finalement, l'ensemble $A$ des nombres algébriques est dénombrable comme union dénombrable d'ensembles finis.
</details>

---
