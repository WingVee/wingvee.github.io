---
layout: default
title: Oraux PC
permalink: oraux-pc
redirect_from:
  - oraux-pcsi
---

---

<h3 id="beos-5473">
  <a href="#beos-5473" class="header">
  X-ESPCI 2019 - Déterminant de l'application transposée</a>
</h3>

[Exercice traité ici.](determinants#determinant-application-transposee)

**Mots-clés** : déterminant

**Source** : <a href="https://beos.prepas.org/sujet.php?id=5473" target="_blank">BEOS 5473</a>

---

<h3 id="beos-6933-2">
  <a href="#beos-6933-2" class="header">
  X-ESPCI 2022 - Équivalent de la partie fractionnaire de $n!e$</a>
</h3>

[Exercice traité ici.](calculs-asymptotiques#equivalent-partie-fractionnaire-n-e)

**Mots-clés** : calculs asymptotiques

**Source** : <a href="https://beos.prepas.org/sujet.php?id=6933" target="_blank">BEOS 6933</a>

---

<h3 id="beos-8252">
  <a href="#beos-8252" class="header">
  CCINP 2024 - Étude de $\displaystyle \sum_{n=1}^{+\infty} \frac{n^2}{n^2+1} x \exp(-nx)$</a>
</h3>

[Exercice traité ici.](suites-et-series-de-fonctions#etude-serie-fonctions-1)

**Mots-clés** : séries de fonctions

**Source** : <a href="https://beos.prepas.org/sujet.php?id=8252" target="_blank">BEOS 8252</a>

---

<h3 id="beos-7214-1">
  <a href="#beos-7214-1" class="header">
  X-ESPCI 2023 - Vitesse de convergence d'une suite récurrente</a>
</h3>

On définit une suite réelle $(u_n)\_{n \in \mathbb{N}}$ par $u_0 > 0$ et la relation de récurrence $u_{n+1} = u_n - e^{-\frac 1{u_n}}$.

1. Montrer que cette suite est bien définie, puis qu'elle converge. Préciser sa limite.
2. Pour tout $\alpha > 0$, montrer que la suite $(n^{\alpha} u_n)_{n \in \mathbb{N}^*}$ tend vers $+\infty$.

**Mots-clés** : suite récurrente, calculs asymptotiques

**Source** : <a href="https://beos.prepas.org/sujet.php?id=7214" target="_blank">BEOS 7214</a>

<details>
  <summary><b>Remarques</b></summary>
    Ce résultat découle du résultat plus général traité dans <a href="calculs-asymptotiques#vitesse-de-convergence-suite-recurrente">cet exercice</a>.
</details>

<details>
  <summary><b>Indications</b></summary>
    <ol>
      <li>Écrire $u_{n+1} = f(u_n)$ et étudier $f$.</li>
      <li>Montrer qu'il s'agit d'obtenir $\displaystyle \frac{1}{u_n^{1/\alpha}} = o(n)$.<br>
      Montrer que $\displaystyle \frac{1}{u_{n+1}^{1/\alpha}} = \frac{1}{u_n^{1/\alpha}} + o(u_n^{\beta-1/\alpha})$ pour tout $\beta > 0$.</li>
    </ol>
</details>

<details>
  <summary><b>Solution</b></summary>
    <ol>
      <li>
        <u>Bonne définition de la suite :</u><br>
        Posons $f(x) = x - e^{-\frac 1{x}}$ définie sur $\mathbb{R}_+^*$.<br>
        Soit $x > 0$. On a
        $$\begin{align*}
        f(x) > 0 &\iff x > e^{-\frac 1{x}}\\
        &\iff \ln(x) > -\frac 1{x}\\
        &\iff -\ln(x) < \frac 1{x}\\
        &\iff \ln\left(\frac 1x\right) < \frac 1x.
        \end{align*}$$
        Or, l'inégalité $\ln(y) \leq y-1 < y$ est vérifiée pour tout $y > 0$, donc $\ln\left(\frac 1x\right) < \frac 1x$ pour tout $x > 0$.<br>
        Ainsi, $u_{n+1} = f(u_n)$ est bien définie pour tout $n\in\mathbb{N}$ car $u_0 > 0$ et $\ f(x) > 0$ pour tout $x > 0$.<br><br>
        <u>Convergence de la suite et limite :</u><br>
        On a $u_{n+1} - u_n = -e^{-\frac 1{u_n}} < 0$, donc $(u_n)$ est (strictement) décroissante.<br>
        Ainsi, la suite $(u_n)$ est décroissante et minorée par $0$, donc elle converge vers une limite $\ell\geq 0$.<br>
        On remarque que $\ f$ est continue sur $\mathbb{R}_+^*$ et est prolongeable par continuité en $0$ en posant $f(0) = 0$.<br>
        Par continuité de $\ f$ (sur $\mathbb R$), on a $\ell = f(\ell)$. Or, $f(x) < x$ pour tout $x > 0$, donc $\ell = 0$.<br>
        Donc $u_n \underset{n\to+\infty}{\longrightarrow} 0$.
      </li>
      <li>
        Soit $\alpha > 0$. On a l'équivalence suivante (avec $u_n > 0$) :
        $$\begin{align*}
        n^{\alpha}u_n \xrightarrow[n\to +\infty]{} +\infty &\iff \frac{1}{n^{\alpha}u_n} \xrightarrow[n\to +\infty]{} 0\\
        &\iff \frac{1}{n u_n^{1/\alpha}} \xrightarrow[n\to +\infty]{} 0\\
        &\iff \frac{1}{n u_n^{1/\alpha}} = o(1)\\
        &\iff \frac{1}{u_n^{1/\alpha}} = o(n).
        \end{align*}$$
        Nous allons démontrer cette dernière affirmation. Faisons un développement asymptotique :
        $$\begin{align*}
        \frac{1}{u_{n+1}^{1/\alpha}} &= \frac{1}{\left(u_n - e^{-\frac 1{u_n}}\right)^{1/\alpha}}\\
        &= \frac{1}{u_n^{1/\alpha}}\left(1 - \frac{1}{u_n}e^{-\frac 1{u_n}}\right)^{-1/\alpha}\\
        &= \frac{1}{u_n^{1/\alpha}}\left(1 + o(u_n^{\beta})\right)^{-1/\alpha}  \qquad \text{pour tout } \beta > 0\ (\text{croissances comparées})\\
        &=\frac{1}{u_n^{1/\alpha}} + o(u_n^{\beta-1/\alpha}).
        \end{align*}$$
        En choisissant $\beta = 1/\alpha$, on a $\displaystyle \frac{1}{u_{n+1}^{1/\alpha}} - \frac{1}{u_n^{1/\alpha}} = o(1)$, donc par télescopage :
        $$\frac{1}{u_n^{1/\alpha}} = \frac{1}{u_0^{1/\alpha}} + o(n) = o(n).$$
        Ce qui conclut la démonstration.
      </li>
    </ol>
</details>

<details>
  <summary><b>Pour aller plus loin</b></summary>
    <ul>
      <li>
        <a href="calculs-asymptotiques#vitesse-de-convergence-suite-recurrente">Vitesse de convergence d'une suite récurrente</a>
      </li>
    </ul>
</details>

---

<h3 id="beos-7413">
  <a href="#beos-7413" class="header">
  X-ESPCI 2023 - Suite de fonctions et convergence uniforme des dérivées vers 0</a>
</h3>

Soit $(f_n)_{n\in\mathbb{N}}$ une suite de fonctions de classe $\mathcal{C}^3$ sur $\mathbb{R}$ telle que :
- $\displaystyle \sup_{n\in\mathbb{N}}\left(\sup_{x\in\mathbb{R}}\vert f_n^{(3)}(x)\vert\right) \leq C$ avec $C\in\mathbb{R}_+$,
- $\displaystyle \sup_{x\in\mathbb{R}}\vert f_n(x)\vert \xrightarrow[n\to +\infty]{} 0$.

Montrer que $\displaystyle \sup_{x\in\mathbb{R}}\vert f_n^{(i)}(x)\vert \xrightarrow[n\to +\infty]{} 0$ pour $i\in\\{1,2\\}$.

**Mots-clés** : dérivabilité, calculs asymptotiques, suites de fonctions

**Source** : <a href="https://beos.prepas.org/sujet.php?id=7413" target="_blank">BEOS 7413</a>

<details>
  <summary><b>Remarques</b></summary>
    L'<a href="https://en.wikipedia.org/wiki/Landau–Kolmogorov_inequality" target="_blank">inégalité de Landau-Kolmogorov</a> permet de résoudre rapidement ce problème.<br>
    Elle stipule que si $\ f$ est de classe $\mathcal{C}^p(T,\mathbb{R})$ avec $T\subseteq\mathbb{R}$, alors, en notant $\displaystyle \Vert f\Vert_{\infty} = \sup_{x\in T}\vert f(x)\vert$ ($\in\mathbb{R}_+\cup\{+\infty\}$ a priori), on a l'inégalité suivante pour tout $1\leq k < p$ :
    $$\Vert f^{(k)}\Vert_{\infty} \leq C(p,k,T) \cdot \Vert f\Vert^{1-k/p}_{\infty} \cdot \Vert f^{(p)}\Vert^{k/p}_{\infty} \quad\text{avec}\quad C(p,k,T)\in\mathbb{R}_+.$$
    Ainsi, dans le cadre du problème, on a
    $$\Vert f_n'\Vert_{\infty} \leq C(3,1,\mathbb{R}) \cdot \Vert f_n\Vert^{2/3}_{\infty} \cdot \Vert f_n^{(3)}\Vert^{1/3}_{\infty}\leq C(3,1,\mathbb{R}) \cdot C^{1/3} \cdot \Vert f_n\Vert^{2/3}_{\infty} \xrightarrow[n\to +\infty]{}0 \quad\text{et}$$
    $$\Vert f_n''\Vert_{\infty} \leq C(3,2,\mathbb{R}) \cdot \Vert f_n\Vert^{1/3}_{\infty} \cdot \Vert f_n^{(3)}\Vert^{2/3}_{\infty}\leq C(3,2,\mathbb{R}) \cdot C^{2/3} \cdot \Vert f_n\Vert^{1/3}_{\infty} \xrightarrow[n\to +\infty]{}0.$$
</details>

<details>
  <summary><b>Indications</b></summary>
    On note $\displaystyle\Vert f\Vert_{\infty} = \sup_{x\in\mathbb{R}}\vert f(x)\vert \in\mathbb{R}_+\cup\{+\infty\}$.<br>
    Lemme : montrer que $\Vert f'\Vert_{\infty} \leq 2\sqrt{\Vert f\Vert_{\infty}\Vert f''\Vert_{\infty}}$ pour toute fonction $f$ de classe $\mathcal{C}^2$ sur $\mathbb{R}$ (cf. <a href="derivabilite#fonctions-a-derivees-bornees-2">cet exercice</a>).
</details>

<details>
  <summary><b>Solution</b></summary>
    On note $\displaystyle\Vert f\Vert_{\infty} = \sup_{x\in\mathbb{R}}\vert f(x)\vert \in\mathbb{R}_+\cup\{+\infty\}$.<br>
    Lemme : $\Vert f'\Vert_{\infty} \leq 2\sqrt{\Vert f\Vert_{\infty}\Vert f''\Vert_{\infty}}$ pour toute fonction $f$ de classe $\mathcal{C}^2$ sur $\mathbb{R}$ (cf. <a href="derivabilite#fonctions-a-derivees-bornees-2">cet exercice</a>).<br>
    Cela découle de la formule de Taylor-Lagrange. Pour $x\in\mathbb R$, pour tout réel $y\neq x$, il existe $c\in\,]x,y[$ tel que
    $$f(y) = f(x) + f'(x)(y-x) + \frac12\ f''(c)\cdot(y-x)^2.$$
    Donc, en posant $h = |y-x| > 0$, on a
    $$|f'(x)| = \left|\frac{f(y) - f(x)}{y-x} - \frac12 f''(c)\cdot(y-x)\right|\leq \frac{2\Vert f\Vert_{\infty}}{h} + \frac{\Vert f''\Vert_{\infty}h}{2}.$$
    En étudiant la fonction $\displaystyle g(h) = \frac{2\Vert f\Vert_{\infty}}{h} + \frac{\Vert f''\Vert_{\infty}h}{2}$ (en dérivant par exemple), on trouve que le minimum est atteint en $\displaystyle h = 2\sqrt{\frac{\Vert f\Vert_{\infty}}{\Vert f''\Vert_{\infty}}}$, et que $\displaystyle g(h) = 2\sqrt{\Vert f\Vert_{\infty}\Vert f''\Vert_{\infty}}$.
    D'où
    $$\Vert f'\Vert_{\infty} \leq 2\sqrt{\Vert f\Vert_{\infty}\Vert f''\Vert_{\infty}}.$$
    Reprenons le problème. En utilisant le lemme, on a
    $$\Vert f'\Vert_{\infty} \leq 2\sqrt{\Vert f\Vert_{\infty}\Vert f''\Vert_{\infty}} \leq 2\sqrt{\Vert f\Vert_{\infty}\cdot2\sqrt{\Vert f'\Vert_{\infty}\Vert f'''\Vert_{\infty}}} = 2^{3/2}\Vert f\Vert_{\infty}^{1/2}\Vert f'\Vert_{\infty}^{1/4}\Vert f'''\Vert_{\infty}^{1/4}.$$
    Donc, en utilisant les hypothèses du problème, on a
    $$\Vert f_n'\Vert_{\infty}^{3/4} \leq 2^{3/2}\Vert f_n\Vert_{\infty}^{1/2}\Vert f_n'''\Vert_{\infty}^{1/4} \leq 2^{3/2}C^{1/4}\Vert f_n\Vert_{\infty}^{1/2} \xrightarrow[n\to +\infty]{} 0.$$
    Donc $\Vert f_n'\Vert_{\infty} \xrightarrow[n\to +\infty]{} 0$. De même, on a
    $$\Vert f_n''\Vert_{\infty} \leq 2\sqrt{\Vert f_n'\Vert_{\infty}\Vert f_n'''\Vert_{\infty}} \leq 2C^{1/2}\sqrt{\Vert f_n'\Vert_{\infty}} \xrightarrow[n\to +\infty]{} 0.$$
    D'où le résultat :
    $$\sup_{x\in\mathbb{R}}\vert f_n^{(i)}(x)\vert = \Vert f_n^{(i)}\Vert_{\infty} \xrightarrow[n\to +\infty]{} 0 \quad\text{pour } i\in\{1,2\}.$$
</details>

<details>
  <summary><b>Pour aller plus loin</b></summary>
    <ul>
      <li>
				<a href="derivabilite#fonctions-a-derivees-bornees-2">Une fonction bornée à dérivée seconde bornée a une dérivée bornée</a>
      </li>
      <li>
				<a href="espaces-vectoriels-normes#fonctions-a-derivees-bornees">Fonctions à dérivées bornées (autour de l'inégalité de Landau–Kolmogorov)</a>
      </li>
    </ul>
</details>

---
