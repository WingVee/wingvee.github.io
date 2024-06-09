---
layout: default
title: Endormorphismes d'un espace euclidien
permalink: endomorphismes-d'un-espace-euclidien
redirect_from:
    - endomorphismes-espace-euclidien
---

---

<h3 id="inégalité-trace-rang">Une inégalité avec la trace et le rang</h3>

Soit $A\in\mathcal{S}_n(\mathbb{R})$. Montrer que

$$\operatorname{Tr}(A)^2\leq \operatorname{rg}(A)\sum_{1\leq i,j\leq n}a_{ij}^2.$$

<details>
  <summary><strong>Indications</strong></summary>
    Remarquer que $(A\mid B)=\operatorname{Tr}(A^TB)$ est le produit scalaire canonique de $\mathcal{M}_n(\mathbb{R})$.
</details>

<details>
  <summary><strong>Solution 1</strong></summary>
    [Sans utiliser les valeurs propres]<br><br>

    On remarque que $\displaystyle\sum_{1\leq i,j\leq n}a_{ij}^2=\operatorname{Tr}(A^TA)=\operatorname{Tr}(A^2)$ car $A^T=A$.<br>
    Puisque $A$ est symétrique, d'après le théorème spectral, il existe une matrice orthogonale $P$ telle que $A=PDP^T$ où $D$ est une matrice diagonale.<br>
    La trace et le rang étant des invariants de similitude, l'inégalité à démontrer devient
    $$\operatorname{Tr}(D)^2\leq \operatorname{rg}(D)\operatorname{Tr}(D^2).$$

    Posons $k=\operatorname{rg}(A)=\operatorname{rg}(D)$. Sans perte de généralité, on peut supposer que $D=\operatorname{diag}(d_1,\ldots,d_k,0,\ldots,0)$ où $d_1,\ldots,d_k$ sont non nuls.<br>
    D'après l'inégalité de Cauchy-Schwarz, on a

    $$\operatorname{Tr}(D)^2=\left(\sum_{i=1}^kd_i\right)^2\leq \sum_{i=1}^k1 \sum_{i=1}^kd_i^2=k\sum_{i=1}^kd_i^2=\operatorname{rg}(D)\operatorname{Tr}(D^2)$$

    ce qui est bien l'inégalité à démontrer.
</details>

<details>
  <summary><strong>Solution 2</strong></summary>
    [En utilisant les valeurs propres]<br><br>

    On remarque que $\displaystyle\sum_{1\leq i,j\leq n}a_{ij}^2=\operatorname{Tr}(A^TA)=\operatorname{Tr}(A^2)$ car $A^T=A$.<br>
    L'inégalité à démontrer devient alors
    $$\operatorname{Tr}(A)^2\leq\operatorname{rg}(A)\operatorname{Tr}(A^2).$$

    Posons $k=\operatorname{rg}(A)$ et $\lambda_1,\ldots,\lambda_k$ les valeurs propres non nulles de $A$.<br>
    Puisque $\displaystyle\operatorname{Tr}(A)=\sum_{i=1}^k\lambda_i$ et $\displaystyle\operatorname{Tr}(A^2)=\sum_{i=1}^k\lambda_i^2$, et d'après l'inégalité de Cauchy-Schwarz, on a

    $$\operatorname{Tr}(A)^2=\left(\sum_{i=1}^k\lambda_i\right)^2\leq \sum_{i=1}^k1 \sum_{i=1}^k\lambda_i^2=k\sum_{i=1}^k\lambda_i^2=\operatorname{rg}(A)\operatorname{Tr}(A^2)$$

    ce qui est bien l'inégalité à démontrer.
</details>

---
