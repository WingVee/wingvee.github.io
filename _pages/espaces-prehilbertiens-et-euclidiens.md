---
layout: default
title: Espaces préhilbertiens et euclidiens
permalink: espaces-prehilbertiens-et-euclidiens
redirect_from:
  - espaces-préhilbertiens
  - espaces-prehilbertiens
  - espaces-euclidiens
---

---

<h3 id="caracterisation-projecteurs-orthogonaux">
  <a href="#caracterisation-projecteurs-orthogonaux" class="header">
  Caractérisation des projecteurs orthogonaux</a>
</h3>

Soit $p$ un projecteur d'un espace préhilbertien réel $E$. Montrer que les assertions suivantes sont équivalentes :
1. $p$ est un projecteur orthogonal.
2. $\forall x\in E,\ \Vert p(x)\Vert\leq\Vert x\Vert$.
3. $\forall (x,y)\in E^2,\ \langle p(x), y\rangle=\langle x, p(y)\rangle$.

<details>
	<summary><b>Indications</b></summary>
		<details>
			<summary>1 $\Rightarrow$ 2</summary>
				Utiliser la décomposition $x=p(x)+(x-p(x))$ et le fait que $E=\operatorname{Ker}\ p\oplus^{\perp}\operatorname{Im}\ p$.
		</details>
		<details>
			<summary>2 $\Rightarrow$ 1</summary>
				Considérer $x+\lambda y$ avec $\lambda\in\mathbb{R}$, $x\in\operatorname{Ker}\ p$ et $y\in\operatorname{Im}\ p$. Montrer que $\langle x, y\rangle=0$.
		</details>
		<details>
			<summary>1 $\Rightarrow$ 3</summary>
				Utiliser la décomposition $x=p(x)+(x-p(x))$ et le fait que $E=\operatorname{Ker}\ p\oplus^{\perp}\operatorname{Im}\ p$.
		</details>
		<details>
			<summary>3 $\Rightarrow$ 1</summary>
				Considérer $x\in\operatorname{Ker}\ p$ et $y\in\operatorname{Im}\ p$ et montrer que $\langle x, y\rangle=0$.
		</details>
</details>

<details>
  <summary><b>Solution</b></summary>
		<details>
			<summary>1 $\Rightarrow$ 2</summary>
				<ol>
					Soit $p$ est un projecteur orthogonal. On a $E=\operatorname{Ker}\ p\oplus^{\perp}\operatorname{Im}\ p$.<br>
					Soit $x\in E$. On décompose : $x=(x-p(x))+p(x)$ dans $E=\operatorname{Ker}\ p\oplus^{\perp}\operatorname{Im}\ p$.<br>
					D'après le théorème de Pythagore, on a
					$$\Vert x\Vert^2=\Vert x-p(x)\Vert^2+\Vert p(x)\Vert^2.$$
					Donc $\Vert p(x)\Vert\leq\Vert x\Vert$.
				</ol>
		</details>
		<details>
			<summary>2 $\Rightarrow$ 1</summary>
				<ol>
					Soit $p$ un projecteur tel que $\forall x\in E,\ \Vert p(x)\Vert\leq\Vert x\Vert$. Il s'agit de montrer que $\operatorname{Ker}\ p\perp\operatorname{Im}\ p$.<br>
					Soient $x\in\operatorname{Ker}\ p$ et $y\in\operatorname{Im}\ p$. Montrons que $\langle x, y\rangle=0$.<br><br>
					Nous allons considérer $x+\lambda y$ pour $\lambda\in\mathbb{R}$.<br>
					On a d'une part :
					$$\Vert x+\lambda y\Vert^2=\Vert x\Vert^2+2\lambda\langle x, y\rangle+\lambda^2\Vert y\Vert^2.$$
					D'autre part, en exploitant le fait que $p(x)=0$ et $p(y)=y$, on a :
					$$\Vert p(x+\lambda y)=\Vert p(x)+\lambda p(y)\Vert^2=\lambda^2\Vert y\Vert^2.$$
					Donc, en utilisant l'hypothèse $\Vert p(x+\lambda y)\Vert\leq\Vert x+\lambda y\Vert$, on a :
					$$\lambda^2\Vert y\Vert^2\leq\Vert x\Vert^2+2\lambda\langle x, y\rangle+\lambda^2\Vert y\Vert^2.$$
					Donc pour tout $\lambda\in\mathbb{R}$, on a :
					$$0\leq\Vert x\Vert^2+2\lambda\langle x, y\rangle.$$
					Cela n'est possible que si $\langle x, y\rangle=0$. D'où le résultat.
				</ol>
		</details>
		<details>
			<summary>1 $\Rightarrow$ 3</summary>
				<ol>
					Soit $p$ un projecteur orthogonal. On a $E=\operatorname{Ker}\ p\oplus^{\perp}\operatorname{Im}\ p$.<br>
					Soit $(x,y)\in E^2$. On a $y=p(y)+(y-p(y))$ avec $p(y)\in\operatorname{Im}\ p$ et $y-p(y)\in\operatorname{Ker}\ p$.<br>
					On a alors :
					$$\langle p(x), y\rangle=\langle p(x), p(y)+(y-p(y))\rangle = \langle p(x), p(y)\rangle+(p(x), y-p(y)) = \langle p(x), p(y)\rangle.$$
					Par symétrie, on a donc $\langle p(x), y\rangle = \langle p(x), p(y)\rangle = \langle x, p(y)\rangle$.
				</ol>
		</details>
		<details>
			<summary>3 $\Rightarrow$ 1</summary>
				<ol>
					Soit $p$ un projecteur tel que $\forall (x,y)\in E^2,\ \langle p(x), y\rangle=\langle x, p(y)\rangle$.<br>
					Il s'agit de montrer que $\operatorname{Ker}\ p\perp\operatorname{Im}\ p$.<br>
					Soient $x\in\operatorname{Ker}\ p$ et $y\in\operatorname{Im}\ p$. Montrons que $\langle x, y\rangle=0$.<br>
					Puisque $p(y)=y$ et $p(x)=0$, et en exploitant l'hypothèse de départ, on a :
					$$\langle x, y\rangle=\langle x, p(y)\rangle=\langle p(x), y\rangle=\langle 0, y\rangle=0.$$
					D'où le résultat.
				</ol>
		</details>
</details>

---

<h3 id="inegalite-trace-carree">
  <a href="#inegalite-trace-carree" class="header">
  Inégalité $\operatorname{Tr}(M^2) \leq \operatorname{Tr}(M^TM)$</a>
</h3>

Soient $M = (a_{ij})_{1\leq i,j\leq n}\in\mathcal{M}_n(\mathbb{R})$. Montrer que :

$$\operatorname{Tr}(M^2) \leq \operatorname{Tr}(M^TM).$$

Que peut-on dire du cas d'égalité ?

Interpréter cette inégalité en utilisant le produit scalaire canonique de $\mathcal{M}_n(\mathbb{R})$.

<details>
  <summary><b>Indications</b></summary>
    Considérer $\operatorname{Tr}(M^TM)-\operatorname{Tr}(M^2)$ et calculer.<br><br>
    Le produit scalaire canonique de $\mathcal{M}_n(\mathbb{R})$ est défini par $\displaystyle \langle A, B\rangle = \operatorname{Tr}(A^TB) = \operatorname{Tr}(AB^T) = \sum_{1\leq i,j\leq n} a_{ij}b_{ij}$.<br>
    Il s'agit d'interpréter l'inégalité $\langle M, M^T\rangle \leq \langle M, M\rangle$.
</details>

<details>
  <summary><b>Solution</b></summary>
    On a :
    $$\operatorname{Tr}(M^2) = \sum_{i=1}^n [M^2]_{ii} = \sum_{i=1}^n \left(\sum_{j=1}^n a_{ij}a_{ji}\right) = \sum_{1\leq i,j\leq n} a_{ij}a_{ji} = 2\sum_{1\leq i < j\leq n} a_{ij}a_{ji} + \sum_{i=1}^n a_{ii}^2$$
    $$\operatorname{Tr}(M^TM) = \sum_{i=1}^n [M^TM]_{ii} = \sum_{i=1}^n \left(\sum_{j=1}^n a_{ij}^2\right) = \sum_{1\leq i,j\leq n} a_{ij}^2 = \sum_{1\leq i < j\leq n} (a_{ij}^2+a_{ji}^2) + \sum_{i=1}^n a_{ii}^2$$
    Donc
    $$\operatorname{Tr}(M^TM) - \operatorname{Tr}(M^2) = \sum_{1\leq i < j\leq n} (a_{ij}^2+a_{ji}^2) - 2\sum_{1\leq i < j\leq n} a_{ij}a_{ji} = 2\sum_{1\leq i < j\leq n} (a_{ij}-a_{ji})^2 \geq 0.$$
    Ainsi, $\operatorname{Tr}(M^2) \leq \operatorname{Tr}(M^TM)$ avec égalité si et seulement si $a_{ij} = a_{ji}$ pour tout $1\leq i < j\leq n$, i.e. $M = M^T$.<br>
    $\square$<br><br>
    Une autre manière de montrer le résultat est de voir que :
    $$\operatorname{Tr}(M^TM) - \operatorname{Tr}(M^2) = \operatorname{Tr}(M^TM - M^2) = \operatorname{Tr}((M^T-M)M) = \langle M-M^T, M\rangle.$$
    En posant $\displaystyle S = \frac{M+M^T}{2}$ symétrique et $\displaystyle A = \frac{M-M^T}{2}$ antisymétrique, on a $M = S+A$ (similairement à la décomposition des fonctions réelles en somme d'une fonction paire et d'une fonction impaire).<br>
    De plus, on a $\langle S, A\rangle = \operatorname{Tr}(S^TA) = \operatorname{Tr}(SA) = \operatorname{Tr}((SA)^T) = \operatorname{Tr}(A^TS^T) = -\operatorname{Tr}(AS^T) = -\langle S, A\rangle$.<br>
    Donc $\langle S, A\rangle = 0$.<br>
    Ainsi, on a
    $$\langle M-M^T, M\rangle = \langle 2A, S+A\rangle = \langle A, S\rangle + \langle A, A\rangle = 0 + \langle A, A\rangle = \Vert A\Vert^2 \geq 0$$
    avec égalité si et seulement si $A = 0$, i.e. $M = S\in\mathcal{S}_n(\mathbb{R})$.<br>
    $\square$<br><br>
    L'inégalité $\operatorname{Tr}(M^2) \leq \operatorname{Tr}(M^TM)$ s'écrit
    $$\langle M, M^T\rangle \leq \langle M, M\rangle.$$
    Or, pour tout produit scalaire dans un espace préhilbertien $E$, l'inégalité suivante est toujours vérifiée pour tout $(x,y)\in E^2$ tel que $\Vert x\Vert = \Vert y\Vert$ :
    $$\langle x, y\rangle \leq \langle x, x\rangle = \Vert x\Vert^2$$
    avec égalité si et seulement si $x = y$.<br>
    En effet, l'inégalité de Cauchy-Schwarz s'écrit $|\langle x, y\rangle| \leq \Vert x\Vert\Vert y\Vert = \Vert x\Vert^2$ avec égalité si et seulement si $x$ et $y$ sont colinéaires, et on vérifie aisément que $\langle x, y\rangle = \Vert x\Vert^2$ si et seulement si $x = y$.<br>
    Ainsi, avec $x = M$ et $y = M^T$, puisque $\Vert M^T\Vert = \Vert M\Vert$, on a bien l'inégalité $\langle M, M^T\rangle \leq \langle M, M\rangle$ avec égalité si et seulement si $M = M^T$.
</details>

---
