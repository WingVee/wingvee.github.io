---
layout: default
title: Raisonnement et vocabulaire ensembliste
permalink: raisonnement-et-vocabulaire-ensembliste
---

---

<h3 id="fonction-indicatrice-proprietes">
  <a href="#fonction-indicatrice-proprietes" class="header">
  Fonction indicatrice (propriétés)</a>
</h3>

Soit $E$ un ensemble. La fonction indicatrice (appelée aussi fonction caractéristique) d'un sous-ensemble $A\subseteq E$ est la fonction notée $\mathbb 1_A$ (ou $\chi_A$) définie par :

$$\begin{array}{rcl}
\mathbb 1_A : E &\longrightarrow &\{0,1\}\\
x &\longmapsto &\left\{\begin{matrix}1 {\text{ si }} x\in A,\\0 {\text{ si }} x\notin A.\end{matrix}\right.
\end{array}$$

On a $\mathbb 1_A \in \mathcal{F}(E,\\{0,1\\}) = \\{0,1\\}^E$.

Montrer les propriétés suivantes de la fonction indicatrice, avec $A,B\subseteq E$ :

1. Intersection : $\mathbb 1_{A\cap B} = \min(\mathbb 1_A,\mathbb 1_B) = \mathbb 1_A \cdot \mathbb 1_B$.
2. Union : $\mathbb 1_{A\cup B} = \max(\mathbb 1_A,\mathbb 1_B) = \mathbb 1_A + \mathbb 1_B - \mathbb 1_A \cdot \mathbb 1_B$.<br> Union disjointe : si $A\cap B = \emptyset$, alors $\mathbb 1\_\{A\cup B\} = \mathbb 1\_A + \mathbb 1\_B$.
3. Complémentaire : $\mathbb 1_{\overline{A}} = 1 - \mathbb 1_A$.
4. Cardinal : $\operatorname{Card}(A)= \sum_{x\in E} \mathbb 1_A(x) \in \mathbb{N}\cup\\{+\infty\\}$.
5. Différence symétrique : $\mathbb 1_{A\Delta B} = (\mathbb 1_A - \mathbb 1_B)^2 = \|\mathbb 1_A - \mathbb 1_B\| = \max(\mathbb 1_A,\mathbb 1_B) - \min(\mathbb 1_A,\mathbb 1_B) = \mathbb 1_A + \mathbb 1_B - 2\mathbb 1_A \cdot \mathbb 1_B$.
6. Inclusion : $A\subseteq B \iff \mathbb 1_A \leq \mathbb 1_B$ (c'est-à-dire $\forall x\in E, \mathbb 1_A(x) \leq \mathbb 1_B(x)$).
7. Bijection : L'application suivante est bijective :

$$\begin{array}{rcl}
\Phi : \mathcal{P}(E) &\longrightarrow &\{0,1\}^E\\
A &\longmapsto &\mathbb 1_A
\end{array}.$$

<ol>
	Autrement dit, à tout sous-ensemble $A\subseteq E$ est associée une fonction (indicatrice) de $E$ à valeurs dans $\{0,1\}$ et réciproquement.<br>
  De plus, pour tout $\ f\in\{0,1\}^E$, on a $\Phi^{-1}(f) = \{x\in E\mid f(x) = 1\} = f^{-1}(\{1\})$
</ol>

<details>
	<summary><b>Indications</b></summary>
		Montrer qu'il y a égalité entre les fonctions. Faire des disjonctions de cas.<br>
		Une astuce est de construire une table de vérité.
</details>

<details>
	<summary><b>Solution</b></summary>
		On démontre les propriétés en montrant qu'il y a égalité entre les fonctions. Soit $x\in E$.
		<ol>
			<li>
				<u>Intersection :</u><br>
				Si $x\in A\cap B$, alors $x\in A$ et $x\in B$, donc $\mathbb 1_{A\cap B}(x) = \mathbb 1_A(x) = \mathbb 1_B(x) = 1$.<br>
				Donc $\mathbb 1_{A\cap B}(x) = \min(\mathbb 1_A(x),\mathbb 1_B(x)) = \mathbb 1_A(x) \cdot \mathbb 1_B(x) = 1$.<br>
				Sinon $x\notin A\cap B$, i.e. $x\notin A$ ou $x\notin B$, donc $\mathbb 1_{A}(x) = 0$ ou $\mathbb 1_{B}(x) = 0$.<br>
				Donc a bien $\mathbb 1_{A\cap B}(x) = \min(\mathbb 1_A(x),\mathbb 1_B(x)) = \mathbb 1_A(x) \cdot \mathbb 1_B(x) = 0$.<br><br>
				Il est également possible d'établir une table de vérité avec les valeurs de $\mathbb 1_A(x)$ et $\mathbb 1_B(x)$ (i.e. en fonction des valeurs de vérité des propositions $x\in A$ et $x\in B$) :
				$$\begin{array}{|c|c|c|c|c|c|}
				\hline
				\mathbb 1_A(x) & \mathbb 1_B(x) & \mathbb 1_{A\cap B}(x) & \min(\mathbb 1_A(x),\mathbb 1_B(x)) & \mathbb 1_A(x) \cdot \mathbb 1_B(x)\\
				\hline
				0 & 0 & 0 & 0 & 0\cdot 0 = 0\\
				0 & 1 & 0 & 0 & 0\cdot 1 = 0\\
				1 & 0 & 0 & 0 & 1\cdot 0 = 0\\
				1 & 1 & 1 & 1 & 1\cdot 1 = 1\\
				\hline
				\end{array}$$
				On retrouve bien l'égalité : $\mathbb 1_{A\cap B} = \min(\mathbb 1_A,\mathbb 1_B) = \mathbb 1_A \cdot \mathbb 1_B$.
			</li>
			<li>
				<u>Union :</u><br>
				$$\begin{array}{|c|c|c|c|c|c|}
				\hline
				\mathbb 1_A(x) & \mathbb 1_B(x) & \mathbb 1_{A\cup B}(x) & \max(\mathbb 1_A(x),\mathbb 1_B(x)) & \mathbb 1_A(x) + \mathbb 1_B(x) - \mathbb 1_A(x) \cdot \mathbb 1_B(x)\\
				\hline
				0 & 0 & 0 & 0 & 0+0-0\cdot 0 = 0\\
				0 & 1 & 1 & 1 & 0+1-0\cdot 1 = 1\\
				1 & 0 & 1 & 1 & 1+0-1\cdot 0 = 1\\
				1 & 1 & 1 & 1 & 1+1-1\cdot 1 = 1\\
				\hline
				\end{array}$$
				On retrouve bien l'égalité : $\mathbb 1_{A\cup B} = \max(\mathbb 1_A,\mathbb 1_B) = \mathbb 1_A + \mathbb 1_B - \mathbb 1_A \cdot \mathbb 1_B$.
				<br>
				<u>Union disjointe :</u><br>
				Si $A\cap B = \emptyset$, alors $\mathbb 1_A\cdot\mathbb 1_B = \mathbb 1_{A\cap B} = 1_{\emptyset} = 0$ (fonction nulle).<br>
				Donc $\mathbb 1_{A\cup B} = \mathbb 1_A + \mathbb 1_B - \mathbb 1_A \cdot \mathbb 1_B = \mathbb 1_A + \mathbb 1_B$.
			</li>
			<li>
				<u>Complémentaire :</u><br>
				$$\begin{array}{|c|c|c|}
				\hline
				\mathbb 1_A(x) & \mathbb 1_{\overline{A}}(x) & 1 - \mathbb 1_A(x)\\
				\hline
				0 & 1 & 1\\
				1 & 0 & 0\\
				\hline
				\end{array}$$
				Une autre preuve consiste à remarquer que $A$ et $\overline{A}$ sont disjoints et forment une partition de $E$.<br>
				Donc $1 = \mathbb 1_E = \mathbb 1_{A\cup\overline{A}} = \mathbb 1_A + \mathbb 1_{\overline{A}}$, d'où $\mathbb 1_{\overline{A}} = 1 - \mathbb 1_A$.
			</li>
			<li>
				<u>Cardinal :</u><br>
				Dans $\mathbb{N}\cup\{+\infty\}$, on a :
				$$\operatorname{Card}(A) = \sum_{x\in A} 1 = \sum_{x\in A} \mathbb 1_A(x) = \left( \sum_{x\in A} \mathbb 1_A(x)\right) + 0 = \sum_{x\in A} \mathbb 1_A(x) + \sum_{x\in E\setminus A} \mathbb 1_A(x) = \sum_{x\in E} \mathbb 1_A(x).$$
			</li>
			<li>
				<u>Différence symétrique :</u><br>
				$$\begin{array}{|c|c|c|c|}
				\hline
				\mathbb 1_A(x) & \mathbb 1_B(x) & \mathbb 1_{A\Delta B}(x) & |\mathbb 1_A(x) - \mathbb 1_B(x)|\\
				\hline
				0 & 0 & 0 & 0\\
				0 & 1 & 1 & 1\\
				1 & 0 & 1 & 1\\
				1 & 1 & 0 & 0\\
				\hline
				\end{array}$$
				Donc $\mathbb 1_{A\Delta B} = |\mathbb 1_A - \mathbb 1_B|$.<br>
				Tout est à valeurs dans $\{0,1\}$ (qui est leur propre carré), donc $(\mathbb 1_A - \mathbb 1_B)^2 = |\mathbb 1_A - \mathbb 1_B|$.<br>
				En exploitant le fait que $|a-b| = \max(a,b) - \min(a,b)$, et en utilisant les propriétés de l'union et de l'intersection démontrées précédemment, on a :
				$$\mathbb 1_{A\Delta B} = |\mathbb 1_A - \mathbb 1_B| = \max(\mathbb 1_A,\mathbb 1_B) - \min(\mathbb 1_A,\mathbb 1_B) = \mathbb 1_{A\cup B} - \mathbb 1_{A\cap B} = \mathbb 1_A + \mathbb 1_B - 2\mathbb 1_A \cdot \mathbb 1_B.$$
			</li>
			<li>
				<u>Inclusion :</u><br>
				Si $x\in A\subseteq B$, on a bien $1 = \mathbb 1_A(x) \leq \mathbb 1_B(x) = 1$.<br>
				Sinon, $x\notin A$, donc $\mathbb 1_A(x) = 0 \leq \mathbb 1_B(x)$ car $\mathbb 1_B(x) \in \{0,1\}$.<br>
				Dans tous les cas, on a $\mathbb 1_A(x) \leq \mathbb 1_B(x)$ lorsque $A\subseteq B$.
			</li>
			<li>
				<u>Bijection :</u><br>
				<ul>
					<li>L'application $\Phi$ est bien définie car $\mathbb 1_A\in\{0,1\}^E$ pour tout $A\in\mathcal{P}(E)$.</li>
					<li>L'application $\Phi$ est injective.<br>
						En effet, soient $A,B\in\mathcal{P}(E)$ tels que $\Phi(A) = \Phi(B)$.<br>
						Alors $\mathbb 1_A = \mathbb 1_B$, i.e. $\forall x\in E, \mathbb 1_A(x) = \mathbb 1_B(x)$.<br>
						Soit $x\in A$. Alors $\mathbb 1_A(x) = 1 = \mathbb 1_B(x)$, donc $x\in B$. Ainsi $A\subseteq B$.<br>
						De même manière, on a $B\subseteq A$. Donc $A = B$, d'où l'injectivité de $\Phi$.</li>
					<li>L'application $\Phi$ est surjective.<br>
						Soit $\ f\in\{0,1\}^E$. On cherche $A\in\mathcal{P}(E)$ tel que $\Phi(A) = f$, i.e. $\mathbb 1_A = f$.<br>
						Posons $A = f^{-1}(\{1\}) = \{x\in E\mid f(x) = 1\}$ (i.e. l'ensemble des antécédents de $1$ par $f$).<br>
						On a bien $A\in\mathcal{P}(E)$. Soit $x\in E$, on a :
						$$\mathbb 1_A(x) = 1 \iff x\in A = f^{-1}(\{1\}) \iff f(x) = 1$$
						$$\text{ et } \mathbb 1_A(x) = 0 \iff x\notin A = f^{-1}
						(\{1\}) \iff f(x) = 0 \text{ (car } f \text{ est à valeurs dans } \{0,1\}).$$
						Donc $\Phi(A) = \mathbb 1_A = f$, d'où la surjectivité de $\Phi$.</li>
				</ul>
				Ainsi, $\Phi$ est une bijection entre $\mathcal{P}(E)$ et $\{0,1\}^E$ et sa bijection réciproque est $\Phi^{-1}(f) = f^{-1}(\{1\})$.
			</li>
		</ol>
</details>

<details>
  <summary><b>Pour aller plus loin</b></summary>
    <ul>
      <li>
				<a href="denombrement#formule-du-crible">Formule du crible</a>
			</li>
			<li>
				<a href="groupes#parties-et-difference-symetrique">L'ensemble des parties muni de la différence symétrique est un groupe abélien</a>
      </li>
    </ul>
</details>

---
