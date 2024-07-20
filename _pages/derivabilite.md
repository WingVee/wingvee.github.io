---
layout: default
title: Dérivabilité
permalink: derivabilite
redirect_from:
  - derivabilité
---

---

<h3 id="fonctions-a-derivees-bornees-2">
  <a href="#fonctions-a-derivees-bornees-2" class="header">
  Une fonction bornée à dérivée seconde bornée a une dérivée bornée</a>
</h3>

Soit $\ f:\mathbb{R}\to\mathbb{R}$ une fonction de classe $\mathcal{C}^2$ telle que $f$ et $f''$ sont bornées sur $\mathbb{R}$ par des constantes $M_0$ et $M_2$.<br>
Montrer que $f'$ est bornée sur $\mathbb{R}$ par une constante $M_1 = 2\sqrt{M_0M_2}$.<br><br>
Reformulé autrement, en notant $\displaystyle \Vert f\Vert_{\infty} = \sup_{x\in\mathbb{R}}\vert f(x)\vert$ ($\in\mathbb{R}_+\cup\\\{+\infty\\}$ a priori), on a l'implication suivante :

$$\Big(\Vert f\Vert_{\infty} \leq M_0 \text{ et } \Vert f''\Vert_{\infty} \leq M_2\Big) \implies \Vert f'\Vert_{\infty} \leq 2\sqrt{M_0M_2}.$$

<details>
	<summary><b>Remarques</b></summary>
		Plus généralement, on peut montrer que si $f$ est de classe $\mathcal{C}^n$ et que $f$ et $f^{(n)}$ sont bornées sur $\mathbb{R}$, alors $f^{(k)}$ est bornée sur $\mathbb{R}$ pour tout $k\in\{0,\ldots,n\}$. Cela est traité dans <a href="espaces-vectoriels-normes#fonctions-a-derivees-bornees">cet exercice</a>.<br><br>
    Pour la culture générale, on peut citer l'<a href="https://en.wikipedia.org/wiki/Landau–Kolmogorov_inequality" target="_blank">inégalité de Landau-Kolmogorov</a> qui est une généralisation de ce résultat : si $f$ est de classe $\mathcal{C}^n(T,\mathbb{R})$ avec $T\subseteq\mathbb{R}$, alors, en notant $\displaystyle \Vert f\Vert_{\infty} = \sup_{x\in T}\vert f(x)\vert$ ($\in\mathbb{R}_+\cup\{+\infty\}$ a priori), on a l'inégalité suivante pour tout $1\leq k < n$ :
    $$\Vert f^{(k)}\Vert_{\infty} \leq C(n,k,T) \cdot \Vert f\Vert^{1-k/n}_{\infty} \cdot \Vert f^{(n)}\Vert^{k/n}_{\infty} \quad\text{avec}\quad C(n,k,T)\in\mathbb{R}_+.$$
    Dans cet exercice, on a montré que, pour $T = \mathbb{R}$, $n = 2$, $k = 1$, $C(2,1,\mathbb{R}) = 2$ convient. Mais la constante optimale est $C(2,1,\mathbb{R}) = \sqrt{2}$. Néanmoins, on a $C(2,1,[c,+∞[) = 2$ pour tout $c\in\mathbb R$.
</details>

<details>
	<summary><b>Indications</b></summary>
		Utiliser la formule de Taylor-Lagrange.
</details>

<details>
	<summary><b>Solution</b></summary>
    Montrons que $|f'(x)| \leq 2\sqrt{M_0M_2}$ pour tout $x\in\mathbb{R}$.<br>
    Soit $x\in\mathbb{R}$. D'après la formule de Taylor-Lagrange, pour tout réel $y\neq x$, il existe $c\in\,]x,y[$ tel que
    $$f(y) = f(x) + f'(x)(y-x) + \frac12 f''(c)\cdot(y-x)^2.$$
    On a alors
    $$f'(x) = \frac{f(y) - f(x)}{y-x} - \frac12 f''(c)\cdot(y-x).$$
    Par inégalité triangulaire, on a
    $$|f'(x)| \leq \frac{1}{|y-x|}\cdot(|f(y)| + |f(x)|) + \frac12 |f''(c)|\cdot|y-x| \leq \frac{2M_0}{|y-x|} + \frac{M_2|y-x|}{2}.$$
    En posant $h = |y-x| > 0$, on a donc l'inégalité suivante vérifiée pour tout $h > 0$ :
    $$|f'(x)| \leq \frac{2M_0}{h} + \frac{M_2h}{2}.$$
    On cherche à minimiser la quantité $\displaystyle g(h) = \frac{2M_0}{h} + \frac{M_2h}{2}$ pour $h > 0$.<br>
    Une étude simple de fonction montre que $g$ est minimale en $\displaystyle h = 2\sqrt{\frac{M_0}{M_2}}$ et que $\displaystyle g\left(2\sqrt{\frac{M_0}{M_2}}\right) = 2\sqrt{M_0M_2}$.<br><br>
    Ainsi, on a bien $|f'(x)| \leq 2\sqrt{M_0M_2}$ pour tout $x\in\mathbb{R}$, i.e. $\Vert f'\Vert_{\infty} \leq 2\sqrt{M_0M_2}$.
</details>

<details>
  <summary><b>Pour aller plus loin</b></summary>
    <ul>
      <li>
				<a href="espaces-vectoriels-normes#fonctions-a-derivees-bornees">Fonctions à dérivées bornées (autour de l'inégalité de Landau–Kolmogorov)</a>
      </li>
    </ul>
</details>

---
