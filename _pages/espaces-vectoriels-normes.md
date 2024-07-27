---
layout: default
title: Espaces vectoriels normés
permalink: espaces-vectoriels-normes
redirect_from:
  - espaces-vectoriels-normés
  - espaces-normes
  - espaces-normés
  - evn
---

---

<h3 id="fonctions-a-derivees-bornees">
  <a href="#fonctions-a-derivees-bornees" class="header">
  Fonctions à dérivées bornées (autour de l'inégalité de Landau–Kolmogorov)</a>
</h3>

Soit $\ f:\mathbb{R}\to\mathbb{R}$ une fonction de classe $\mathcal{C}^n$ telle que $\ f$ et $\ f^{(n)}$ sont bornées sur $\mathbb{R}$.<br>
L'objectif de l'exercice est de montrer que $\ f^{(k)}$ est bornée sur $\mathbb{R}$ pour tout $k\in\\{0,\ldots,n\\}$.

Autrement dit, en notant $\displaystyle \Vert f\Vert_{\infty} = \sup_{x\in\mathbb{R}}\vert f(x)\vert$ ($\in\mathbb{R}_+\cup\\{+\infty\\}$ a priori), on a l'implication suivante :

$$\Big(\Vert f\Vert_{\infty} < +\infty \text{ et } \Vert f^{(n)}\Vert_{\infty} < +\infty\Big) \implies \forall k\in\{0,\ldots,n\},\ \Vert f^{(k)}\Vert_{\infty} < +\infty.$$

<ol>
  <li>
    Considérons $\mathbb{R}_{n-1}[X]$ l'espace vectoriel des polynômes réels de degré inférieur ou égal à $n-1$.<br>
    Pour $P = \displaystyle\sum_{k=0}^{n-1} a_kX^k\in\mathbb{R}_{n-1}[X]$ et $\delta > 0$, on pose
    $$N_1(P) = \max_{0\leq k\leq n-1}\vert a_k\vert \quad\text{et}\quad N_2(P) = \sup_{0\leq h\leq \delta}\vert P(h)\vert.$$
    Montrer que $N_1$ et $N_2$ sont des normes sur $\mathbb{R}_{n-1}[X]$ et qu'elles sont équivalentes.
  </li>
  <li>
    Soit $x\in\mathbb{R}$. Posons
    $$P_{x}(h)=\sum_{k=0}^{n-1}f^{(k)}(x)\frac{h^{k}}{k!}.$$
    Montrer que pour tout $x\in\mathbb{R}$ et $\delta > 0$, on a
    $$N_2(P_{x})\leq\Vert f\Vert_{\infty}+\Vert f^{(n)}\Vert_{\infty}\frac{\delta^{n}}{n!}.$$
  </li>
  <li>
    Conclure. (Question bonus : est-ce que la preuve est valable pour $\delta = 0$ ?)
  </li>
</ol>

**Source** : <a href="https://les-mathematiques.net/vanilla/discussion/331165/fonctions-a-derivees-bornees" target="_blank">CQFD</a>

<details>
	<summary><b>Remarques</b></summary>
		Pour la culture générale, on peut citer l'<a href="https://en.wikipedia.org/wiki/Landau–Kolmogorov_inequality" target="_blank">inégalité de Landau-Kolmogorov</a> qui est une généralisation de ce résultat : si $f$ est de classe $\mathcal{C}^n(T,\mathbb{R})$ avec $T\subseteq\mathbb{R}$, alors, en notant $\displaystyle \Vert f\Vert_{\infty} = \sup_{x\in T}\vert f(x)\vert$ ($\in\mathbb{R}_+\cup\{+\infty\}$ a priori), on a l'inégalité suivante pour tout $1\leq k < n$ :
    $$\Vert f^{(k)}\Vert_{\infty} \leq C(n,k,T) \cdot \Vert f\Vert^{1-k/n}_{\infty} \cdot \Vert f^{(n)}\Vert^{k/n}_{\infty} \quad\text{avec}\quad C(n,k,T)\in\mathbb{R}_+.$$
    Dans <a href="derivabilite#fonctions-a-derivees-bornees-2">cet exercice</a>, on montre que, pour $T = \mathbb{R}$, $n = 2$, $k = 1$, $C(2,1,\mathbb{R}) = 2$ convient. Mais la constante optimale est $C(2,1,\mathbb{R}) = \sqrt{2}$. Néanmoins, on a $C(2,1,[c,+∞[) = 2$ pour tout $c\in\mathbb R$.
</details>

<details>
  <summary><b>Indications</b></summary>
    2. Utiliser la formule de Taylor-Lagrange.
</details>

<details>
  <summary><b>Solution</b></summary>
    <ol>
      <li>
        Pour $N_1$, la séparation et l'absolue homogénéité sont claires.<br>
        Pour l'inégalité triangulaire, si $\displaystyle P = \sum_{k=0}^{n-1} a_kX^k$ et $\displaystyle Q = \sum_{k=0}^{n-1} b_kX^k$ sont dans $\mathbb{R}_{n-1}[X]$, alors $\displaystyle |a_k + b_k| \leq |a_k| + |b_k| \leq N_1(P) + N_1(Q)$ pour tout $0\leq k\leq n-1$.<br>
        Donc, $\displaystyle N_1(P + Q) = \max_{0\leq k\leq n-1} |a_k + b_k| \leq N_1(P) + N_1(Q)$.<br><br>
        Pour $N_2$, l'absolue homogénéité et l'inégalité triangulaire sont claires.<br>
        Pour la séparation, si $\displaystyle \sup_{0\leq h\leq \delta} |P(h)| = 0$, alors $\displaystyle P(h) = 0$ pour tout $h\in[0,\delta]$ et donc $P=0$ car un polynôme ayant une infinité de racines est le polynôme nul.<br><br>
        Donc, $N_1$ et $N_2$ sont des normes sur $\mathbb{R}_{n-1}[X]$ qui est un espace vectoriel de dimension finie, donc toutes les normes sont équivalentes.
      </li>
      <li>
        Soit $x\in\mathbb{R}$. D'après la formule de Taylor-Lagrange, pour tout $h\in [0,\delta]$, il existe $c\in[x,x+h]$ tel que
        $$\begin{align*}
        f(x+h) &= f(x) + f'(x)h + \dots + \frac{f^{(n-1)}(x)}{(n-1)!}h^{n-1} + \frac{f^{(n)}(c)}{n!}h^n\\
        &= \sum_{k=0}^{n-1} \frac{f^{(k)}(x)}{k!}h^k + \frac{f^{(n)}(c)}{n!}h^n\\
        &= P_x(h) + \frac{f^{(n)}(c)}{n!}h^n.
        \end{align*}$$
        Donc, puisque $h\in [0,\delta]$, on a
        $$|P_x(h)| = \left|f(x+h) - \frac{f^{(n)}(c)}{n!}h^n\right| \leq \left|f(x+h)\right| + \left|\frac{f^{(n)}(c)}{n!}h^n\right| \leq \Vert f\Vert_{\infty} + \Vert f^{(n)}\Vert_{\infty}\frac{\delta^n}{n!}.$$
        Ainsi,
        $$N_2(P_x) \leq \Vert f\Vert_{\infty} + \Vert f^{(n)}\Vert_{\infty}\frac{\delta^n}{n!}.$$
      </li>
      <li>
        Notons $\displaystyle M = \Vert f\Vert_{\infty} + \Vert f^{(n)}\Vert_{\infty}\frac{\delta^n}{n!} \in\mathbb{R}_+$.<br>
        Alors, d'après la question précédente, on a $\displaystyle N_2(P_x) \leq M$ pour tout $x\in\mathbb{R}$.<br>
        Puisque $N_1$ et $N_2$ sont équivalentes, on a $\displaystyle N_1(P_x) \leq C\cdot N_2(P_x) \leq C\cdot M$ pour un certain $C\in\mathbb{R}_+$.<br>
        Cela signifie que pour tout $k\in\{0,\ldots,n-1\}$ et $x\in\mathbb{R}$, on a $\displaystyle \left|\frac{f^{(k)}(x)}{k!}\right| \leq C\cdot M$.<br>
        Ainsi,
        $$\Vert f^{(k)}\Vert_{\infty} \leq C\cdot M\cdot k! < +\infty \quad\text{pour tout } k\in\{0,\ldots,n-1\}.$$
        D'où le résultat.<br><br>
        Si $\delta = 0$, alors $N_2$ n'est pas une norme car ne vérifie pas la propriété de séparation. (De plus, cela vaudrait dire qu'on n'aurait pas besoin de l'hypothèse de $\ f^{(n)}$ bornée avec la question 2.)
      </li>
    </ol>
</details>

<details>
  <summary><b>Pour aller plus loin</b></summary>
    <ul>
      <li>
				<a href="derivabilite#fonctions-a-derivees-bornees-2">Une fonction bornée à dérivée seconde bornée a une dérivée bornée</a>
      </li>
      <li>
				<a href="oraux-pc#beos-7413">X-ESPCI 2023 - Suite de fonctions et convergence uniforme des dérivées vers 0</a>
      </li>
    </ul>
</details>

---
