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

<h3 id="utilisation-des-fonctions-indicatrices-pour-denombrer">
  <a href="#utilisation-des-fonctions-indicatrices-pour-denombrer" class="header">
  Utilisation des fonctions indicatrices pour dénombrer</a>
</h3>

Soit $E$ un ensemble fini de cardinal $n$.<br>
Montrer les égalités suivantes en utilisant les fonctions indicatrices et les propriétés associées (voir remarque ci-dessous) :

1. $\displaystyle\sum_{A\subseteq E} \|A\| = n2^{n-1}$.
2. $\displaystyle\sum_{A,B\subseteq E} \|A\cap B\| = n(2^{n-1})^2 = n4^{n-1}$.
3. $\displaystyle\sum_{A_1,\ldots,A_p\subseteq E} \|A_1\cap\ldots\cap A_p\| = n(2^{n-1})^p$.
4. $\displaystyle\sum_{A,B\subseteq E} \|A\cup B\| = n\ 3\cdot4^{n-1}$.
5. $\displaystyle\sum_{A,B\subseteq E} \|A\Delta B\| = n\ 2\cdot4^{n-1}\quad$ où $\quad A\Delta B = (A\cup B)\setminus(A\cap B)$ est la différence symétrique de $A$ et $B$.

<details>
  <summary><b>Remarques</b></summary>
    Les fonctions indicatrices peuvent former un outil extrêmement puissant et utile pour dénombrer et manipuler des ensembles. Grâce aux propriétés des fonctions indicatrices avec les opérations ensemblistes (vues et démontrées dans cet <a href="/raisonnement-et-vocabulaire-ensembliste#fonction-indicatrice-proprietes" target="_blank">exercice sur les propriétés des fonctions indicatrices</a>), nous allons pouvoir retrouver et démontrer aisément certaines formules de dénombrement.<br><br>
    Rappelons les propriétés des fonctions indicatrices ($A,B\subseteq E$) :
    $$\mathbb 1_\emptyset = 0 \qquad \mathbb 1_E = 1$$
    $$\mathbb 1_{A\cap B} = \mathbb 1_A \cdot \mathbb 1_B \qquad \mathbb 1_{A\cup B} = \mathbb 1_A + \mathbb 1_B - \mathbb 1_A \cdot \mathbb 1_B \qquad \mathbb 1_{\overline{A}} = 1 - \mathbb 1_A$$
    $$\mathbb 1_{A\Delta B} = (\mathbb 1_A - \mathbb 1_B)^2 = |\mathbb 1_A - \mathbb 1_B| = \max(\mathbb 1_A,\mathbb 1_B) - \min(\mathbb 1_A,\mathbb 1_B) = \mathbb 1_A + \mathbb 1_B - 2\mathbb 1_A \cdot \mathbb 1_B$$
    $$|A| := \operatorname{Card}(A) =  \sum_{x\in A} 1 = \sum_{x\in A} \mathbb 1_A(x) = \sum_{x\in E} \mathbb 1_A(x)$$
    Attention, cette technique de dénombrement est très puissante mais n'est utilisable que pour des calcul de cardinaux ou de sommes de cardinaux utilisant des opération ensemblistes élémentaires (union, intersection, différence symétrique, etc.). Si l'on rajoute des conditions supplémentaires, cela sera plus délicat et nécessitera des considérations combinatoires.
</details>

<details>
  <summary><b>Indications</b></summary>
    Lemmes utiles :
    $$\sum_{A\subseteq E} \mathbb 1_A(x) = 2^{n-1} \quad \text{pour tout } x\in E.$$
    $$\sum_{A\subseteq E} 1 = |\mathcal{P}(E)| = 2^n.$$
</details>

<details>
  <summary><b>Solution</b></summary>
    Avant de commencer, démontrons les deux lemmes suivants :
    $$\sum_{A\subseteq E} \mathbb 1_A(x) = 2^{n-1} \quad \text{pour tout } x\in E.$$
    $$\sum_{A\subseteq E} 1 = |\mathcal{P}(E)| = 2^n.$$
    <li>
      <u>Lemme 1 :</u><br>
      Pour tout $x\in E$, on a
      $$\begin{align*}
      \sum_{A\subseteq E} \mathbb 1_A(x) &= \sum_{\substack{A\subseteq E\\x\in A}} \mathbb 1_A(x) + \sum_{\substack{A\subseteq E\\x\notin A}} \mathbb 1_A(x)\\
      &= \sum_{\substack{A\subseteq E\\x\in A}} 1\\
      &= |\{A\in\mathcal{P}(E)\mid x\in A\}|\\
      &= |\{\{x\}\cup A'\mid A'\in\mathcal{P}(E\setminus\{x\})\}|\\
      &= |\mathcal{P}(E\setminus\{x\})|\\
      &= 2^{n-1}.
      \end{align*}$$
    </li>
    <li>
      <u>Lemme 2 :</u><br>
      $$\begin{align*}
      \sum_{A\subseteq E} 1 &= |\{A\subseteq E\}|\\
      &= |\mathcal{P}(E)|\\
      &= 2^n.
      \end{align*}$$
    </li>
    <ol>
      <li>
        On a
        $$\begin{align*}
        \sum_{A\subseteq E} |A| &= \sum_{A\subseteq E} \sum_{x\in E} \mathbb 1_A(x)\\
        &= \sum_{x\in E} \sum_{A\subseteq E} \mathbb 1_A(x)\\
        &= \sum_{x\in E} 2^{n-1} \quad \text{(cf. lemme)}\\
        &= n2^{n-1}.
        \end{align*}$$
      </li>
      <li>
        On a
        $$\begin{align*}
        \sum_{A,B\subseteq E} |A\cap B| &= \sum_{A,B\subseteq E} \sum_{x\in E} \mathbb 1_{A\cap B}(x)\\
        &= \sum_{x\in E} \sum_{A,B\subseteq E} \mathbb 1_{A\cap B}(x)\\
        &= \sum_{x\in E} \sum_{A,B\subseteq E} \mathbb 1_A(x) \cdot \mathbb 1_B(x)\\
        &= \sum_{x\in E} \sum_{A\subseteq E} \mathbb 1_A(x) \sum_{B\subseteq E} \mathbb 1_B(x)\\
        &= \sum_{x\in E} (2^{n-1})\cdot(2^{n-1}) \qquad \text{(cf. lemme)}\\
        &= n(2^{n-1})^2\\
        &= n4^{n-1}.
        \end{align*}$$
      </li>
      <li>
        On a
        $$\begin{align*}
        \sum_{A_1,\ldots,A_p\subseteq E} |A_1\cap\ldots\cap A_p| &= \sum_{A_1,\ldots,A_p\subseteq E} \sum_{x\in E} \mathbb 1_{A_1\cap\ldots\cap A_p}(x)\\
        &= \sum_{x\in E} \sum_{A_1,\ldots,A_p\subseteq E} \mathbb 1_{A_1\cap\ldots\cap A_p}(x)\\
        &= \sum_{x\in E} \sum_{A_1,\ldots,A_p\subseteq E} \prod_{i=1}^p \mathbb 1_{A_i}(x)\\
        &= \sum_{x\in E} \prod_{i=1}^p \sum_{A_i\subseteq E} \mathbb 1_{A_i}(x)\\
        &= \sum_{x\in E} \prod_{i=1}^p 2^{n-1}\\
        &= \sum_{x\in E} (2^{n-1})^p\\
        &= n(2^{n-1})^p.
        \end{align*}$$
      </li>
      <li>
        On a
        $$\begin{align*}
        \sum_{A,B\subseteq E} |A\cup B| &= \sum_{A,B\subseteq E} \sum_{x\in E} \mathbb 1_{A\cup B}(x)\\
        &= \sum_{x\in E} \sum_{A,B\subseteq E} \mathbb 1_{A\cup B}(x)\\
        &= \sum_{x\in E} \sum_{A,B\subseteq E} \mathbb 1_A(x) + \mathbb 1_B(x) - \mathbb 1_A(x) \cdot \mathbb 1_B(x)\\
        &= \sum_{x\in E} \left(\sum_{A\subseteq E} \mathbb 1_A(x)\sum_{B\subseteq E} 1 + \sum_{B\subseteq E} \mathbb 1_B(x)\sum_{A\subseteq E} 1 - \sum_{A\subseteq E} \mathbb 1_A(x)\sum_{B\subseteq E} \mathbb 1_B(x)\right)\\
        &= \sum_{x\in E} \left(2^{n-1}\cdot 2^n + 2^{n-1}\cdot 2^n - (2^{n-1})^2\right) \qquad \text{(cf. lemme)}\\
        &= n \left((2^n)^2 - (2^{n-1})^2\right)\\
        &= n (4^n - 4^{n-1})\\
        &= n\ 3\cdot4^{n-1} 
        \end{align*}$$
      </li>
      <li>
        On a
        $$\begin{align*}
        \sum_{A,B\subseteq E} |A\Delta B| &= \sum_{A,B\subseteq E} \sum_{x\in E} \mathbb 1_{A\Delta B}(x)\\
        &= \sum_{x\in E} \sum_{A,B\subseteq E} \mathbb 1_{A\Delta B}(x)\\
        &= \sum_{x\in E} \sum_{A,B\subseteq E} \mathbb 1_A(x) + \mathbb 1_B(x) - 2\mathbb 1_A(x) \cdot \mathbb 1_B(x)\\
        &= \sum_{x\in E} \left(2^{n-1}\cdot 2^n + 2^{n-1}\cdot 2^n - 2(2^{n-1})^2\right)\\
        &= n \left(4^n - 2\cdot 4^{n-1}\right)\\
        &= n\ 2\cdot4^{n-1}.
        \end{align*}$$
      </li>
    </ol>
    Remarque : $A\cup B = (A\cap B) \sqcup (A\Delta B)$ (union disjointe).<br>
    Donc, on a $\displaystyle\sum_{A,B\subseteq E} |A\cup B| = \sum_{A,B\subseteq E} |A\cap B| + \sum_{A,B\subseteq E} |A\Delta B|$.<br>
    C'est bien le cas car $\displaystyle n\ 3\cdot4^{n-1} = n\ 4^{n-1} + n\ 2\cdot4^{n-1}$.
</details>

---
