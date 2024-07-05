---
layout: default
title: Calculs algébriques et trigonométrie
permalink: calculs-algebriques-et-trigonometrie
redirect_from:
  - calculs-algébriques-et-trigonométrie
---

---

<h3 id="formules-de-faulhaber-123">
  <a href="#formules-de-faulhaber-123" class="header">
  Formules de Faulhaber (exposants 1,2,3)</a>
</h3>

Les <a href="https://fr.wikipedia.org/wiki/Formule_de_Faulhaber" target="_blank">formules de Faulhaber</a> expriment les sommes des puissances $j$-èmes des entiers de $1$ à $n$ sous forme de fonction polynomiale en $n$ (de degré $j+1$), i.e. il existe des coefficients réels $a_0,a_1,\ldots,a_{j+1}$ tels que :

$$1^j + 2^j + \ldots + n^j = a_0 + a_1n + a_2n^2 + \ldots + a_{j+1}n^{j+1}.$$

Montrer les formules de Faulhaber pour les exposants $j=1,2,3$ :

1. $\displaystyle\sum_{k=1}^n k = \frac{n(n+1)}{2}$.
2. $\displaystyle\sum_{k=1}^n k^2 = \frac{n(n+1)(2n+1)}{6}$.
3. $\displaystyle\sum_{k=1}^n k^3 = \left(\frac{n(n+1)}{2}\right)^2$.

Remarque : $\displaystyle\sum_{k=1}^n k^3 = \left(\sum_{k=1}^n k\right)^2$ (identité de Nicomaque).

<details>
  <summary><b>Indications</b></summary>
    <details>
      <summary><u>Indication solution 1</u></summary>
        Faire une récurrence.
    </details>
    <details>
      <summary><u>Indication solution 2</u></summary>
        Visualiser géométriquement.
    </details>
</details>

<details>
  <summary><b>Solution 1</b></summary>
    Montrons les formules de Faulhaber par récurrence sur $n\in\mathbb{N}^*$.<br>
    <li>
      <u>Initialisation :</u><br>
      Pour $n=1$, on a
      <ol>
        <li>$\displaystyle\sum_{k=1}^1 k = 1 = \frac{1(1+1)}{2}$.</li>
        <li>$\displaystyle\sum_{k=1}^1 k^2 = 1 = \frac{1(1+1)(2\cdot 1+1)}{6}$.</li>
        <li>$\displaystyle\sum_{k=1}^1 k^3 = 1 = \left(\frac{1(1+1)}{2}\right)^2$.</li>
      </ol>
      Donc les formules de Faulhaber sont vraies pour $n=1$.
    </li>
    <li>
      <u>Hérédité :</u><br>
      Supposons que les formules de Faulhaber soient vraies pour un certain $n\in\mathbb{N}^*$.<br>
      Montrons-les pour $n+1$.
      <ol>
        <li>
          Pour l'exposant $j=1$, on a
          $$\begin{align*}
            \sum_{k=1}^{n+1} k &= \left(\sum_{k=1}^n k\right) + (n+1)\\
            &= \frac{n(n+1)}{2} + (n+1) \qquad \text{(par hypothèse de récurrence)}\\
            &= \frac{n(n+1) + 2(n+1)}{2}\\
            &= \frac{(n+1)(n+2)}{2}.
          \end{align*}$$
          D'où l'hérédité et la récurrence.
        </li>
        <li>
          Pour l'exposant $j=2$, on a
          $$\begin{align*}
            \sum_{k=1}^{n+1} k^2 &= \left(\sum_{k=1}^n k^2\right) + (n+1)^2\\
            &= \frac{n(n+1)(2n+1)}{6} + (n+1)^2 \qquad \text{(par hypothèse de récurrence)}\\
            &= \frac{n(n+1)(2n+1) + 6(n+1)^2}{6}\\
            &= \frac{(n+1)(n(2n+1)+6(n+1))}{6}\\
            &= \frac{(n+1)(2n^2+7n+6)}{6}\\
            &= \frac{(n+1)(n+2)(2n+3)}{6}.
          \end{align*}$$
          D'où l'hérédité et la récurrence.
        </li>
        <li>
          Pour l'exposant $j=3$, on a
          $$\begin{align*}
            \sum_{k=1}^{n+1} k^3 &= \left(\sum_{k=1}^n k^3\right) + (n+1)^3\\
            &= \left(\frac{n(n+1)}{2}\right)^2 + (n+1)^3 \qquad \text{(par hypothèse de récurrence)}\\
            &= \frac{n^2(n+1)^2}{4} + (n+1)^3\\
            &= \frac{n^2(n+1)^2 + 4(n+1)^3}{4}\\
            &= \frac{(n+1)^2(n^2+4(n+1))}{4}\\
            &= \frac{(n+1)^2(n^2+4n+4)}{4}\\
            &= \frac{(n+1)^2(n+2)^2}{4}.
          \end{align*}$$
          D'où l'hérédité et la récurrence.
        </li>
      </ol>
    </li>
    Ce qui conclut la preuve par récurrence.
</details>

<details>
  <summary><b>Solution 2</b></summary>
    Preuve (presque) sans mots, par visualisation géométrique.<br>
    <ol>
      <li>
        $\displaystyle S_1 = \sum_{k=1}^n k = \frac{n(n+1)}{2}$<br>
        Ici, avec $n=6$ : $S_1 = 1+2+3+4+5+6$
        <p align="center" style="font-size: 3em; line-height: 0.6em">
        ■□□□□□□ <br>
        ■■□□□□□ <br>
        ■■■□□□□ <br>
        ■■■■□□□ <br>
        ■■■■■□□ <br>
        ■■■■■■□ <br>
        </p>
        $S_1+S_1$ forme un rectangle de longueur $n+1=7$ et de largeur $n=6$.<br>
        Donc $2S_1 = n(n+1)$ d'où $\displaystyle S_1 = \frac{n(n+1)}{2}$.<br><br>
        Voici de plus la preuve de Gauss (quand il était enfant selon la légende) :
        <p align="center">
        <img src="https://upload.wikimedia.org/wikipedia/commons/2/28/Animated_proof_for_the_formula_giving_the_sum_of_the_first_integers_1%2B2%2B...%2Bn.gif" alt="Somme des entiers" width="400"/>
        </p>
        $$\begin{array}{lr*{10}{c}}
        S_1 &=& 1 & + & 2 & + & \cdots & + & n-1 & + & n\\
        S_1 &=& n & + & n-1 & + & \cdots & + & 2 & + & 1\\
        S_1+S_1 &=& n+1 & + & n+1 & + & \cdots & + & n+1 & + & n+1
        \end{array}$$
        Donc $2S_1 = n(n+1)$ d'où $\displaystyle S_1 = \frac{n(n+1)}{2}$.<br><br>
      </li>
      <li>
        $\displaystyle S_2 = \sum_{k=1}^n k^2 = \frac{n(n+1)(2n+1)}{6}$<br>
        <p align="center">
        <img src="https://upload.wikimedia.org/wikipedia/commons/9/9d/Somme-des-carrés_%28cl%29.jpg" alt="Somme des carrés" width="400"/>
        </p>
        $3S_2$ forme un parallépipède de dimensions $n$, $n+1$ et $\displaystyle n+\frac12$.<br>
        Donc $\displaystyle 3S_2 = n(n+1)\left(n+\frac12\right)$ d'où $\displaystyle S_2 = \frac{n(n+1)(2n+1)}{6}$.<br><br>
      </li>
      <li>
        $\displaystyle S_3 = \sum_{k=1}^n k^3 = \left(\sum_{k=1}^n k\right)^2 = S_1^2$
        <p align="center">
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/2/26/Nicomachus_theorem_3D.svg/1280px-Nicomachus_theorem_3D.svg.png" alt="Somes des cubes" width="400"/>
        </p>
      </li>
    </ol>
</details>

---
