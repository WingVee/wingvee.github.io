---
layout: default
title: Matrices
permalink: matrices
redirect_from:
    - matrice
---

---

<h3 id="groupe-gln-divise-somme-trace">
  <a href="#groupe-gln-divise-somme-trace" class="header">
  Le cardinal d'un sous-groupe fini de $GL_n(\mathbb{R})$ divise la somme des traces de ses éléments</a>
</h3>

Soit $G$ un sous-groupe fini de $GL_n(\mathbb{R})$. Montrer que $\vert G\vert$ divise $\displaystyle\sum_{M\in G}\operatorname{Tr}(M)$.

<details>
  <summary><b>Indications</b></summary>
    <details>
    <summary><u>Indication 1</u></summary>
        Considérer la matrice $\displaystyle A = \frac{1}{\vert G\vert}\sum_{M\in G}M$.
    </details>
    <details>
    <summary><u>Indication 2</u></summary>
        Quelles sont les matrices (vues comme endomorphismes) ayant pour trace un entier ?
    </details>
    <details>
    <summary><u>Indication 3</u></summary>
        Calculer $A^2$.
    </details>
</details>

<details>
  <summary><b>Solution</b></summary>
    Posons $\displaystyle A = \frac{1}{\vert G\vert}\sum_{M\in G}M$.<br>
    Par linéarité de la trace, remarquons que $\vert G\vert$ divise $\displaystyle\sum_{M\in G}\operatorname{Tr}(M)$ si et seulement si $\operatorname{Tr}(A)$ est un entier.<br>
    Nous allons montrer que $A$ est un projecteur, i.e. $A^2 = A$. Puis en utilisant le fait que la trace d'un projecteur est son rang, on aura bien $\operatorname{Tr}(A)$ est un entier et donc $\vert G\vert$ divise $\displaystyle\sum_{M\in G}\operatorname{Tr}(M)$.<br><br>

    Montrons que $A^2 = A$. On a tout d'abord
    $$A^2 = \left(\frac{1}{\vert G\vert}\sum_{M\in G}M\right)^2 = \frac{1}{\vert G\vert^2}\sum_{N\in G}\sum_{M\in G}NM.$$

    Montrons que pour tout $N\in G$, on a $\displaystyle\sum_{M\in G}NM = \sum_{M\in G}M$.<br>
    Puisque $G$ est un groupe, l'application suivante est bien définie et est bijective :
    $$\begin{align*}
        \varphi : G &\longrightarrow G \\
        M &\longmapsto NM.
    \end{align*}$$

    Ainsi, par changement de variable dans la somme, on a
    $$\sum_{M\in G}NM = \sum_{M\in G}M.$$

    Donc
    $$A^2 = \frac{1}{\vert G\vert^2}\sum_{N\in G}\sum_{M\in G}NM = \frac{1}{\vert G\vert^2}\sum_{N\in G}\sum_{M\in G}M = \frac{1}{\vert G\vert}\sum_{M\in G}M = A,$$
    ce qui conclut la preuve de l'exercice.
</details>

---

<h1 id="formulaire">
  <a href="#formulaire" class="header">
  Formulaire</a>
</h1>

<h2 id="matrices-a-connaitre">
  <a href="#matrices-a-connaitre" class="header">
  Matrices à connaître</a>
</h2>

<h3 id="J">
  <a href="#J" class="header">
  Matrice de permutation $J$</a>
</h3>

**Définition**

$$J = \begin{pmatrix}
  0 & 0 & \ldots & 0 & 1 \\
  1 & 0 & \ldots & 0 & 0 \\
  0 & 1 & \ldots & 0 & 0 \\
  \vdots & \vdots & \ddots & \vdots & \vdots \\
  0 & 0 & \ldots & 1 & 0
\end{pmatrix} \in\mathcal{M}_n(\mathbb{R}).$$

$$[J]_{i,j} = \begin{cases}
  1 & \text{si } i \equiv j+1 \ [n] \\
  0 & \text{sinon}.
\end{cases}$$

**Interprétation**

$J$ est la matrice qui envoie le vecteur canonique $e_i$ sur $e_{i+1}$ pour $i\in\\{1,\ldots,n-1\\}$ et $e_n$ sur $e_1$.<br>
Schématiquement,

$$e_1 \xrightarrow{J} e_2 \xrightarrow{J} e_3 \xrightarrow{J} \ldots \xrightarrow{J} e_n \xrightarrow{J} e_1.$$

$J$ est la matrice de permutation $P_\sigma$ associée à la permutation (circulaire de longueur $n$, aussi appelée $n$-cycle) du groupe symétrique $S_n$ donnée par

$$\sigma = \begin{pmatrix} 1 & 2 & 3 & \ldots & n \end{pmatrix} \in S_n.$$

**Propriétés générales**

1. $J$ est une matrice de permutation, donc inversible ($GL_n(\mathbb{R})$) et même orthogonale ($O_n(\mathbb{R})$).
2. $J$ est une matrice compagnon, associée au polynôme (caractéristique) $X^n - 1$.
3. $J$ est un élément d'ordre $n$ de $GL_n(\mathbb{R})$ : $J^n = I_n$.
4. $J$ est une matrice circulante. En fait, toute matrice circulante est une combinaison linéaire de puissances de $J$, i.e. un polynôme en $J$.
5. Puissances de $J$ :<br>
  En remarquant que $J$ envoie $e_i$ sur $e_{i+1}$ pour $i\in\\{1,\ldots,n-1\\}$ et $e_n$ sur $e_1$, alors les comportements de $J^k$ pour $k\in\\{1,\ldots,n-1\\}$ se déduisent facilement :

  $$\begin{equation*}
    \begin{aligned}
      e_1 &\overset{J}{\longrightarrow} e_2\\
      e_2 &\longrightarrow e_3\\
      &\ \ \ \vdots\\
      e_{n-1} &\longrightarrow e_n\\
      e_n &\longrightarrow e_1
    \end{aligned}
    \qquad
    \begin{aligned}
      e_1 &\overset{J^2}{\longrightarrow} e_3\\
      e_2 &\longrightarrow e_4\\
      &\ \ \ \vdots\\
      e_{n-2} &\longrightarrow e_n\\
      e_{n-1} &\longrightarrow e_1\\
      e_n &\longrightarrow e_2
    \end{aligned}
    \qquad
    \begin{aligned}
      e_1 &\overset{J^k}{\longrightarrow} e_{k+1}\\
      e_2 &\longrightarrow e_{k+2}\\
      &\ \ \ \vdots\\
      e_{n-k} &\longrightarrow e_n\\
      e_{n-k+1} &\longrightarrow e_1\\
      &\ \ \ \vdots\\
      e_n &\longrightarrow e_k
    \end{aligned}
    \qquad
    \begin{aligned}
      e_1 &\overset{J^{n-1}}{\longrightarrow} e_n\\
      e_2 &\longrightarrow e_1\\
      &\ \ \ \vdots\\
      e_{n-1} &\longrightarrow e_{n-2}\\
      e_n &\longrightarrow e_{n-1}
    \end{aligned}
    \qquad
    \begin{aligned}
      e_1 &\overset{J^n=I_n}{\longrightarrow} e_1\\
      e_2 &\longrightarrow e_2\\
      &\ \ \ \vdots\\
      e_{n-1} &\longrightarrow e_{n-1}\\
      e_n &\longrightarrow e_n
    \end{aligned}
  \end{equation*}$$

<ol>
  Ainsi, lorsqu'on passe de $P^k$ à $P^{k+1}$, on décale la "diagonale" (les 1) vers le bas et le 1 qui disparaît à la dernière ligne réapparaît à la première ligne.
</ol>

$$J^2 = \begin{pmatrix}
  0 & 0 & \ldots & 0 & 1 & 0 \\
  0 & 0 & \ldots & 0 & 0 & 1 \\
  1 & 0 & \ldots & 0 & 0 & 0 \\
  0 & 1 & \ldots & 0 & 0 & 0 \\
  \vdots & \vdots & \ddots & \vdots & \vdots & \vdots \\
  0 & 0 & \ldots & 1 & 0 & 0
\end{pmatrix}, \quad \dots \quad, \ J^{n-1} = J^{-1} = J^T = \begin{pmatrix}
  0 & 1 & 0 & \ldots & 0 & 0 \\
  0 & 0 & 1 & \ldots & 0 & 0 \\
  \vdots & \vdots & \vdots & \ddots & \vdots & \vdots \\
  0 & 0 & 0 & \ldots & 1 & 0 \\
  0 & 0 & 0 & \ldots & 0 & 1 \\
  1 & 0 & 0 & \ldots & 0 & 0 \\
\end{pmatrix}.$$

**Réduction**

- Polynôme caractéristique :

  $$\chi_J(X) = X^n - 1 = \prod_{k=0}^{n-1}(X - \omega^k),\quad \omega = e^{2i\pi/n}.$$

- Spectre (dans $\mathbb C$) : ensemble des racines $n$-ièmes de l'unité :

$$\operatorname{Sp}(J) = \left\{\omega^k=\exp\left(\frac{2ik\pi}{n}\right) \mid k\in\{0,\ldots,n-1\}\right\}.$$

- Trace et déterminant :

$$\operatorname{Tr}(J) = 0 \quad \text{et} \quad \det(J) = (-1)^{n-1}.$$

- Vecteurs propres : $JX_k = \omega^kX_k$ avec

$$X_k = \begin{pmatrix} 1 \\ \omega^k \\ \omega^{2k} \\ \vdots \\ \omega^{(n-1)k} \end{pmatrix},\quad k\in\{0,\ldots,n-1\},\ \omega = e^{2i\pi/n}.$$

- Diagonalisabilité :<br>
$J$ est diagonalisable sur $\mathbb R$ si et seulement si $n\in\{1,2\}$.<br>
$J$ est diagonalisable sur $\mathbb C$ (valeurs propres distinctes).<br>
En notant :

$$P = [X_0\ \ X_1\ \ \ldots\ \ X_{n-1}] = \begin{pmatrix}
  1 & 1 & \ldots & 1 \\
  1 & \omega & \ldots & \omega^{n-1} \\
  1 & \omega^2 & \ldots & \omega^{2(n-1)} \\
  \vdots & \vdots & \ddots & \vdots \\
  1 & \omega^{n-1} & \ldots & \omega^{(n-1)(n-1)}
\end{pmatrix}$$

<ol>
  la matrice de passage de la base canonique à la base des vecteurs propres, on a 
  
  $$J = P\operatorname{diag}(1,\omega,\ldots,\omega^{n-1})P^{-1}.$$

  D'ailleurs, $P$ est une matrice de Vandermonde.
</ol>

---
