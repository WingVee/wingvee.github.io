---
layout: default
title: Arithmétique des entiers
permalink: arithmetique-des-entiers
redirect_from:
  - arithmétique-des-entiers
  - arithmetique
  - arithmétique
---

---

<h3 id="theoreme-de-wilson">
  <a href="#theoreme-de-wilson" class="header">
  Théorème de Wilson (1770) - Un critère de primalité</a>
</h3>

L'objectif de cet exercice est de montrer le théorème de Wilson (de plusieurs manières différentes) :

$$\text{Soit } p\geq 2. \text{ Alors } p \text{ est premier} \iff (p-1)!\equiv -1\ [p].$$

Sens facile : Montrer que si $p$ n'est pas premier, alors $(p-1)!+1\not\equiv 0\ [p]$.

**Première méthode : inverses de $\mathbb{Z}/p\mathbb{Z}^*$**

1. Montrer que si $p$ est premier, alors tout élément $\overline k$ de $\mathbb{Z}/p\mathbb{Z}^*$ admet un inverse. Étudier le cas où l'inverse de $\overline k$ est $\overline k$ lui-même.

2. En déduire le théorème de Wilson.

**Deuxième méthode : avec un polynôme**

<ol>
  <li>
    Soit $p$ un nombre premier. Considérons le polynôme
    $$P(X) = X^{p-1}-1 - (X-1)(X-2)\dots(X-(p-1)).$$
    Montrer que $P$ est le polynôme nul dans $\mathbb{Z}/p\mathbb{Z}[X]$, i.e. les coefficients de $P$ sont nuls modulo $p$.<br><br>
  </li>
  <li>
    En déduire le théorème de Wilson.
  </li>
</ol>

<details>
  <summary><b>Remarque</b></summary>
    Cette caractérisation des nombres premiers est très peu utilisée en pratique puisqu'il est laborieux de calculer $(p-1)!$ pour des grands nombres, ce critère de primalité est intéressant d'un point de vue théorique.
</details>

<details>
  <summary><b>Indications</b></summary>
    <details>
      <summary><u>Sens facile</u></summary>
        Si $p$ n'est pas premier, alors il existe $2\leq d\leq p-1$ tel que $d$ divise $p$.
    </details>
    <details>
      <summary><u>Première méthode : inverses de $\mathbb{Z}/p\mathbb{Z}^*$</u></summary>
        Regrouper les éléments de $\mathbb{Z}/p\mathbb{Z}^*$ par paires ($\overline k$ et son inverse $\overline k^{-1}$).
    </details>
    <details>
      <summary><u>Deuxième méthode : avec un polynôme</u></summary>
        Étudier le degré de $P$ et utiliser le petit théorème de Fermat.
    </details>
</details>

<details>
  <summary><b>Solution</b></summary>
    Sens facile :<br>
    Si $p$ n'est pas premier, alors il existe $2\leq d\leq p-1$ tel que $d$ divise $p$.<br>
    En particulier, $d$ divise $(p-1)!$ et donc $d$ ne divise pas $(p-1)!+1$.<br>
    Ainsi, $p$ ne divise pas $(p-1)!+1$, d'où $(p-1)!+1\not\equiv 0\ [p]$.<br><br>
    Remarque : on ne peut pas utiliser le fait que $p = ab$ avec $1<a,b<p$ et que $p=ab$ divise $(p-1)!$ car $a$ et $b$ ne sont pas forcément distincts (prendre $p=4$ par exemple).<br><br>
    <b>Première méthode : inverses de $\mathbb{Z}/p\mathbb{Z}^*$</b>
    <ol>
      <li>
        Si $p$ est premier, alors $\mathbb{Z}/p\mathbb{Z}$ est un corps, donc tout élément non nul de $\mathbb{Z}/p\mathbb{Z}$ admet un inverse.<br>
        Soit $\overline k\in\mathbb{Z}/p\mathbb{Z}^*$ qui est son propre inverse. On a alors :
        $$\overline k^{-1} = \overline k \Longleftrightarrow \overline k^2 = \overline 1 \Longleftrightarrow (\overline k-\overline 1)(\overline k+\overline 1) = \overline 0 \Longleftrightarrow \overline k = \pm\overline 1.$$
      </li>
      <li>
        Dans $\mathbb{Z}/p\mathbb{Z}^*$, on a :
        $$\overline{(p-1)!} = \overline 1\times \overline 2\times \dots \times \overline{p-1} = \overline 1 \times \overline{p-1} = \overline{-1}$$
        car on peut regrouper chaque élément $\overline k$ dans le produit $\overline 2\times \dots \times\overline{p-2}$ avec son inverse $\overline k^{-1} \neq \overline k$, et le produit de chaque paire vaut $\overline 1$.
        Donc $(p-1)!\equiv -1\ [p]$ si $p$ est premier.
      </li>
    </ol>
    <b>Deuxième méthode : avec un polynôme</b>
    <ol>
      <li>
        $P$ est de degré strictement inférieur à $p-1$ et on vérifie que $P(k)\equiv 0\ [p]$ pour $k\in\{1,\dots,p-1\}$.<br>
        En effet, d'après le petit théorème de Fermat, on a $k^{p-1}\equiv 1\ [p]$ pour tout $k\in\mathbb{Z}$ tel que $p\nmid k$.<br>
        Ainsi, $P(k)\equiv 0\ [p]$ pour $k\in\{1,\dots,p-1\}$.<br>
        Dans $\mathbb{Z}/p\mathbb{Z}[X]$, $P$ possède donc $p-1$ racines distinctes. Puisque $P$ est de degré strictement inférieur à $p-1$ et que $\mathbb{Z}/p\mathbb{Z}$ est un corps, $P$ est le polynôme nul dans $\mathbb{Z}/p\mathbb{Z}[X]$.
      </li>
      <li>
        $P$ étant le polynôme nul dans $\mathbb{Z}/p\mathbb{Z}[X]$, on a $P(k)\equiv 0\ [p]$ pour tout $k\in\mathbb{Z}$.<br>
        En évaluant en $X=0$, on obtient $P(0) = -1 - (-1)^{p-1}(p-1)! \equiv 0\ [p]$, d'où le théorème de Wilson en remarquant que $(-1)^{p-1} \equiv 1\ [p]$ (dans tous les cas, que $p=2$ ou $p$ impair).
      </li>
    </ol>
</details>

---

<h3 id="theoreme-de-lucas">
  <a href="#theoreme-de-lucas" class="header">
  Théorème de Lucas (1878) - Reste modulo $p$ de $\displaystyle\binom{n}{k}$</a>
</h3>

Soient $n,k\in\mathbb{N}$ et $p$ un nombre premier.<br>
Décomposons $n$ et $k$ en base $p$ :

$$n = n_r p^r + n_{r-1} p^{r-1} + \ldots + n_1 p + n_0 \quad \text{et} \quad k = k_r p^r + k_{r-1} p^{r-1} + \ldots + k_1 p + k_0$$

où $0\leq n_i,k_i<p$ pour tout $i\in\\{0,\ldots,r\\}$.

L'objectif de cet exercice est de montrer le théorème de Lucas :

$$\binom{n}{k}\equiv\prod_{i=0}^r\binom{n_i}{k_i}\ [p].$$

1. Montrer que $(1+X)^p\equiv 1+X^p\ [p]$.

2. Montrer que pour tout $i\in\mathbb{N}$, on a $(1+X)^{p^i}\equiv 1+X^{p^i}\ [p]$.

3. Montrer que $\displaystyle\sum_{k=0}^{n}\binom{n}{k}X^k\equiv\sum_{k=0}^{n}\left(\prod_{i=0}^r\binom{n_i}{k_i}\right)X^k\ [p]$.

4. En déduire le théorème de Lucas.

<details>
  <summary><b>Indications</b></summary>
    <ol>
      <li>
        Montrer que $p$ divise $\binom{p}{k}$ pour $0<k<p$.
      </li>
      <li>
        Récurrence.
      </li>
      <li>
        Binôme de Newton.
      </li>
      <li>
        Immédiat.
      </li>
    </ol>
</details>

<details>
  <summary><b>Solution</b></summary>
    <ol>
      <li>
        D'après le binôme de Newton, on a $\displaystyle (1+X)^p = \sum_{k=0}^{p}\binom{p}{k}X^k$.<br>
        Or, pour $0<k<p$, on a $\displaystyle \binom{p}{k} = \frac{p!}{k!(p-k)!} = \frac{p(p-1)\dots(p-k+1)}{k(k-1)\dots 1}\in\mathbb N$, dont le numérateur est divisible par $p$ mais pas le dénominateur, donc $p$ divise $\displaystyle\binom{p}{k}$ pour $0<k<p$.<br>
        Remarque : on pouvait aussi voir que $\displaystyle k\binom{p}{k} = p\binom{p-1}{k-1}$ donc $p$ divise $\displaystyle k\binom{p}{k}$ et donc $p$ divise $\displaystyle\binom{p}{k}$ d'après le lemme de Gauss ($0<k<p$ et $p$ est premier).<br>
        Ainsi, on a $(1+X)^p\equiv 1+X^p\ [p]$.
      </li>
      <li>
        Montrons le résultat par récurrence sur $i\in\mathbb{N}$.<br>
        Pour $i=0$, c'est immédiat.<br>
        Supposons que $(1+X)^{p^i}\equiv 1+X^{p^i}\ [p]$ pour un certain $i\in\mathbb{N}$. On a :
        $$\begin{align*}
        (1+X)^{p^{i+1}} &= ((1+X)^{p^i})^{p}\\
        &\equiv (1+X^{p^i})^{p}\ [p] \quad \text{(hypothèse de récurrence)}\\
        &\equiv 1+\left(X^{p^i}\right)^p\ [p] \quad \text{(d'après la question précédente)}\\
        &\equiv 1+X^{p^{i+1}}\ [p].
        \end{align*}$$
        Ainsi, pour tout $i\in\mathbb{N}$, on a $(1+X)^{p^i}\equiv 1+X^{p^i}\ [p]$.
      </li>
      <li> Avec le binôme de Newton, et en utilisant la question précédente, on a :
        $$\begin{align*}
        \sum_{k=0}^{n}\binom{n}{k}X^k &= \left(1+X\right)^n\\
        &= \left(1+X\right)^{n_r p^r + n_{r-1} p^{r-1} + \ldots + n_1 p + n_0}\\
        &= \prod_{i=0}^r\left(1+X\right)^{n_i p^i}\\
        &\equiv \prod_{i=0}^r\left(1+X^{p^i}\right)^{n_i}\ [p] \qquad \text{(question 2)}.
        \end{align*}$$
        Or,
        $$\begin{align*}
        \prod_{i=0}^r\left(1+X^{p^i}\right)^{n_i} &= \prod_{i=0}^r \sum_{k_i=0}^{n_i}\binom{n_i}{k_i}X^{k_i p^i} \qquad \text{(binôme de Newton)}\\
        &= \prod_{i=0}^r \sum_{k_i=0}^{p-1}\binom{n_i}{k_i}X^{k_i p^i} \qquad \text{(car $\binom{n_i}{k_i}=0$ pour $n_i < k_i \leq p-1$)}\\
        &= \sum_{0\leq k_0,\dots,k_r\leq p-1}\left(\prod_{i=0}^r\binom{n_i}{k_i}X^{k_i p^i}\right) \qquad \text{(distributivité)}\\
        &= \sum_{0\leq k_0,\dots,k_r\leq p-1}\left(\prod_{i=0}^r\binom{n_i}{k_i}\right)X^{k_0 + k_1 p + \ldots + k_r p^r}\\
        &= \sum_{k=0}^{p^{r+1}-1}\left(\prod_{i=0}^r\binom{n_i}{k_i}\right)X^k \qquad \text{(bijection entre les indices)}\\
        &= \sum_{k=0}^{n}\left(\prod_{i=0}^r\binom{n_i}{k_i}\right)X^k \qquad \text{(car $\displaystyle \prod_{i=0}^r\left(1+X^{p^i}\right)^{n_i}$ polynôme de degré $n$)}.
        \end{align*}$$
        D'où
        $$\sum_{k=0}^{n}\binom{n}{k}X^k\equiv\sum_{k=0}^{n}\left(\prod_{i=0}^r\binom{n_i}{k_i}\right)X^k\ [p].$$
      </li>
      <li>
        Par identification des coefficients de $X^k$ dans les deux membres de l'équation précédente, on obtient le théorème de Lucas :
        $$\binom{n}{k}\equiv\prod_{i=0}^r\binom{n_i}{k_i}\ [p].$$
      </li>
    </ol>
</details>

---

<h3 id="formule-de-legendre">
  <a href="#formule-de-legendre" class="header">
  Formule de Legendre (1830) - Valuation $p$-adique de $n!$</a>
</h3>

Soient $n\in\mathbb{N}^*$ et $p$ un nombre premier.<br>
On note $v_p(n)$ la valuation $p$-adique de $n$, c'est-à-dire l'exposant de $p$ dans la décomposition en facteurs premiers de $n$ (de manière équivalente, le plus grand entier $k$ tel que $p^k$ divise $n$).<br>

Montrer la formule de Legendre :

$$v_p(n!)=\sum_{k=1}^{\infty}\left\lfloor\frac{n}{p^k}\right\rfloor.$$

<details>
  <summary><b>Indications</b></summary>
    Combien y a-t-il de multiples de $p^k$ parmi les entiers de $1$ à $n$ ?
</details>

<details>
  <summary><b>Solution</b></summary>
    Les trois solutions suivantes sont équivalentes et détaillent la même idée.
    <details>
      <summary><u>Solution rapide</u></summary>
        Le nombre d'entiers de $1$ à $n$ qui sont multiples de $p^k$ est $\displaystyle\left\lfloor\frac{n}{p^k}\right\rfloor$.<br>
        Ainsi, le nombre d'entiers de $1$ à $n$ dont la valuation $p$-adique est $k$ (i.e. multiples de $p^k$ mais pas de $p^{k+1}$) est :
        $$\displaystyle\left\lfloor\frac{n}{p^k}\right\rfloor-\left\lfloor\frac{n}{p^{k+1}}\right\rfloor.$$
        Puisque la valuation $p$-adique de $n!$ est la somme des valuations $p$-adiques des entiers de $1$ à $n$, en regroupant leur valuation $p$-adique, et en remarquant que $\left\lfloor\frac{n}{p^{k}}\right\rfloor = 0$ pour $k>\log_p(n)$, on obtient :
        $$v_p(n!) = \left(\left\lfloor\frac{n}{p}\right\rfloor-\left\lfloor\frac{n}{p^2}\right\rfloor\right) + 2\left(\left\lfloor\frac{n}{p^2}\right\rfloor-\left\lfloor\frac{n}{p^3}\right\rfloor\right) + 3\left(\left\lfloor\frac{n}{p^3}\right\rfloor-\left\lfloor\frac{n}{p^4}\right\rfloor\right) + \ldots = \sum_{k=1}^{\infty}\left\lfloor\frac{n}{p^k}\right\rfloor.$$
    </details>
    <details>
      <summary><u>Solution sans mot</u></summary>
        $$\begin{align*}
          v_p(n!) &= v_p\left(\prod_{j=1}^n j\right) = \sum_{j=1}^n v_p(j) \\
          &= \sum_{k=0}^{\infty}\sum_{\substack{j\in\{1,\ldots,n\}\\v_p(j)=k}}v_p(j) = \sum_{k=0}^{\infty}\sum_{\substack{j\in\{1,\ldots,n\}\\v_p(j)=k}}k \\
          &= \sum_{k=0}^{\infty}k\cdot\operatorname{Card}\left(\{j\in\{1,\ldots,n\}\mid v_p(j)=k\}\right) \\
          &= \sum_{k=0}^{\infty}k\left(\left\lfloor\frac{n}{p^k}\right\rfloor-\left\lfloor\frac{n}{p^{k+1}}\right\rfloor\right) \\
          &= \sum_{k=0}^{\infty}\left\lfloor\frac{n}{p^{k+1}}\right\rfloor + k\left\lfloor\frac{n}{p^k}\right\rfloor - (k+1)\left\lfloor\frac{n}{p^{k+1}}\right\rfloor \\
          &= \sum_{k=0}^{\infty}\left\lfloor\frac{n}{p^{k+1}}\right\rfloor = \sum_{k=1}^{\infty}\left\lfloor\frac{n}{p^k}\right\rfloor.
        \end{align*}$$
    </details>
    <details>
      <summary><u>Solution détaillée</u></summary>
        Il est facile de montrer que $v_p(ab)=v_p(a)+v_p(b)$ pour tous $a,b\in\mathbb{N}^*$.<br>
        On a alors
        $$v_p(n!) = v_p\left(\prod_{j=1}^n j\right) = \sum_{j=1}^n v_p(j).$$
        On peut faire une disjonction de cas sur la valuation $p$-adique de $j$ :
        $$\{1,\ldots,n\} = \bigsqcup_{k=0}^{\infty}\Big\{j\in\{1,\ldots,n\}\mid v_p(j)=k\Big\} = \bigsqcup_{k=0}^{\infty} A_k$$
        où $A_k = \{j\in\{1,\ldots,n\}\mid v_p(j)=k\}$ est l'ensemble des entiers de $1$ à $n$ dont la valuation $p$-adique est $k$ (on peut aller jusqu'à $+\infty$ en remarquant que les ensembles $A_k$ sont vides pour $k>\log_p(n)$).
        Ainsi, on a
        $$v_p(n!) = \sum_{j=1}^n v_p(j) = \sum_{k=0}^{\infty}\sum_{j\in A_k}v_p(j) = \sum_{k=0}^{\infty}k\cdot\operatorname{Card}(A_k)$$
        Il reste à déterminer $\operatorname{Card}(A_k)$, i.e. le nombre d'entiers de $1$ à $n$ dont la valuation $p$-adique est exactement $k$.<br>
        Il suffit de remarquer qu'un entier $j$ a pour valuation $p$-adique $k$ si et seulement si $p^k$ divise $j$ mais $p^{k+1}$ ne divise pas $j$.<br>
        Or le nombre d'entiers de $1$ à $n$ qui sont divisibles par $p^k$ est $\displaystyle \left\lfloor\frac{n}{p^k}\right\rfloor$ (c'est le plus grand entier $m$ tel que $p^k\cdot m\leq n$).<br>
        Donc le nombre d'entiers de $1$ à $n$ dont la valuation $p$-adique est exactement $k$ est la différence entre le nombre d'entiers de $1$ à $n$ divisibles par $p^k$ et le nombre d'entiers de $1$ à $n$ divisibles par $p^{k+1}$, i.e.
        $$\displaystyle \operatorname{Card}(A_k) = \left\lfloor\frac{n}{p^k}\right\rfloor-\left\lfloor\frac{n}{p^{k+1}}\right\rfloor.$$
        Ainsi, on a, en faisant apparaître un télescopage, et en remarquant que $\displaystyle\left\lfloor\frac{n}{p^{k}}\right\rfloor = 0$ pour $k>\log_p(n)$ :
        $$\begin{align*}
        v_p(n!) &= \sum_{k=0}^{\infty}k\cdot\operatorname{Card}(A_k) \\
        &= \sum_{k=0}^{\infty}k\left(\left\lfloor\frac{n}{p^k}\right\rfloor-\left\lfloor\frac{n}{p^{k+1}}\right\rfloor\right) \\
        &= \sum_{k=0}^{\infty}\left\lfloor\frac{n}{p^{k+1}}\right\rfloor + k\left\lfloor\frac{n}{p^k}\right\rfloor - (k+1)\left\lfloor\frac{n}{p^{k+1}}\right\rfloor \\
        &= \sum_{k=0}^{\infty}\left\lfloor\frac{n}{p^{k+1}}\right\rfloor = \sum_{k=1}^{\infty}\left\lfloor\frac{n}{p^k}\right\rfloor.
        \end{align*}$$
        D'où la formule de Legendre.
    </details>
</details>

<details>
  <summary><b>Pour aller plus loin</b></summary>
    <ul>
      <li>
        <a href="#formule-de-legendre-2">Formule de Legendre (1830) - Forme alternative</a>
      </li>
    </ul>
</details>

---

<h3 id="formule-de-legendre-2">
  <a href="#formule-de-legendre-2" class="header">
  Formule de Legendre (1830) - Forme alternative</a>
</h3>

Soient $n\in\mathbb{N}^*$ et $p$ un nombre premier.<br>
On note $v_p(n)$ la valuation $p$-adique de $n$, c'est-à-dire l'exposant de $p$ dans la décomposition en facteurs premiers de $n$ (de manière équivalente, le plus grand entier $k$ tel que $p^k$ divise $n$).

Montrer la forme alternative de la formule de Legendre :

$$v_p(n!)=\frac{n-s_p(n)}{p-1}$$

où $s_p(n)$ est la somme des chiffres de l'écriture de $n$ en base $p$.

On pourra admettre la formule de Legendre (traitée dans [l'exercice précédent](#formule-de-legendre)) :

$$v_p(n!)=\sum_{k=1}^{\infty}\left\lfloor\frac{n}{p^k}\right\rfloor.$$

<details>
  <summary><b>Indications</b></summary>
    Écrire $n$ en base $p$ : $\displaystyle n = \overline{a_r\dots a_1a_0} = a_0 + \dots + a_rp^r = \sum_{j=0}^r a_jp^j$ avec $a_j\in\{0,\ldots,p-1\}$ et $a_r\neq 0$.<br>
    Étudier la valeur de $\displaystyle\left\lfloor\frac{n}{p^k}\right\rfloor$ pour $1\leq k\leq r$.
</details>

<details>
  <summary><b>Solution</b></summary>
    Écrivons $n$ en base $p$ : $\displaystyle n = \overline{a_r\dots a_1a_0} = a_0 + \dots + a_rp^r = \sum_{j=0}^r a_jp^j$ avec $a_j\in\{0,\ldots,p-1\}$ et $a_r\neq 0$.<br>
    On remarque que si $k>r$, alors $\displaystyle\left\lfloor\frac{n}{p^k}\right\rfloor = 0$ car $p^k>n$.<br>
    Et si $1\leq k\leq r$, puisque $\displaystyle 0\leq \frac{a_0+\dots+a_{k-1}p^{k-1}}{p^k}<1$ et que $\displaystyle\frac{a_k p^k + \dots + a_rp^r}{p^k}$ est entier, on a $$\left\lfloor\frac{n}{p^k}\right\rfloor = \left\lfloor\frac{a_0+\dots+a_{k-1}p^{k-1}}{p^k}+\frac{a_kp^k+\dots+a_rp^r}{p^k}\right\rfloor = a_k + \dots + a_r p^{r-k} = \sum_{j=k}^r a_jp^{j-k}.$$
    Autrement dit, si $n = \overline{a_r\dots a_1a_0}$, alors $\displaystyle\left\lfloor\frac{n}{p^k}\right\rfloor = \overline{a_r\dots a_k}$ pour tout $k\in\mathbb N$ (c'est exactement comme en base décimale où la partie entière de $n$ divisé par $10^k$ revient à enlever les $k$ derniers chiffres de $n$ en base 10).<br>
    Ainsi, on a :
    $$\begin{align*}
    v_p(n!) &= \sum_{k=1}^{\infty}\left\lfloor\frac{n}{p^k}\right\rfloor = \sum_{k=1}^{r}\left\lfloor\frac{n}{p^k}\right\rfloor \qquad \text{(formule de Legendre)}\\
    &= \sum_{k=1}^r\sum_{j=k}^r a_jp^{j-k} = \sum_{1\leq k\leq j\leq r} a_jp^{j-k} = \sum_{j=1}^r\sum_{k=1}^j a_jp^{j-k} \qquad \text{(permutation de sommes)}\\
    &= \sum_{j=1}^r a_j \sum_{k=1}^j p^{j-k} = \sum_{j=1}^r a_j \sum_{k=0}^{j-1} p^k \qquad \text{(changement d'indices)}\\
    &= \sum_{j=1}^r a_j \frac{p^j-1}{p-1} = \sum_{j=0}^r a_j \frac{p^j-1}{p-1} \qquad \text{(somme d'une suite géométrique, et $p\neq 1$)}\\
    &= \frac{1}{p-1}\left(\sum_{j=0}^r a_jp^j - a_j\right)\\
    &= \frac{n-s_p(n)}{p-1} \qquad \text{(car $n = \sum_{j=0}^r a_jp^j$ et $s_p(n) = \sum_{j=0}^r a_j$)}.
    \end{align*}$$
    D'où la formule alternative de Legendre.
</details>

<details>
  <summary><b>Pour aller plus loin</b></summary>
    <ul>
      <li>
        <a href="#theoreme-de-kummer">Théorème de Kummer (1852) - Valuation $p$-adique de $\binom{n}{k}$</a>
      </li>
    </ul>
</details>

---

<h3 id="theoreme-de-kummer">
  <a href="#theoreme-de-kummer" class="header">
  Théorème de Kummer (1852) - Valuation $p$-adique de $\binom{n}{k}$</a>
</h3>

Soient $n\in\mathbb{N}^*$ et $p$ un nombre premier.<br>
On note $v_p(n)$ la valuation $p$-adique de $n$, c'est-à-dire l'exposant de $p$ dans la décomposition en facteurs premiers de $n$ (de manière équivalente, le plus grand entier $j$ tel que $p^j$ divise $n$).<br>
Soit $k\in\{0,\ldots,n\}$.

Montrer les deux formulations du théorème de Kummer :

<ol>
  <li>
    En notant $s_p(n)$ la somme des chiffres de l'écriture de $n$ en base $p$, on a :
    $$v_p\left(\binom{n}{k}\right) = \frac{s_p(k)+s_p(n-k)-s_p(n)}{p-1}.$$
  </li>
  <li>
    $\displaystyle v_p\left(\binom{n}{k}\right)$ est égale au nombre de retenues lors de l'addition de $k$ et $n-k$ en base $p$.
  </li>
</ol>

On pourra admettre la forme alternative de la formule de Legendre (traitée dans [l'exercice précédent](#formule-de-legendre-2)) :

$$v_p(n!)=\frac{n-s_p(n)}{p-1}.$$

<details>
  <summary><b>Indications</b></summary>
    <ol>
      <li>
        Utiliser la propriété $v_p(ab)=v_p(a)+v_p(b)$ pour $a,b\in\mathbb{N}^*$.
      </li>
      <li>
        Écrire $k$ et $n-k$ en base $p$ et compter le nombre de retenues lors de l'addition.
      </li>
    </ol>
</details>

<details>
  <summary><b>Solution</b></summary>
    <ol>
      <li>
        On a :
        $$\begin{align*}
        v_p\left(\binom{n}{k}\right) &= v_p\left(\frac{n!}{k!(n-k)!}\right)\\
        &= v_p(n!)-v_p(k!)-v_p((n-k)!) \qquad \text{(car $v_p(ab)=v_p(a)+v_p(b)$)}\\
        &= \frac{n-s_p(n)}{p-1} - \frac{k-s_p(k)}{p-1} - \frac{n-k-s_p(n-k)}{p-1} \qquad \text{(formule de Legendre)}\\
        &= \frac{s_p(k)+s_p(n-k)-s_p(n)}{p-1}.
        \end{align*}$$
      </li>
      <li>
        Écrivons $k$, $n-k$ et $n$ en base $p$ :<br>
        $$\begin{align*}
        k &= \overline{a_r\dots a_1a_0} & (0\leq a_j<p)\\
        n-k &= \overline{b_r\dots b_1b_0} & (0\leq b_j<p)\\
        n &= \overline{c_r\dots c_1c_0} & (0\leq c_j<p, c_r\neq 0).
        \end{align*}$$
        D'après les règles de l'addition en base $p$ (similaires à celles en base 10), on a :
        $$c_0 \equiv a_0 + b_0\ [p]$$
        et pour tout $j\in\{1,\ldots,r\}$
        $$c_j \equiv a_j + b_j + \delta_{j-1}\ [p]$$
        où l'on pose $\delta_{-1} = 0$ et
        $$\delta_j = \begin{cases} 1 & \text{si } a_j+b_j+\delta_{j-1}\geq p \\ 0 & \text{sinon}\end{cases} \quad \text{(c'est la retenue)}.$$
        En remarquant que $0 \leq a_j + b_j + \delta_{j-1} < 2p$, on a :
        $$c_j = \begin{cases} a_j + b_j + \delta_{j-1} & \text{si } a_j + b_j + \delta_{j-1} < p \\ a_j + b_j + \delta_{j-1} - p & \text{sinon}\end{cases}.$$
        Autrement dit :
        $$c_j = (a_j + b_j + \delta_{j-1}) - \delta_j p.$$
        Ainsi, en sommant sur les chiffres, et sachant que $\delta_{-1} = 0$ et $\delta_r = 0$ :
        $$s_p(n) = \sum_{j=0}^r c_j = \sum_{j=0}^r (a_j + b_j + \delta_{j-1}) - \delta_j p = s_p(k) + s_p(n-k) - \sum_{j=0}^{r-1}(p-1)\delta_j.$$
        D'où
        $$\sum_{j=0}^{r-1}\delta_j = \frac{s_p(k) + s_p(n-k) - s_p(n)}{p-1},$$
        i.e. le nombre de retenues lors de l'addition de $k$ et $n-k$ en base $p$ est
        $$\displaystyle\frac{s_p(k) + s_p(n-k) - s_p(n)}{p-1} = v_p\left(\binom{n}{k}\right).$$
      </li>
    </ol>
</details>

---

<h3 id="sommes-de-puissances-dans-zpz">
  <a href="#sommes-de-puissances-dans-zpz" class="header">
  Sommes de puissances dans $\mathbb{Z}/p\mathbb{Z}$</a>
</h3>

Soit $p$ un nombre premier. Que valent ces sommes dans $\mathbb{Z}/p\mathbb{Z}$ ?

1. $\displaystyle\sum_{k=1}^p \overline k$.
2. $\displaystyle\sum_{k=1}^p \overline k^2$.
3. $\displaystyle\sum_{k=1}^p \overline k^3$.

<details>
  <summary>Rappel des formules de Faulhaber (pour les exposants 1,2,3) :</summary>
    Les <a href="https://fr.wikipedia.org/wiki/Formule_de_Faulhaber" target="_blank">formules de Faulhaber</a> expriment les sommes des puissances $j$-èmes des entiers de $1$ à $n$ sous forme de fonction polynomiale en $n$ (de degré $j+1$).<br>
    Ici, pour $j=1,2,3$, on a dans $\mathbb{Z}$ :
    $$\sum_{k=1}^n k = \frac{n(n+1)}{2} \quad,\quad \sum_{k=1}^n k^2 = \frac{n(n+1)(2n+1)}{6} \quad,\quad \sum_{k=1}^n k^3 = \left(\frac{n(n+1)}{2}\right)^2.$$
</details>

<details>
  <summary><b>Indications</b></summary>
    Faire des disjonctions de cas sur $p$ et voir quand certaines fractions sont entières.
</details>

<details>
  <summary><b>Solution</b></summary>
    <ol>
      <li>
        On a
        $$\sum_{k=1}^p \overline k = \overline{\sum_{k=1}^p k} = \overline{\frac{p(p+1)}{2}}.$$
        Si $p=2$, on a $\overline{\frac{p(p+1)}{2}} = \overline{\frac{2(2+1)}{2}} = \overline{3} = \overline{1}$.<br>
        Sinon, $p$ est impair, donc $\overline{\frac{p(p+1)}{2}} = \overline{p}\cdot\overline{\frac{p+1}{2}} = \overline{0}\cdot\overline{\frac{p+1}{2}} = \overline{0}$.<br>
        Donc
        $$\displaystyle\sum_{k=1}^p \overline k = \begin{cases} \overline{1} & \text{si } p=2 \\ \overline{0} & \text{sinon}\end{cases}.$$
      </li>
      <li>
        On a
        $$\sum_{k=1}^p \overline k^2 = \overline{\sum_{k=1}^p k^2} = \overline{\frac{p(p+1)(2p+1)}{6}}.$$
        Si $p=2$, on a $\overline{\frac{p(p+1)(2p+1)}{6}} = \overline{\frac{2(2+1)(2\cdot 2+1)}{6}} = \overline{5} = \overline{1}$.<br>
        Si $p=3$, on a $\overline{\frac{p(p+1)(2p+1)}{6}} = \overline{\frac{3(3+1)(2\cdot 3+1)}{6}} = \overline{\frac{3\cdot 4}{6}}\cdot\overline{7} = \overline{2}\cdot\overline{7} = \overline{14} = \overline{2}$.<br>
        Sinon, $p$ est impair et n'est pas un multiple de $3$.
        On a alors 6 divise $(p+1)(2p+1)$ car $2|p+1$ et, si $p\equiv 1\ [3]$, alors $3|2p+1$, et si $p\equiv 2\ [3]$, alors $3|p+1$, donc $3|(p+1)(2p+1)$ dans tous les cas.<br>
        Ainsi, $\overline{\frac{p(p+1)(2p+1)}{6}} = \overline{p}\cdot\overline{\frac{(p+1)(2p+1)}{6}} = \overline{0}\cdot\overline{\frac{(p+1)(2p+1)}{6}} = \overline{0}$.<br>
        Donc
        $$\displaystyle\sum_{k=1}^p \overline k^2 = \begin{cases} \overline{1} & \text{si } p=2 \\ \overline{2} & \text{si } p=3 \\ \overline{0} & \text {sinon} \end{cases}.$$
      </li>
      <li>
        On a
        $$\sum_{k=1}^p \overline k^3 = \overline{\sum_{k=1}^p k^3} = \overline{\left(\frac{p(p+1)}{2}\right)^2}.$$
        D'après les résultats pour l'exposant 1, on a $\overline{\frac{p(p+1)}{2}} = \overline{1}$ si $p=2$ et $\overline{0}$ sinon.<br>
        Donc
        $$\displaystyle\sum_{k=1}^p \overline k^3 = \begin{cases} \overline{1} & \text{si } p=2 \\ \overline{0} & \text{sinon}\end{cases}.$$
      </li>
    </ol>
</details>

---
