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

<h3 id="formule-de-legendre">
  <a href="#formule-de-legendre" class="header">
  Formule de Legendre (1830)</a>
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

---

<h3 id="formule-de-legendre-2">
  <a href="#formule-de-legendre-2" class="header">
  Formule de Legendre (1830) - Forme alternative</a>
</h3>

On pourra admettre la formule de Legendre (traitée dans [l'exercice précédent](#formule-de-legendre)) :

$$v_p(n!)=\sum_{k=1}^{\infty}\left\lfloor\frac{n}{p^k}\right\rfloor$$

où $n\in\mathbb{N}^*$, $p$ est un nombre premier et $v_p(n)$ est la valuation $p$-adique de $n$, c'est-à-dire l'exposant de $p$ dans la décomposition en facteurs premiers de $n$ (de manière équivalente, le plus grand entier $k$ tel que $p^k$ divise $n$).

Montrer la forme alternative de la formule de Legendre :

$$v_p(n!)=\frac{n-s_p(n)}{p-1}$$

où $s_p(n)$ est la somme des chiffres de l'écriture de $n$ en base $p$.

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

---
