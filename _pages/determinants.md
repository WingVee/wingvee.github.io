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
