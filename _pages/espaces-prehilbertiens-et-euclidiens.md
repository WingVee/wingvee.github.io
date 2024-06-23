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

<h3 id="caracterisation-projecteurs-orthogonaux">Caractérisation des projecteurs orthogonaux</h3>

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
