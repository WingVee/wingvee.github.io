---
layout: default
title: Calculs algébriques et trigonométrie
permalink: calculs-algebriques-et-trigonometrie
redirect_from:
  - calculs-algébriques-et-trigonométrie
---

---

<h3 id="moyennes-arithmetique-geometrique-harmonique-quadratique">
  <a href="#moyennes-arithmetique-geometrique-harmonique-quadratique" class="header">
  Moyennes arithmétique, géométrique, harmonique et quadratiques de deux nombres</a>
</h3>

Soient $a$ et $b$ deux nombres réels strictement positifs.

- La moyenne arithmétique de $a$ et $b$ est $A = \displaystyle\frac{a+b}{2}.$

- La moyenne géométrique de $a$ et $b$ est $G = \displaystyle\sqrt{ab}.$

- La moyenne harmonique de $a$ et $b$ est $H = \displaystyle\frac{2}{\frac{1}{a}+\frac{1}{b}}.$

- La moyenne quadratique de $a$ et $b$ est $Q = \displaystyle\sqrt{\frac{a^2+b^2}{2}}.$

<ol>
  <li>
    Montrer que $G^2 = AH.$
  </li>
  <li>
    Montrer que $\displaystyle A^2 = \frac{G^2+Q^2}{2}.$
  </li>
  <li>
    Montrer que $\min(a,b) \leq H \leq G \leq A \leq Q \leq \max(a,b).$
  </li>
  <li>
    Montrer que chaque inégalité est une égalité si et seulement si $a=b$.
  </li>
</ol>

Ainsi, on a

$$\min(a,b) \leq \frac{2}{\frac{1}{a}+\frac{1}{b}} \leq \sqrt{ab} \leq \frac{a+b}{2} \leq \sqrt{\frac{a^2+b^2}{2}}$$

avec égalité si et seulement si $a=b$.

<details>
  <summary><b>Remarques</b></summary>
    Ces moyennes sont généralisables à $n$ nombres réels strictement positifs $a_1,\ldots,a_n$ :
    $$A = \frac{a_1+\ldots+a_n}{n},\quad G = \sqrt[n]{a_1\ldots a_n},\quad H = \frac{n}{\frac{1}{a_1}+\ldots+\frac{1}{a_n}},\quad Q = \sqrt{\frac{a_1^2+\ldots+a_n^2}{n}}.$$
    Les égalités des questions 1. et 2. sont fausses en général pour $n>2$, mais les inégalités restent vraies :
    $$\min(a_1,\ldots,a_n) \leq H \leq G \leq A \leq Q \leq \max(a_1,\ldots,a_n).$$
    C'est-à-dire :
    $$\min(a_1,\ldots,a_n) \leq \frac{n}{\frac{1}{a_1}+\ldots+\frac{1}{a_n}} \leq \sqrt[n]{a_1\ldots a_n} \leq \frac{a_1+\ldots+a_n}{n} \leq \sqrt{\frac{a_1^2+\ldots+a_n^2}{n}} \leq \max(a_1,\ldots,a_n).$$
    Voici une visualisation géométrique des moyennes arithmétique, géométrique, harmonique et quadratique :
    <p align="center">
    <img src="https://upload.wikimedia.org/wikipedia/commons/c/cc/Inegalites_moyennes.gif" alt="Diagramme de Venn de la différence symétrique" width="400"/>
    </p>
    De plus, on peut démontrer la formule $\displaystyle A^2 = \frac{G^2+Q^2}{2}$ à partir de ce dessin et en utilisant le théorème de Pythagore plusieurs fois :
    $$A^2 + OK^2 = Q^2,\quad G^2 + OK^2 = (OP+H)^2 = A^2.$$
    Pour finir, voici une preuve géométriques des inégalités :
    $$\min(a,b) \leq H = \frac{2}{\frac{1}{a}+\frac{1}{b}} \leq \sqrt{ab} = G \leq \frac{a+b}{2} = A \leq \sqrt{\frac{a^2+b^2}{2}} = Q \leq \max(a,b).$$
    <p align="center">
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/a1/QM_AM_GM_HM_inequality_visual_proof.svg/1920px-QM_AM_GM_HM_inequality_visual_proof.svg.png" alt="Diagramme de Venn de la différence symétrique" width="400"/>
    </p>
</details>

<details>
  <summary><b>Indications</b></summary>
    Pour la question 3., commencer par la dernière inégalité et montrer que $Q \leq \max(a,b)$, puis $A \leq Q$ etc.
</details>

<details>
  <summary><b>Solution</b></summary>
    <ol>
      <li>
        $\displaystyle AH = \frac{a+b}{2}\frac{2}{\frac{1}{a}+\frac{1}{b}} = \frac{a+b}{\frac{a+b}{ab}} = ab = G^2$.
      </li>
      <li>
        $\displaystyle G^2+Q^2 = ab + \frac{a^2+b^2}{2} = \frac{2ab+a^2+b^2}{2} = 2\frac{(a+b)^2}{4} = 2A^2$.
      </li>
      <li>
        $\bullet\ Q \leq \max(a,b)$ :
        $$Q = \sqrt{\frac{a^2+b^2}{2}} \leq \sqrt{\frac{\max(a^2,b^2)+\max(a^2,b^2)}{2}} = \sqrt{\max(a^2,b^2)} = \sqrt{\max(a,b)^2} = \max(a,b).$$
        $\bullet\ A \leq Q$ :
        $$A \leq Q \iff A^2 \leq Q^2 \iff \frac{a^2+2ab+b^2}{4} \leq \frac{a^2+b^2}{2} \iff 0 \leq a^2-2ab+b^2 = (a-b)^2.$$
        $\bullet\ G \leq A$ :
        $$G \leq A \iff G^2 \leq A^2 \iff ab \leq \frac{a^2+2ab+b^2}{4} \iff 0 \leq a^2-2ab+b^2 = (a-b)^2.$$
        $\bullet\ H \leq G$ :
        $$H \leq G \iff \frac{2ab}{a+b} \leq \sqrt{ab} \iff \sqrt{ab} \leq \frac{a+b}{2} \iff G \leq A.$$
        On pouvait aussi utiliser la question 1. :
        $$\displaystyle H \leq G \iff \frac{G^2}{A} \leq G \iff G \leq A.$$
        $\bullet\ \min(a,b) \leq H$ :
        $$\min(a,b) \leq H = \frac{2}{\frac{1}{a}+\frac{1}{b}} \iff \frac{\frac{1}{a}+\frac{1}{b}}{2} \leq \frac{1}{\min(a,b)} = \max\left(\frac1a,\frac1b\right) \iff \frac{a'+b'}{2} \leq \max(a',b')$$
        avec $a' = \frac1a$ et $b' = \frac1b$ des nombres réels strictement positifs, et on invoque l'inégalité $A\leq\max(a,b)$.
      </li>
      <li>
        D'après les preuves de la question 3, on voit que chaque inégalité est une égalité si et seulement si $a=b$ :<br>
        $\bullet\ Q = \max(a,b) \iff a^2+b^2 = 2\max(a^2,b^2) \iff a^2 = b^2 \iff a=b$ ($a,b>0$).<br>
        $\bullet\ A = Q \iff (a-b)^2 = 0 \iff a=b$.<br>
        $\bullet\ G = A \iff (a-b)^2 = 0 \iff a=b$.<br>
        $\bullet\ H = G \iff G = A \iff a=b$.<br>
        $\bullet\ \displaystyle \min(a,b) = H \iff \frac{\frac1a+\frac1b}{2} = \max\left(\frac1a,\frac1b\right) \iff \frac1a = \frac1b \iff a=b$.
      </li>
    </ol>
</details>

---

<h3 id="troisieme-identite-remarquable-generalisee">
  <a href="#troisieme-identite-remarquable-generalisee" class="header">
  Troisième identité remarquable généralisée - Différence de puissances $n$-ièmes</a>
</h3>

<ol>
  <li>
    Montrer que pour tous nombres réels $a$ et $b$, on a
    $$a^{3}-b^{3}=(a-b)(a^{2}+ab+b^{2})\\a^{3}+b^{3}=(a+b)(a^{2}-ab+b^{2}).$$
  </li>
  <li>
    Plus généralement, montrer que pour tous nombres réels $a$ et $b$ et tout entier naturel $n$, on a
    $$a^{n}-b^{n}=(a-b)\left(a^{n-1}+a^{n-2}b+a^{n-3}b^{2}+\ldots+ab^{n-2}+b^{n-1}\right)=(a-b)\sum_{k=0}^{n-1}a^{n-1-k}b^{k}.$$
  </li>
  <li>
    Montrer que pour tout entier $n$ impair, on a
    $$a^{n}+b^{n}=(a+b)\left(a^{n-1}-a^{n-2}b+a^{n-3}b^{2}-\ldots+ab^{n-2}-b^{n-1}\right)=(a+b)\sum_{k=0}^{n-1}(-1)^{k}a^{n-1-k}b^{k}.$$
  </li>
</ol>

<details>
  <summary><b>Remarques</b></summary>
    Ces identités généralisent celle bien connue pour $n=2$ : $a^2-b^2=(a-b)(a+b)$.<br>
    De plus, ces formules sont vraies pour $a$ et $b$ dans $\mathbb{C}$, ou plus généralement dans un anneau commutatif (en gros une structure algébrique où l'on peut additionner et multiplier, avec la distributivité et la commutativité) ou dans un anneau quelconque où $a$ et $b$ commutent.
</details>

<details>
  <summary><b>Solution</b></summary>
    <ol>
      <li>
        On développe les produits :
        $$\begin{align*}
          (a-b)(a^{2}+ab+b^{2}) &= a^{3}+a^{2}b+ab^{2}-a^{2}b-ab^{2}-b^{3}\\
          &= a^{3}-b^{3}.
        \end{align*}$$
        $$\begin{align*}
          (a+b)(a^{2}-ab+b^{2}) &= a^{3}-a^{2}b+ab^{2}+a^{2}b-ab^{2}-b^{3}\\
          &= a^{3}+b^{3}.
        \end{align*}$$
      </li>
      <li>
        On développe :
        $$\begin{align*}
          (a-b)\sum_{k=0}^{n-1}a^{n-1-k}b^{k} &= \sum_{k=0}^{n-1}a^{n-k}b^{k}-\sum_{k=0}^{n-1}a^{n-1-k}b^{k+1}\\
          &= \sum_{k=0}^{n-1}a^{n-k}b^{k} - \sum_{k=1}^{n}a^{n-k}b^{k}\\
          &= a^{n}b^{0}+a^{n-1}b^{1}+\ldots+a^{1}b^{n-1} - a^{n-1}b^{1}-\ldots-a^{1}b^{n-1}-a^{0}b^{n}\\
          &= a^{n}-b^{n}.
        \end{align*}$$
      </li>
      <li>
        Lorque $n$ est impair, on remplace $b$ par $-b$ dans la formule précédente :
        $$a^{n}+b^{n} = a^n-(-b)^n = (a-(-b))\sum_{k=0}^{n-1}a^{n-1-k}(-b)^{k} = (a+b)\sum_{k=0}^{n-1}(-1)^{k}a^{n-1-k}b^{k}.$$
      </li>
    </ol>
</details>

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
