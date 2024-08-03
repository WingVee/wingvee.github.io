---
layout: default
title: Déterminants
permalink: determinants
redirect_from:
  - déterminants
  - determinant
  - déterminant
---

---

<h3 id="determinant-de-vandermonde">
  <a href="#determinant-de-vandermonde" class="header">
  Déterminant de Vandermonde</a>
</h3>

Soient $a_1,\ldots,a_n\in\mathbb{C}$ (avec $n\geq 1$).

On appelle déterminant de Vandermonde la quantité

$$V(a_1,\ldots,a_n) = \left|\begin{matrix}
1 & 1 & \cdots & 1 \\
a_1 & a_2 & \cdots & a_n \\
a_1^2 & a_2^2 & \cdots & a_n^2 \\
\vdots & \vdots & \ddots & \vdots \\
a_1^{n-1} & a_2^{n-1} & \cdots & a_n^{n-1}
\end{matrix}\right| = \det((a_j^{i-1})_{1\leq i,j\leq n}).$$

Montrer que

$$V(a_1,\ldots,a_n) = \prod_{1\leq i<j\leq n} (a_j-a_i).$$

<details>
  <summary><b>Indications</b></summary>
    Considérer le polynôme $P(X) = V(a_1,\ldots,a_{n-1},X)$, développer par rapport à la dernière colonne et analyser les racines.
</details>

<details>
  <summary><b>Solution</b></summary>
    On prouve par récurrence sur $n\geq 1$.<br>
    Pour $n=1$, on a $\displaystyle V(a_1) = 1 = \prod_{1\leq i<j\leq 1} (a_j-a_i)$ (produit vide).<br>
    Supposons que la formule est vraie pour $n-1\geq 1$.<br>
    S'il existe $i,j\in\{1,\ldots,n\}$ distincts tels que $a_i=a_j$, alors deux colonnes sont égales et le déterminant est nul et la formule est vérifiée.<br>
    On suppose désormais que les $a_i$ sont distincts deux à deux.<br>
    En développant par rapport à la dernière colonne, on remarque que
    $$x\in\mathbb C\mapsto V(a_1,\ldots,a_{n-1},x) = \left|\begin{matrix}
    1 & 1 & \cdots & 1 \\
    a_1 & a_2 & \cdots & x \\
    a_1^2 & a_2^2 & \cdots & x^2 \\
    \vdots & \vdots & \ddots & \vdots \\
    a_1^{n-1} & a_2^{n-1} & \cdots & x^{n-1}
    \end{matrix}\right|$$
    est une fonction polynomiale de degré au plus $n-1$.<br>
    Ainsi, en posant $P(X) = V(a_1,\ldots,a_{n-1},X)$, on a $P\in\mathbb{C}_{n-1}[X]$.<br>
    Le coefficient de $X^{n-1}$ dans $P$ vaut $V(a_1,\ldots,a_{n-1})$.<br>
    Par hypothèse de récurrence, on a $\displaystyle V(a_1,\ldots,a_{n-1}) = \prod_{1\leq i<j\leq n-1} (a_j-a_i)\neq 0$ comme produit de termes non nuls, donc $P$ est de degré $n-1$.<br>
    De plus, $P(a_i) = 0$ pour tout $1\leq i\leq n-1$ car deux colonnes sont égales lorsque $x=a_i$.<br>
    Ainsi, puisque les $a_i$ sont distincts deux à deux, $P$ est scindé et on a
    $$P(X) = V(a_1,\ldots,a_{n-1}) \prod_{1\leq k\leq n-1} (X-a_k).$$
    D'où
    $$\begin{align*}
    V(a_1,\ldots,a_n) &= P(a_n)\\
    &= V(a_1,\ldots,a_{n-1}) \prod_{1\leq k\leq n-1} (a_n-a_k)\\
    &= \prod_{1\leq i < j \leq n-1} (a_j-a_i)\prod_{1\leq k\leq n-1} (a_n-a_k)\\
    &= \prod_{1\leq i < j < n} (a_j-a_i)\prod_{1\leq i < j = n} (a_j-a_i)\\
    &= \prod_{1\leq i < j\leq n} (a_j-a_i).
    \end{align*}$$
    Ce qui conclut la preuve par récurrence.
</details>

<details>
  <summary><b>Pour aller plus loin</b></summary>
    <ul>
      <li>
        <a href="#determinant-somme-2-vandermonde">Déterminant d'une somme de deux matrices</a>
      </li>
    </ul>
</details>

---

<h3 id="determinant-somme-2-vandermonde">
  <a href="#determinant-somme-2-vandermonde" class="header">
  Déterminant d'une somme de deux matrices</a>
</h3>

Soient $a_1,\ldots,a_n\in\mathbb{C}$ (avec $n\geq 1$).

Déterminer le déterminant de la matrice

$$ A = \begin{pmatrix}
a_1 + a_2 & a_2 + a_3 & \cdots & a_n + a_1 \\
a_1^2 + a_2^2 & a_2^2 + a_3^2 & \cdots & a_n^2 + a_1^2 \\
\vdots & \vdots & \ddots & \vdots \\
a_1^n + a_2^n & a_2^n + a_3^n & \cdots & a_n^n + a_1^n \\
\end{pmatrix}.$$

Dans quels cas $A$ est-elle inversible ?

<details>
  <summary><b>Remarques</b></summary>
    Cet exercice semblerait avoir été donné à l'oral MP Mines-Ponts 2024 (voir <a href="https://beos.prepas.org/sujet.php?id=8418" target="_blank">BEOS 8418</a>).
</details>

<details>
  <summary><b>Indications</b></summary>
    Le déterminant est $n$-linéaire et alterné en les colonnes.<br>
    Connaître le déterminant de Vandermonde (voir <a href="#determinant-de-vandermonde">exercice précédent</a>).
</details>

<details>
  <summary><b>Solution</b></summary>
    Notons $C_i = \begin{pmatrix} a_i\\ a_i^2\\ \vdots\\ a_i^n \end{pmatrix}$ pour tout $1\leq i\leq n$.<br>
    Alors
    $$A = \left[C_1 + C_2 | C_2 + C_3 | \cdots | C_n + C_1\right]$$
    (notation pour dire que $A$ est formée des colonnes $C_1 + C_2$, $C_2 + C_3$, $\ldots$, $C_n + C_1$).<br>
    Par $n$-linéarité du déterminant, on a
    $$\det(A) = \sum_{i_1\in\{1,2\}}\sum_{i_2\in\{2,3\}}\cdots\sum_{i_n\in\{n,1\}}\det\left[C_{i_1} | C_{i_2} | \cdots | C_{i_n}\right].$$
    Dès qu'il existe $i_j$ et $i_k$ tels que $i_j = i_k$ pour $j\neq k$, le déterminant est nul car deux colonnes sont égales.<br>
    Si $i_1=1$, alors il faut que $i_n = n$ pour que le déterminant soit non nul, et donc $i_{n-1} = n-1$, etc.<br>
    Si $i_1=2$, alors il faut que $i_2 = 3$, $i_3 = 4$, etc.<br>
    Donc
    $$\det(A) = \det\left[C_1 | C_2 | \cdots | C_n\right] + \det\left[C_2 | C_3 | \cdots | C_1\right].$$
    En échangeant les colonnes de la deuxième matrice $n-1$ fois, on obtient
    $$\det(A) = \det\left[C_1 | C_2 | \cdots | C_n\right] + (-1)^{n-1}\det\left[C_1 | C_2 | \cdots | C_n\right] = (1+(-1)^{n-1})\det\left[C_1 | C_2 | \cdots | C_n\right].$$
    Ainsi, si $n$ est pair, on a $\det(A) = 0$.<br>
    Si $n$ est impair, on doit calculer
    $$\det\left[C_1 | C_2 | \cdots | C_n\right] = \det\begin{pmatrix}
    a_1 & a_2 & \cdots & a_n \\
    a_1^2 & a_2^2 & \cdots & a_n^2 \\
    \vdots & \vdots & \ddots & \vdots \\
    a_1^n & a_2^n & \cdots & a_n^n
    \end{pmatrix}=a_1\dots a_n\det\begin{pmatrix}
    1 & 1 & \cdots & 1 \\
    a_1 & a_2 & \cdots & a_n \\
    \vdots & \vdots & \ddots & \vdots \\
    a_1^{n-1} & a_2^{n-1} & \cdots & a_n^{n-1}.
    \end{pmatrix}$$
    En reconnaissant le déterminant de Vandermonde (traité dans l'<a href="#determinant-de-vandermonde">exercice précédent</a>), on a donc
    $$\det(A) = 2\prod_{k=1}^n a_k\prod_{1\leq i<j\leq n} (a_j-a_i).$$
    Ainsi, $A$ est inversible si et seulement si $n$ est impair, les $a_i$ sont deux à deux distincts et tous non nuls.
</details>

---

<h3 id="determinant-application-transposee">
  <a href="#determinant-application-transposee" class="header">
  Déterminant de l'application transposée</a>
</h3>

On considère l'endomorphisme $\varphi: M\mapsto M^T$ de $\mathcal{M}_n(\mathbb{R})$. Calculer le déterminant de $\varphi$.

<details>
  <summary><b>Remarques</b></summary>
    Cet exercice semblerait avoir été donné à l'oral PC X-ESPCI 2019 (voir <a href="https://beos.prepas.org/sujet.php?id=5473" target="_blank">BEOS 5473</a>).
</details>

<details>
  <summary><b>Indications</b></summary>
    Remarquer que l'endomorphisme $\varphi$ est une symétrie de $\mathcal{M}_n(\mathbb{R})$.
</details>

<details>
  <summary><b>Solution</b></summary>
    Puisque $(M^T)^T = M$, on a clairement $\varphi^2 = \operatorname{Id}$. Ainsi, $\varphi$ est une symétrie de $\mathcal{M}_n(\mathbb{R})$.<br>
    On sait alors que ses valeurs propres sont dans $\{-1,1\}$ (car $X^2-1 = (X-1)(X+1)$ est un polynôme annulateur de $\varphi$).<br>
    Donc
    $$\det(\varphi) = (-1)^{\text{nombre de valeurs propres égales à }-1}$$
    (on savait déjà que $\det(\varphi) = \pm 1$ car $\det(\varphi)^2 = \det(\varphi^2) = \det(\operatorname{Id}) = 1$).<br><br>
    On cherche à déterminer l'espace propre $E_{-1}$ associé à la valeur propre $-1$.<br>
    Soit $M\in\mathcal{M}_n(\mathbb{R})$. On a
    $$M\in E_{-1} \iff \varphi(M) = -M \iff M^T = -M \iff M\in\mathcal{A}_n(\mathbb{R}),$$
    où $\mathcal{A}_n(\mathbb{R})$ est l'ensemble des matrices antisymétriques de $\mathcal{M}_n(\mathbb{R})$.<br>
    Donc $E_{-1} = \mathcal{A}_n(\mathbb{R})$.<br>
    Or, $\mathcal{A}_n(\mathbb{R}) = \operatorname{Vect}((E_{ij} - E_{ji})_{1\leq i<j\leq n})$ où $E_{ij}$ est la matrice élémentaire dont tous les coefficients sont nuls sauf celui de la $i$-ème ligne et de la $j$-ème colonne qui vaut $1$.<br>
    Ainsi, $\displaystyle \dim(\mathcal{A}_n(\mathbb{R})) = \frac{n(n-1)}{2}$ (c'est $\displaystyle \binom{n}{2}$ car on choisit $2$ indices parmi $n$).<br>
    Remarque : on pouvait voir que $\mathcal{M}_n(\mathbb{R}) = \mathcal{S}_n(\mathbb{R})\oplus\mathcal{A}_n(\mathbb{R})$ et puisque $\dim(\mathcal{S}_n(\mathbb{R})) = \frac{n(n+1)}{2}$, on a $\dim(\mathcal{A}_n(\mathbb{R})) = n^2 - \frac{n(n+1)}{2} = \frac{n(n-1)}{2}$.<br>
    Donc
    $$\det(\varphi) = (-1)^{\frac{n(n-1)}{2}}.$$
    On a $\displaystyle \det(\varphi) = 1 \iff \frac{n(n-1)}{2}\equiv 0\ [2] \iff n(n-1)\equiv 0\ [4] \iff n\equiv 0\ [4] \text{ ou } n\equiv 1\ [4].$<br>
    Ainsi,
    $$\begin{cases}
    \det(\varphi) = 1 & \text{si } n\equiv 0\ [4] \text{ ou } n\equiv 1\ [4],\\
    \det(\varphi) = -1 & \text{si } n\equiv 2\ [4] \text{ ou } n\equiv 3\ [4].
    \end{cases}$$
</details>

---
