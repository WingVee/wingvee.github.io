---
layout: default
title: Suites et séries de fonctions
permalink: suites-et-series-de-fonctions
redirect_from:
  - suites-et-séries-de-fonctions
---

---

<h3 id="etude-serie-fonctions-1">
  <a href="#etude-serie-fonctions-1" class="header">
  Étude de $\displaystyle \sum_{n=1}^{+\infty} \frac{n^2}{n^2+1} x \exp(-nx)$</a>
</h3>

On pose pour $x\in\mathbb R_+$ et $n\in\mathbb N$ :

$$f_k: x\mapsto \frac{n^2}{n^2+1} x \exp(-nx).$$

1. Montrer que la série de fonctions $\displaystyle \sum_{n\geq 0} f_n$ converge simplement sur $\mathbb R_+$.

2. A-t-on convergence normale sur $\mathbb R_+$ ?

3. A-t-on convergence normale sur tout $[A,+\infty[$ avec $A>0$ ?

<details>
  <summary><b>Remarques</b></summary>
    Cet exercice semblerait avoir été donné à l'oral PSI CCINP 2022 (voir <a href="https://beos.prepas.org/sujet.php?id=8252" target="_blank">BEOS 8252</a>).<br>
    J'ai rajouté la question 3.
</details>

<details>
  <summary><b>Solution</b></summary>
    <ol>
      <li>
        Par croissances comparées, on a pour tout $x\in\mathbb R_+$ :
        $$|n^2 f_n(x)|\leq n^2 x \exp(-nx)\xrightarrow[n\to+\infty]{}0.$$
        Donc la série numérique $\displaystyle \sum_{n\geq 0} f_n(x)$ converge pour tout $x\in\mathbb R_+$, d'où la convergence simple de la série de fonctions $\displaystyle \sum_{n\geq 0} f_n$ sur $\mathbb R_+$.
      </li>
      <li>
        On a
        $$f_n'(x) = \frac{n^2}{n^2+1}\left(1-nx\right)\exp(-nx).$$
        Donc $\displaystyle\ f_n'(x)\leq 0 \iff x\geq\frac{1}{n}$.<br>
        Puisque $\ f_n(x)\geq 0$ pour tout $x\in\mathbb R_+$, $f_n$ atteint son maximum en $\displaystyle x = \frac{1}{n}$ et on a
        $$\Vert f_n\Vert_{\infty} = \sup_{x\in\mathbb R_+} |f_n(x)| = f_n\left(\frac{1}{n}\right) = \frac{n}{n^2+1}\frac{1}{e} \sim \frac{1}{en}$$
        qui est un terme général de série divergente.<br>
        Donc la série de fonctions $\displaystyle \sum_{n\geq 0} f_n$ ne converge pas normalement sur $\mathbb R_+$.
      </li>
      <li>
        Lorsque $\displaystyle n\geq \frac1A$, $f_n$ est décroissante sur $[A,+\infty[$ et on a alors
        $$\sup_{x\in[A,+\infty[} |f_n(x)| = f_n(A) = \frac{n^2}{n^2+1}A\exp(-nA) \sim A\exp(-nA)$$
        terme général d'une série convergente.<br>
        Donc la série de fonctions $\displaystyle \sum_{n\geq 0} f_n$ converge normalement sur tout $[A,+\infty[$ avec $A>0$.
      </li>
    </ol>
</details>

---
