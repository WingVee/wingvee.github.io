---
layout: default
title: Arithmétique des polynômes
permalink: arithmetique-des-polynomes
redirect_from:
  - arithmétique-des-polynômes
---

---

<h3 id="polynome-positif-somme-de-deux-carres">
  <a href="#polynome-positif-somme-de-deux-carres" class="header">
  Polynôme positif et somme de deux carrés</a>
</h3>

Soit $P\in\mathbb{R}[X]$. Montrer l'équivalence suivante :

$$\forall x\in\mathbb{R},\ P(x)\geq 0 \iff \exists (A,B)\in\mathbb{R}[X]^2,\ P = A^2 + B^2.$$

<details>
  <summary><b>Indications</b></summary>
    Quelques pistes de réflexion :<br>
    Si $P\geq 0$, quel est le degré de $P$ ?<br>
    Traiter le cas où $P$ est de degré 0,1,2.<br>
    Factoriser $P$ en polynômes irréductibles sur $\mathbb{R}[X]$.<br>
    Est-ce que les racines de $P$ peuvent être de multiplicité impaire ?<br>
    Est-ce que $(A^2+B^2)(C^2+D^2)$ est une somme de deux carrés ?
</details>

<details>
  <summary><b>Solution</b></summary>
    Le sens réciproque est immédiat. Montrons l'implication directe.<br>
    Supposons que $P(x)\geq 0$ pour tout $x\in\mathbb{R}$.<br><br>
    Commençons par traiter les cas où $P$ est de degré $-\infty$, 0, 1, 2.<br>
    Si $P$ est le polynôme constant, alors $P = P(0) \geq 0$ et on peut écrire $P = \sqrt{P(0)}^2+0^2$.<br>
    Si $P$ est de degré 1, alors $P = aX+b$ avec $a\neq 0$. Cela n'est pas possible car une fonction affine change de signe (voir en $\pm\infty$).<br>
    Si $P$ est de degré 2, alors $P = aX^2+bX+c$ avec $a\neq 0$. Puisque $P(x)\geq 0\ \forall x\in\mathbb{R}$, le discriminant de $P$ est négatif et $a>0$. On a alors (sous forme canonique)
    $$P = a\left(X+\frac{b}{2a}\right)^2 + \frac{-b^2+4ac}{4a} = \left(\sqrt{a}\left(X+\frac{b}{2a}\right)\right)^2 + \left(\sqrt{\frac{-b^2+4ac}{4a}}\right)^2.$$
    Donc $P$ est une somme de deux carrés.<br><br>
    Traitons le cas général $(P\neq 0)$.<br>
    En factorisant $P$ en polynômes irréductibles sur $\mathbb{R}[X]$, on a :
    $$P = \lambda\prod_{i=1}^n (X-a_i)^{n_i} \prod_{j=1}^p (X^2+b_jX+c_j)^{p_j}$$
    où $\lambda\in\mathbb{R}^*$, $n,p\in\mathbb N$, $n_i,p_j\in\mathbb{N}^*$, $a_i\in\mathbb{R}$ distincts deux à deux et $b_j,c_j\in\mathbb{R}$ tels que $\Delta_j = b_j^2-4c_j<0$.<br><br>
    Montrons que les $n_i$ sont pairs.<br>
    Regardons au voisinage de $a_i$. Écrivons $P = (X-a_i)^{n_i}Q$ avec $Q\in\mathbb{R}[X]$ tel que $Q(a_i)\neq 0$.<br>
    Pour $h$ proche de $0$, on a
    $$P(a_i+h) = h^{n_i}Q(a_i+h) \sim Q(a_i)h^{n_i}.$$
    Si $n_i$ est impair, puisque $h^{n_i}$ change de signe lorsque $h$ change de signe, $P(a_i+h)$ change de signe lorsque $h$ change de signe au voisinage de $0$, ce qui contredit $P(x)\geq 0$ pour tout $x\in\mathbb{R}$.<br>
    Donc les $n_i$ sont pairs et peuvent s'écrire $n_i = 2k_i$.<br>
    Ainsi, on a
    $$\begin{align*}
    P &= \lambda\prod_{i=1}^n (X-a_i)^{2k_i} \prod_{j=1}^p (X^2+b_jX+c_j)^{p_j}\\
    &= \lambda\prod_{i=1}^n (X^2-2a_iX+a_i^2)^{k_i} \prod_{j=1}^p (X^2+b_jX+c_j)^{p_j}\\
    &= \lambda\prod_{k=1}^m (X^2+\alpha_kX+\beta_k)
    \end{align*}$$
    avec $\alpha_k,\beta_k\in\mathbb{R}$ tels que $\Delta_k = \alpha_k^2-4\beta_k\leq 0$ (pas nécessairement distincts).<br>
    D'après le cas de degré 2 (discriminant négatif), chaque $X^2+\alpha_kX+\beta_k$ est une somme de deux carrés.<br>
    Donc
    $$P = \lambda \prod_{k=1}^m (A_k^2 + B_k^2).$$
    Or, on remarque (en développant ou en utilisant les modules avec les complexes) que
    $$(A^2+B^2)(C^2+D^2) = (AC-BD)^2 + (AD+BC)^2.$$
    Donc "être somme de deux carrés" est stable par produit.<br>
    Ainsi, $P = \lambda(A^2+B^2) = (\sqrt{\lambda}A)^2 + (\sqrt{\lambda}B)^2$ car $\lambda > 0$ puisque $P(x)\geq 0$ pour tout $x\in\mathbb{R}$.<br>
    Donc $P$ est une somme de deux carrés.
</details>

---

<h3 id="cn-racines-rationnelles-polynomes-entiers">
  <a href="#cn-racines-rationnelles-polynomes-entiers" class="header">
  Racines rationnelles de polynômes entiers (condition nécessaire)</a>
</h3>

Soit $P = a_0 + a_1X + \ldots + a_nX^n\in\mathbb{Z}[X]$ (avec $a_n\neq 0$).<br>
On suppose que $P$ admet une racine rationnelle $\displaystyle\frac{p}{q}$ avec $p\wedge q = 1$ (fraction irréductible).<br>
Montrer que $p\mid a_0$ et $q\mid a_n$.

<details>
  <summary><b>Indications</b></summary>
    Écrire $\displaystyle P\left(\frac{p}{q}\right) = 0$ et développer et utiliser le lemme de Gauss.
</details>

<details>
  <summary><b>Solution</b></summary>
    $$\begin{align*}
    P\left(\frac{p}{q}\right) = 0 &\iff a_0 + a_1\frac{p}{q} + \ldots + a_n\left(\frac{p}{q}\right)^n = 0\\
    &\iff a_0q^n + a_1pq^{n-1} + \ldots + a_np^n = 0\\
    &\iff a_0q^n = -p(a_1q^{n-1} + \ldots + a_np^{n-1})\\
    &\implies p\mid a_0q^n\\
    &\iff p\mid a_0 \quad \text{(d'après le lemme de Gauss)}.
    \end{align*}$$
    De même, on a :
    $$\begin{align*}
    P\left(\frac{p}{q}\right) = 0 &\iff a_0q^n + a_1pq^{n-1} + \ldots + a_np^n = 0\\
    &\iff a_np^n = -q(a_0q^{n-1} + \ldots + a_{n-1}p^{n-1})\\
    &\implies q\mid a_np^n\\
    &\iff q\mid a_n \quad \text{(d'après le lemme de Gauss)}.
    \end{align*}$$
    Donc $\displaystyle P\left(\frac{p}{q}\right) = 0 \implies p\mid a_0$ et $q\mid a_n$.
</details>

---
