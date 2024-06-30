---
layout: default
title: Endormorphismes d'un espace euclidien
permalink: endomorphismes-d'un-espace-euclidien
redirect_from:
    - endomorphismes-espace-euclidien
    - endomorphismes-des-espaces-euclidiens
---

---

<h3 id="valeurs-propres-complexes-matrices-orthogonales">
  <a href="#valeurs-propres-complexes-matrices-orthogonales" class="header">
  Valeurs propres complexes des matrices orthogonales</a>
</h3>

Soit $M\in\mathcal{O}_n(\mathbb{R})$. Montrer que les valeurs propres complexes de $M$ sont de module 1.

<details>
  <summary><b>Indications</b></summary>
  <details>
    <summary><u>Indication solution 1</u></summary>
        Considérer $M+M^{-1}$.
    </details>
    <details>
    <summary><u>Indication solution 2</u></summary>
        Considérer $X^T\overline{X}$ où $X$ est un vecteur propre complexe associé à une valeur propre complexe de $M$ et $\overline{X}$ désigne le vecteur dont les coefficients sont les conjugués complexes des coefficients de $X$.
    </details>
</details>

<details>
  <summary><b>Solution 1</b></summary>
    On remarque que $M+M^{-1}$ est symétrique car $(M+M^{-1})^T=M^T+(M^T)^{-1}=M^{-1}+M$.<br>
    Soit $\lambda\in\mathbb{C}$ une valeur propre de $M$ et $X$ un vecteur propre (complexe) associé. On a

    $$(M+M^{-1})X=\lambda X+M^{-1}X=\lambda X+\frac{1}{\lambda}X=\left(\lambda+\frac{1}{\lambda}\right)X.$$

    Donc $\displaystyle\lambda+\frac{1}{\lambda}$ est une valeur propre de $M+M^{-1}\in\mathcal{S}_n(\mathbb{R})$ et est donc réelle d'après le théorème spectral.<br>
    Une étude simple des nombres complexes montre que $\lambda+\lambda^{-1}$ est réel si et seulement si $\vert\lambda\vert=1$ ou $\lambda\in\mathbb{R}$.<br><br>

    Il reste a montrer que si $\lambda$ est une valeur propre réelle de $M$, alors $\lambda=\pm 1$.<br>
    Si $\lambda\in\mathbb{R}$ est une valeur propre réelle de $M$, alors il existe $X$ un vecteur propre réel associé. On a

    $$\Vert MX\Vert^2=\Vert\lambda X\Vert^2=\lambda^2\Vert X\Vert^2.$$

    Or, $M$ est orthogonale donc préserve les normes, i.e.

    $$\Vert MX\Vert^2=\Vert X\Vert^2.$$

    Donc $\Vert X\Vert^2=\lambda^2\Vert X\Vert^2$, i.e. $\lambda^2=1$, ce qui donne $\lambda=\pm 1$.
</details>

<details>
  <summary><b>Solution 2</b></summary>
    Soit $\lambda\in\mathbb{C}$ une valeur propre de $M$ et $X$ un vecteur propre (complexe) associé. Montrons que $\lambda\overline{\lambda}=\vert\lambda\vert^2=1$.<br>
    En utilisant le fait que $MX=\lambda X$, $M^TM=I_n$ et que $\overline{MX}=M\overline{X}$, on a :
    $$X^T\overline{X}=X^T(M^TM)\overline{X}=(MX)^T\overline{MX}=(\lambda X)^T(\overline{\lambda X})=\vert\lambda\vert^2X^T\overline{X}.$$

    En écrivant $X=\begin{pmatrix}x_1\\\vdots\\x_n\end{pmatrix}$, on a $\displaystyle X^T\overline{X}=\sum_{i=1}^n\vert x_i\vert^2$ qui est non nul car $X$ est un vecteur propre donc non nul.<br><br>
    Ainsi, $X^T\overline{X}=\vert\lambda\vert^2X^T\overline{X}$ et $X^T\overline{X}\neq 0$ entraînent que $\vert\lambda\vert^2=1$, i.e. $\lambda$ est de module 1.
</details>

---

<h3 id="inegalite-trace-rang">
  <a href="#inegalite-trace-rang" class="header">
  Une inégalité avec la trace et le rang</a>
</h3>

Soit $A\in\mathcal{S}_n(\mathbb{R})$. Montrer que

$$\operatorname{Tr}(A)^2\leq \operatorname{rg}(A)\sum_{1\leq i,j\leq n}a_{ij}^2.$$

<details>
  <summary><b>Indications</b></summary>
    Remarquer que $(A\mid B)=\operatorname{Tr}(A^TB)$ est le produit scalaire canonique de $\mathcal{M}_n(\mathbb{R})$.
</details>

<details>
  <summary><b>Solution 1</b></summary>
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
  <summary><b>Solution 2</b></summary>
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

<h3 id="cns-commutation-transposee">
  <a href="#cns-commutation-transposee" class="header">
  Condition (nécessaire et) suffisante pour que $A$ et $A^T$ commutent</a>
</h3>

Soit $A\in\mathcal{M}_n(\mathbb{R})$ telle que

$$\operatorname{Sp}(A^TA - AA^T)\subset\mathbb{R}_+.$$

Montrer que $A$ et $A^T$ commutent.

<details>
  <summary><b>Indications</b></summary>
    Considérer $S=A^TA - AA^T$ et $\operatorname{Tr}(S)$.
</details>

<details>
  <summary><b>Solution</b></summary>
    Posons $S=A^TA - AA^T$.<br>
    En remarquant que $S$ est symétrique réelle et est donc diagonalisable, il suffit de montrer que toutes les valeurs propres de $S$ sont nulles.<br>
    On a $\operatorname{Tr}(S) = \operatorname{Tr}(A^TA - AA^T) = \operatorname{Tr}(A^TA) - \operatorname{Tr}(AA^T) = 0$, donc la somme des valeurs propres de $S$ est nulle.<br>
    Or, les valeurs propres de $S$ sont positives par hypothèse, et ici de somme nulle, donc elles sont toutes nulles.<br>
    Puisque $S$ est diagonalisable de seule valeur propre 0, on a alors $S=0$, i.e. $A^TA = AA^T$.<br>
    Ainsi, $A$ et $A^T$ commutent.
</details>

---
