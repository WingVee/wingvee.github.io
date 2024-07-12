---
layout: default
title: Dénombrement
permalink: denombrement
redirect_from:
  - dénombrement
  - combinatoire
---

---

<h3 id="formule-du-crible">
  <a href="#formule-du-crible" class="header">
  Formule du crible</a>
</h3>

Soient $A_1, \ldots, A_n$ des ensembles finis. On note $|A| = \operatorname{Card}(A)$ le cardinal d'un ensemble $A$.<br>
Montrer la formule du crible (de Poincaré, aussi appelée <a href="https://fr.wikipedia.org/wiki/Principe_d'inclusion-exclusion" target="_blank">principe d'inclusion-exclusion</a>) :

$$\left|\bigcup_{i=1}^n A_i\right| = \sum_{k=1}^n (-1)^{k-1} \sum_{1\leq i_1 < \ldots < i_k \leq n} \left|\bigcap_{j=1}^k A_{i_j}\right|.$$

<details>
  <summary><b>Remarque</b></summary>
    La formule du crible s'écrit aussi :
    $$\left|\bigcup_{i=1}^n A_i\right| = \sum_{k=1}^n (-1)^{k-1} \sum_{\substack{J\subset\{1,\ldots,n\}\\|J|=k}} \left|\bigcap_{j\in J} A_j\right|.$$
    Plus généralement, si $(A_i)_{i\in I}$ est une famille finie d'ensembles finis, on a :
    $$\left|\bigcup_{i\in I} A_i\right| = \sum_{\substack{J\subset I\\J\neq\emptyset}} (-1)^{|J|-1} \left|\bigcap_{j\in J} A_j\right|.$$
    Des démonstrations de ces formules peuvent être trouvées sur <a href="https://fr.wikiversity.org/wiki/Formule_du_crible/Démonstration_de_la_formule_du_crible" target="_blank">Wikiversité</a>.
</details>

<details>
  <summary><b>Indications</b></summary>
		<details>
			<summary><u>Indication solution 1</u></summary>
				Récurrence en utilisant $|A\cup B| = |A| + |B| - |A\cap B|$ et puis bien réarranger les termes.
		</details>
    <details>
			<summary><u>Indication solution 2</u></summary>
				Utiliser les fonctions indicatrices : $\mathbb 1_A(x) = 1$ si $x\in A$ et $\mathbb 1_A(x) = 0$ sinon.<br>
				Puis exploiter leurs propriétés de l'intersection, l'union et le passage au complémentaire (cf. l'exercice sur les <a href="/raisonnement-et-vocabulaire-ensembliste#fonction-indicatrice-proprietes" target="_blank">propriétés des fonctions indicatrices</a>).
				<details>
					<summary><u>Propriétés des fonctions indicatrices</u></summary>
						$$\mathbb 1_{A\cap B} = \mathbb 1_A \cdot \mathbb 1_B \qquad \mathbb 1_{A\cup B} = \mathbb 1_A + \mathbb 1_B - \mathbb 1_A \cdot \mathbb 1_B \qquad \mathbb 1_{\overline{A}} = 1 - \mathbb 1_A.$$
						$$|A| = \sum_{x\in A} \mathbb 1_A(x) = \sum_{x\in E} \mathbb 1_A(x) \quad \text{pour tout ensemble } A\subset E.$$
				</details>
    </details>
</details>

<details>
  <summary><b>Solution 1</b></summary>
    Montrons la formule du crible par récurrence sur $n\in\mathbb{N}^*$.<br>
    <li>
      <u>Initialisation :</u><br>
      Pour $n=1$, on a
      $$\left|\bigcup_{i=1}^1 A_i\right| = |A_1| \quad \text{et} \quad \sum_{k=1}^1 (-1)^{k-1} \sum_{1\leq i_1 \leq 1} \left|\bigcap_{j=1}^k A_{i_j}\right| = (-1)^0 |A_1| = |A_1|.$$
      Donc la formule du crible est vraie pour $n=1$.
    </li>
    <li>
      <u>Hérédité :</u><br>
      $$\begin{align*}
      \left|\bigcup_{i=1}^{n+1} A_i\right| &=\left|\left(\bigcup_{i=1}^{n} A_i\right) \cup A_{n+1}\right|\\
      &=\left|\bigcup_{i=1}^{n} A_i\right| + |A_{n+1}| - \left|\left(\bigcup_{i=1}^{n} A_i\right) \cap A_{n+1}\right| \quad (|A\cup B| = |A| + |B| - |A\cap B|)\\
      &=\left|\bigcup_{i=1}^{n} A_i\right| + |A_{n+1}| - \left|\bigcup_{i=1}^{n} (A_i \cap A_{n+1})\right| \quad \text{(distributivité de l'intersection sur l'union)}\\
      &=\sum_{k=1}^n (-1)^{k-1} \sum_{1\leq i_1 < \ldots < i_k \leq n} \left|\bigcap_{j=1}^k A_{i_j}\right| + |A_{n+1}|\\
      &\quad - \sum_{k=1}^n (-1)^{k-1} \sum_{1\leq i_1 < \ldots < i_k \leq n} \left|\bigcap_{j=1}^k A_{i_j} \cap A_{n+1}\right| \quad \text{(par hypothèse de récurrence)}\\
      &=\sum_{k=1}^n (-1)^{k-1} \sum_{1\leq i_1 < \ldots < i_k \leq n} \left|\bigcap_{j=1}^k A_{i_j}\right| + |A_{n+1}| + \sum_{k=1}^n (-1)^k \sum_{1\leq i_1 < \ldots < i_k \leq n} \left|\bigcap_{j=1}^k A_{i_j} \cap A_{n+1}\right|\\
      &=\sum_{k=1}^n (-1)^{k-1} \sum_{1\leq i_1 < \ldots < i_k \leq n} \left|\bigcap_{j=1}^k A_{i_j}\right| + \sum_{k=0}^n (-1)^k \sum_{1\leq i_1 < \ldots < i_k < i_{k+1} = n+1} \left|\bigcap_{j=1}^k A_{i_j}\right|\\
      &=\sum_{k=1}^{n+1} (-1)^{k-1} \sum_{1\leq i_1 < \ldots < i_k < n+1} \left|\bigcap_{j=1}^k A_{i_j}\right| + \sum_{k=1}^{n+1} (-1)^{k-1} \sum_{1\leq i_1 < \ldots < i_k = n+1} \left|\bigcap_{j=1}^k A_{i_j}\right|\\
      &=\sum_{k=1}^{n+1} (-1)^{k-1} \sum_{1\leq i_1 < \ldots < i_k \leq n+1} \left|\bigcap_{j=1}^k A_{i_j}\right|.
      \end{align*}$$
    </li>
    Ce qui conclut la preuve par récurrence.
</details>

<details>
  <summary><b>Solution 2</b></summary>
    Avec les fonctions indicatrices, nous pouvons montrer la formule du crible très simplement.<br>
    Soit $\mathbb 1_A$ la fonction indicatrice de l'ensemble $A$, i.e. $\mathbb 1_A(x) = 1$ si $x\in A$ et $\mathbb 1_A(x) = 0$ sinon.<br>
    Les fonctions indicatrices ont pour propriétés suivantes pour l'intersection, l'union et le passage au complémentaire :
    $$\mathbb 1_{A\cap B} = \mathbb 1_A \cdot \mathbb 1_B \qquad \mathbb 1_{A\cup B} = \mathbb 1_A + \mathbb 1_B - \mathbb 1_A \cdot \mathbb 1_B \qquad \mathbb 1_{\overline{A}} = 1 - \mathbb 1_A.$$
    De plus, il y a un lien entre le cardinal d'un ensemble $A\subset E$ et sa fonction indicatrice :
    $$|A| = \sum_{x\in A} \mathbb 1_A(x) = \sum_{x\in E} \mathbb 1_A(x).$$
    On a alors :
    $$\begin{align*}
    \mathbb 1_{\bigcup_{i=1}^n A_i} &= 1 - \mathbb 1_{\overline{\bigcup_{i=1}^n A_i}}\\
    &= 1 - \mathbb 1_{\bigcap_{i=1}^n \overline{A_i}}\\
    &= 1 - \prod_{i=1}^n \mathbb 1_{\overline{A_i}}\\
    &= 1 - \prod_{i=1}^n (1 - \mathbb 1_{A_i})\\
    &= 1 - \sum_{k=0}^n \sum_{1\leq i_1 < \ldots < i_k \leq n} 1^{n-k}\prod_{j=1}^k (-\mathbb 1_{A_{i_j}})\\
    &= -\sum_{k=1}^n (-1)^k \sum_{1\leq i_1 < \ldots < i_k \leq n} \prod_{j=1}^k \mathbb 1_{A_{i_j}}\\
    &= \sum_{k=1}^n (-1)^{k-1} \sum_{1\leq i_1 < \ldots < i_k \leq n} \mathbb 1_{\bigcap_{j=1}^k A_{i_j}}.
    \end{align*}$$
    Donc, en sommant sur tous les éléments de l'ensemble $\displaystyle A=\bigcup_{i=1}^n A_i$, on obtient la formule du crible :
    $$\begin{align*}
    \left|\bigcup_{i=1}^n A_i\right| &= \sum_{x\in A} \mathbb 1_{\bigcup_{i=1}^n A_i}(x)\\
    &= \sum_{x\in A} \sum_{k=1}^n (-1)^{k-1} \sum_{1\leq i_1 < \ldots < i_k \leq n} \mathbb 1_{\bigcap_{j=1}^k A_{i_j}}(x)\\
    &= \sum_{k=1}^n (-1)^{k-1} \sum_{1\leq i_1 < \ldots < i_k \leq n} \sum_{x\in A} \mathbb 1_{\bigcap_{j=1}^k A_{i_j}}(x)\\
    &= \sum_{k=1}^n (-1)^{k-1} \sum_{1\leq i_1 < \ldots < i_k \leq n} \left|\bigcap_{j=1}^k A_{i_j}\right|.
    \end{align*}$$
</details>

---
