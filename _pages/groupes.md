---
layout: default
title: Groupes
permalink: groupes
redirect_from:
  - groupe
---

---

<h3 id="sous-groupes-de-r">
  <a href="#sous-groupes-de-r" class="header">
  Sous-groupes de $\mathbb{R}$</a>
</h3>

Soit $G$ un sous-groupe additif de $\mathbb{R}$. Montrer que 
- soit $G$ est monogène, i.e. de la forme $G = a\mathbb{Z}$ pour un certain $a \in \mathbb{R}_+$,
- soit $G$ est dense dans $\mathbb{R}$.

<details>
  <summary><b>Indications</b></summary>
  <details>
    <summary><u>Indication 1</u></summary>
      Lorsque $G\neq\{0\}$, considérer $a = \inf(G\cap\mathbb{R}^*_+)$.
  </details>
  <details>
    <summary><u>Indication 2</u></summary>
      Séparer les cas $a > 0$ et $a = 0$.
  </details>
</details>

<details>
  <summary><b>Solution</b></summary>
    Si $G = \{0\}$, le résultat est immédiat : $G = 0\mathbb{Z}$.<br><br>

    Supposons maintenant que $G\neq\{0\}$.<br>
    Il existe alors $x\in G\setminus\{0\}$. Puisque $G$ est un sous-groupe additif de $\mathbb{R}$, on a $-x\in G$.<br>
    Donc, $G\cap\mathbb{R}^*_+$ est une partie non vide et minorée de $\mathbb{R}$, donc admet une borne inférieure. Posons

    $$a = \inf(G\cap\mathbb{R}^*_+) \geq 0$$

    Premier cas : $a > 0$.
    <ol>
      Montrons que $G = a\mathbb{Z}$.<br><br>

      Montrons d'abord que $a\in G$. Supposons par l'absurde que $a\notin G$.<br>
      Par caractérisation de l'infimum, et puisque $a\notin G\cap\mathbb{R}^*_+$, il existe $x_1$ et $x_2$ dans $G\cap\mathbb{R}^*_+$ tels que $a < x_1 < x_2 < 2a$.<br>
      Puisque $x_1$ et $x_2$ sont dans $G$ qui est un groupe additif, on a $x_2 - x_1\in G$. De plus, $0 < x_2 - x_1$ donc $x_2 - x_1\in G\cap\mathbb{R}^*_+$.<br>
      Or, $x_2 - x_1 < a = \inf(G\cap\mathbb{R}^*_+)$, ce qui est absurde.<br>
      Donc, $a\in G$.<br><br>

      Montrons maintenant que $G = a\mathbb{Z}$ par double inclusion.<br>
      Puisque $a\in G$, on a $a\mathbb{Z} = \langle a\rangle \subset G$.<br>
      Reciproquement, soit $x\in G$. Il existe $n\in\mathbb{Z}$ tel que $na \leq x < (n+1)a$ (avec $n=\lfloor x/a\rfloor$).<br>
      Puisque $a\in G$, on a $na\in G$. Donc $x - na\in G$.<br>
      Or, $0 \leq x - na < a = \inf(G\cap\mathbb{R}^*_+)$, donc $x - na = 0$ et $x = na\in a\mathbb{Z}$.<br><br>

      Ainsi, $G = a\mathbb{Z}$.
    </ol>

    Deuxième cas : $a = 0$.
    <ol>
      Montrons que $G$ est dense dans $\mathbb{R}$.<br>
      Soit $x\in\mathbb{R}$ et $\varepsilon > 0$. On cherche $g\in G$ tel que $|x - g| < \varepsilon$.<br>
      Par caractérisation de l'infimum $a=\inf(G\cap\mathbb{R}^*_+)=0$, il existe $y\in G\cap\mathbb{R}^*_+$ tel que $0 < y < \varepsilon$.<br>
      Puisque $y\in G$, on a $y\mathbb{Z}\subset G$.<br>
      De plus, on a $y\mathbb{Z}\ \cap\ ]x-\varepsilon,x+\varepsilon[\ \neq \emptyset$ car il existe $n\in\mathbb{Z}$ tel que $ny\leq x < (n+1)y$ (avec $n=\lfloor x/y\rfloor$).<br>
      En notant $g = ny \in y\mathbb{Z} \subset G$, on a $|x - g| = x - ny < y < \varepsilon$.<br>
      Donc, $G$ est dense dans $\mathbb{R}$.
    </ol>

    Par conséquent, soit $G$ est monogène de la forme $G = a\mathbb{Z}$ pour un certain $a\in\mathbb{R}_+$, soit $G$ est dense dans $\mathbb{R}$.
</details>

---

<h3 id="groupe-infini-infinites-sous-groupes">
  <a href="#groupe-infini-infinites-sous-groupes" class="header">
  Un groupe infini admet une infinité de sous-groupes</a>
</h3>

Montrer que tout groupe infini $G$ admet une infinité de sous-groupes.

<details>
  <summary><b>Indications</b></summary>
    <details>
      <summary><u>Indication 1</u></summary>
        Supposer que $G$ admet un nombre fini de sous-groupes.<br>
        Montrer qu'il existe une partie finie $A$ de $G$ telle que $\displaystyle G = \bigcup_{a\in A} \langle a\rangle$.
    </details>
    <details>
      <summary><u>Indication 2</u></summary>
        Montrer que tous les sous-groupes engendrés $\langle a\rangle$ sont finis.
    </details>
</details>

<details>
  <summary><b>Solution</b></summary>
    Montrons la contraposée de l'énoncé : si $G$ admet un nombre fini de sous-groupes, alors $G$ est fini.<br>
    Supposons que $G$ admet un nombre fini de sous-groupes.<br><br>
    <li>
      <u>Étape 1 :</u> Montrons qu'il existe une partie finie $A$ de $G$ telle que $\displaystyle G = \bigcup_{a\in A} \langle a\rangle$.<br>
      <ol>
        Remarquons tout d'abord que $a \in \langle a\rangle$ pour tout $a\in G$. Donc
        $$G = \bigcup_{a\in G} \langle a\rangle.$$
        Or, $G$ admet un nombre fini de sous-groupes, donc l'ensemble des sous-groupes engendrés $\left\{\langle a\rangle\mid a\in G\right\}$ est fini.<br>
        Donc il existe une partie finie $A$ de $G$ telle que les deux ensembles suivants soient égaux :
        $$\left\{\langle a\rangle\mid a\in G\right\} = \left\{\langle a\rangle\mid a\in A\right\}.$$
        Ainsi,
        $$G = \displaystyle\bigcup_{a\in A} \langle a\rangle.$$
      </ol>
    </li>
    <li>
      <u>Étape 2 :</u> Montrons que tous les sous-groupes engendrés $\langle a\rangle$ sont finis.<br>
      <ol>
        Soit $a\in G$. Si $\langle a\rangle$ est infini, alors $\langle a\rangle$ est isomorphe à $\mathbb{Z}$.<br>
        Or $\mathbb{Z}$ admet une infinité de sous-groupes distincts (de la forme $n\mathbb{Z}$ pour $n\in\mathbb{N}$).<br>
        Donc par isomorphisme, $\langle a\rangle$ admet une infinité de sous-groupes distincts et donc $G$ admet une infinité de sous-groupes, ce qui contredit l'hypothèse de départ.<br>
        Donc tous les sous-groupes engendrés $\langle a\rangle$ sont finis.
      </ol>
    </li>
    En combinant les deux étapes, on obtient que $\displaystyle G = \bigcup_{a\in A} \langle a\rangle$ est une union finie de sous-groupes finis, donc $G$ est fini, ce qui conclut la preuve par contraposée.
</details>

---

<h3 id="parties-et-difference-symetrique">
  <a href="#parties-et-difference-symetrique" class="header">
  L'ensemble des parties muni de la différence symétrique est un groupe abélien</a>
</h3>

Soit $E$ un ensemble. On note $\mathcal{P}(E)$ l'ensemble des parties de $E$ et $\Delta$ la différence symétrique :

$$\forall A,B\in\mathcal{P}(E),\ A\Delta B = (A\cup B)\setminus (A\cap B) = (A\setminus B)\cup (B\setminus A) = (A\cap \overline{B})\cup (B\cap \overline{A}).$$

Montrer que $(\mathcal{P}(E),\Delta)$ est un groupe abélien.

<details>
  <summary><b>Remarque</b></summary>
    Géométriquement, la différence symétrique $A\Delta B$ correspond à l'ensemble des points qui sont dans $A$ ou dans $B$ mais pas dans les deux à la fois.
    <p align="center">
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/46/Venn0110.svg/1920px-Venn0110.svg.png" alt="Diagramme de Venn de la différence symétrique" width="300"/>
    </p>
    <div style="display: flex; justify-content: center;">
      <p style="display: flex; align-items: center;">
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/30/Venn0111.svg/1920px-Venn0111.svg.png" alt="A union B" width="60"/>
        $\setminus$
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/99/Venn0001.svg/1920px-Venn0001.svg.png" alt="A inter B" width="60"/>
        <span style="vertical-align: middle;">$=$</span>
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/46/Venn0110.svg/1920px-Venn0110.svg.png" alt="A delta B" width="60"/>
      </p>
    </div>
    $$(A\cup B)\setminus (A\cap B) = A\Delta B$$
    Que se passe-t-il si on rajoute un troisième ensemble ?
    <p align="center">
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/ae/Venn_0110_1001.svg/1280px-Venn_0110_1001.svg.png" alt="Diagramme de Ven de la différence symétrique de trois ensembles" width="300"/>
    </p>
    <div style="display: flex; justify-content: center;">
      <p style="display: flex; align-items: center;">
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/b/bd/Venn_0110_0110.svg/1280px-Venn_0110_0110.svg.png" alt="A delta B" width="50"/>
        $\Delta$
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/0e/Venn_0000_1111.svg/1280px-Venn_0000_1111.svg.png" alt="C" width="50"/>
        <span style="vertical-align: middle;">$=$</span>
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/ae/Venn_0110_1001.svg/80px-Venn_0110_1001.svg.png" alt="A delta B delta C" width="50"/>
      </p>
    </div>
    $$(A\Delta B)\Delta C = A\Delta B\Delta C$$
    Voir la solution 2 pour la preuve "géométrique".
</details>

<details>
  <summary><b>Indications</b></summary>
    Faire des dessins est toujours utile.
    <details>
      <summary><u>Indication solution 1</u></summary>
        Montrer que $\Delta$ est une loi de composition interne sur $\mathcal{P}(E)$ et est commutative.<br>
        Trouver l'élément neutre et l'inverse de chaque élément.<br>
        Pour l'associativité (qui est plus délicate), utiliser les différentes définitions de la différence symétrique, les lois de De Morgan et les opérations ensemblistes.
    </details>
    <details>
      <summary><u>Indication solution 2</u></summary>
        Utiliser les fonctions indicatrices et raisonner modulo 2 (cf. l'exercice sur les <a href="/raisonnement-et-vocabulaire-ensembliste#fonction-indicatrice-proprietes" target="_blank">propriétés des fonctions indicatrices</a>).<br>
        Il s'agit de voir géométriquement ce qui se passe, cf. remarque ci-dessus.
    </details>
</details>

<details>
  <summary><b>Solution 1</b></summary>
    Avec les opérations ensemblistes.<br><br>
    $\Delta$ est une loi de composition interne sur $\mathcal{P}(E)$ car $A\Delta B\in\mathcal{P}(E)$ pour tout $A,B\in\mathcal{P}(E).$<br>
    Élément neutre : $\emptyset$ est l'élément neutre de $\Delta$ car pour tout $A\in\mathcal{P}(E)$, on a
    $$A\Delta \emptyset = (A\cup \emptyset)\setminus (A\cap \emptyset) = A\setminus \emptyset = A.$$
    Inverse : pour tout $A\in\mathcal{P}(E)$, $A$ est son propre inverse car
    $$A\Delta A = (A\cup A)\setminus (A\cap A) = A\setminus A = \emptyset.$$
    Commutativité : pour tous $A,B\in\mathcal{P}(E)$, on a immédiatement
    $$A\Delta B = (A\cup B)\setminus (A\cap B) = (B\cup A)\setminus (B\cap A) = B\Delta A.$$
    $\Delta$ est associative : soient $A,B,C\in\mathcal{P}(E)$, on a
    $$\begin{align*}
    A\Delta (B\Delta C) &= \color{orange}{\Big(}\color{blue}{\big(}A\Delta B\color{blue}{\big)}\cap \overline{C}\color{orange}{\Big)}\cup \color{orange}{\Big(}C\cap \overline{\color{blue}{\big(}A\Delta B\color{blue}{\big)}}\color{orange}{\Big)}\\
    &= \color{orange}{\Big(}\color{blue}{\big(}\color{green}{(}A\cap \overline{B}\color{green}{)}\cup \color{green}{(}B\cap \overline{A}\color{green}{)}\color{blue}{\big)}\cap \overline{C}\color{orange}{\Big)}\cup \color{orange}{\Big(}C\cap \overline{\color{blue}{\big(}\color{green}{(}A\cap \overline{B}\color{green}{)}\cup \color{green}{(}B\cap \overline{A}\color{green}{)}\color{blue}{\big)}}\color{orange}{\Big)}\\
    &= \color{orange}{\Big(}\color{blue}{\big(}\color{green}{(}A\cap \overline{B}\color{green}{)}\cap \overline{C}\color{blue}{\big)}\cup \color{blue}{\big(}\color{green}{(}B\cap \overline{A}\color{green}{)}\cap \overline{C}\color{blue}{\big)}\color{orange}{\Big)}\cup \color{orange}{\Big(}C\cap \color{blue}{\big(}\color{green}{(}\overline{A}\cup B\color{green}{)}\cap \color{green}{(}\overline{B}\cup A\color{green}{)}\color{blue}{\big)}\color{orange}{\Big)}\\
    &= \color{orange}{\Big(}A\cap \overline{B}\cap \overline{C}\color{orange}{\Big)}\cup \color{orange}{\Big(}B\cap \overline{A}\cap \overline{C}\color{orange}{\Big)}\cup \color{orange}{\Big(}C\cap \color{blue}{\big(}\color{green}{(}\overline{A}\cap \overline{B}\color{green}{)}\cup \color{green}{(}B\cap A\color{green}{)}\color{blue}{\big)}\color{orange}{\Big)}\\
    &= \color{orange}{\Big(}A\cap \overline{B}\cap \overline{C}\color{orange}{\Big)}\cup \color{orange}{\Big(}\overline{A}\cap B\cap\overline{C}\color{orange}{\Big)}\cup \color{orange}{\Big(}\overline{A}\cap\overline{B}\cap C\color{orange}{\Big)}\cup \color{orange}{\Big(}A\cap B \cap C\color{orange}{\Big)}\\
    \end{align*}$$
    Une autre manière de le démontrer (si on est plus à l'aise avec les opérations ensemblistes) :
    $$\begin{align*}
    (A\Delta B)\Delta C &= \color{orange}{\Big(}\color{blue}{\big(}A\Delta B\color{blue}{\big)}\setminus C\color{orange}{\Big)}\cup \color{orange}{\Big(}C\setminus \color{blue}{\big(}A\Delta B\color{blue}{\big)}\color{orange}{\Big)}\\
    &= \color{orange}{\Big(}\color{blue}{\big(}\color{green}{(}A\setminus B\color{green}{)}\cup \color{green}{(}B\setminus A\color{green}{)}\color{blue}{\big)}\setminus C\color{orange}{\Big)}\cup \color{orange}{\Big(}C\setminus \color{blue}{\big(}\color{green}{(}A\cup B\color{green}{)}\setminus \color{green}{(}A\cap B\color{green}{)}\color{blue}{\big)}\color{orange}{\Big)}\\
    &= \color{orange}{\Big(}\color{blue}{\big(}A\setminus \color{green}{(}B\cup C\color{green}{)}\color{blue}{\big)}\cup \color{blue}{\big(}B\setminus \color{green}{(}A\cup C\color{green}{)}\color{blue}{\big)}\color{orange}{\Big)}\cup \color{orange}{\Big(}\color{blue}{\big(}C\setminus \color{green}{(}A\cup B\color{green}{)}\color{blue}{\big)}\cup \color{blue}{\big(}C\cap \color{green}{(}A\cap B\color{green}{)}\color{blue}{\big)}\color{orange}{\Big)}\\
    &= \color{orange}{\Big(}A\setminus \color{blue}{\big(}B\cup C\color{blue}{\big)}\color{orange}{\Big)}\cup \color{orange}{\Big(}B\setminus \color{blue}{\big(}A\cup C\color{blue}{\big)}\color{orange}{\Big)}\cup \color{orange}{\Big(}C\setminus \color{blue}{\big(}A\cup B\color{blue}{\big)}\color{orange}{\Big)}\cup \color{orange}{\Big(}A\cap B\cap C\color{orange}{\Big)}.
    \end{align*}$$
    Dans tous les cas, on obtient une expression symétrique en $A,B,C$ (cela veut dire que l'expression finale ne change pas si on permute $A,B,C$), donc
    $$(A\Delta B)\Delta C = A\Delta (B\Delta C) = A\Delta B\Delta C.$$
    Donc $(\mathcal{P}(E),\Delta)$ est un groupe abélien.
</details>

<details>
  <summary><b>Solution 2</b></summary>
    Avec les fonctions indicatrices.<br><br>
    Avant de passer à la preuve, visualisons ce qui se passe et interprétons la différence symétrique de deux ou plusieurs ensembles.<br>
    <details>
      <summary><u>Remarque copiée et collée (cf. plus haut)</u></summary>
        Géométriquement, la différence symétrique $A\Delta B$ correspond à l'ensemble des points qui sont dans $A$ ou dans $B$ mais pas dans les deux à la fois.
        <p align="center">
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/46/Venn0110.svg/1920px-Venn0110.svg.png" alt="Diagramme de Venn de la différence symétrique" width="300"/>
        </p>
        <div style="display: flex; justify-content: center;">
          <p style="display: flex; align-items: center;">
            <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/30/Venn0111.svg/1920px-Venn0111.svg.png" alt="A union B" width="60"/>
            $\setminus$
            <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/99/Venn0001.svg/1920px-Venn0001.svg.png" alt="A inter B" width="60"/>
            <span style="vertical-align: middle;">$=$</span>
            <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/46/Venn0110.svg/1920px-Venn0110.svg.png" alt="A delta B" width="60"/>
          </p>
        </div>
        $$(A\cup B)\setminus (A\cap B) = A\Delta B$$
        Que se passe-t-il si on rajoute un troisième ensemble ?
        <p align="center">
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/ae/Venn_0110_1001.svg/1280px-Venn_0110_1001.svg.png" alt="Diagramme de Ven de la différence symétrique de trois ensembles" width="300"/>
        </p>
        <div style="display: flex; justify-content: center;">
          <p style="display: flex; align-items: center;">
            <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/b/bd/Venn_0110_0110.svg/1280px-Venn_0110_0110.svg.png" alt="A delta B" width="50"/>
            $\Delta$
            <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/0e/Venn_0000_1111.svg/1280px-Venn_0000_1111.svg.png" alt="C" width="50"/>
            <span style="vertical-align: middle;">$=$</span>
            <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/ae/Venn_0110_1001.svg/80px-Venn_0110_1001.svg.png" alt="A delta B delta C" width="50"/>
          </p>
        </div>
        $$(A\Delta B)\Delta C = A\Delta B\Delta C$$
    </details>
    On remarque que $x\in A\Delta B\Delta C$ si et seulement si $x$ appartient à un nombre impair d'ensembles dans $A,B,C$.<br>
    En effet, à chaque ajout d'un ensemble, on inverse les "couleurs" des points de l'ensemble (les couleurs représentent l'appartenance à la différence symétrique des ensembles).<br>
    Ainsi, puisqu'il n'y a que deux "couleurs", i.e. $0$ et $1$ (faux et vrai), on peut définir la différence symétrique de plusieurs ensembles comme une addition modulo 2.<br>
    Soit $A\in\mathcal{P}(E)$. On définit la fonction indicatrice de $A$ par
    $$\begin{array}{rcl}
    \mathbb 1_A : E &\longrightarrow &\{0,1\}\\
    x &\longmapsto &\left\{\begin{matrix}1 {\text{ si }} x\in A,\\0 {\text{ si }} x\notin A.\end{matrix}\right.
    \end{array}$$
    On définit donc une application bijective (cf. l'exercice sur les <a href="/raisonnement-et-vocabulaire-ensembliste#fonction-indicatrice-proprietes" target="_blank">propriétés des fonctions indicatrices</a>) :
    $$\begin{array}{rcl}
    \mathbb 1 : \mathcal{P}(E) &\longrightarrow &\{0,1\}^E\\
    A &\longmapsto &\mathbb 1_A
    \end{array}.$$
    On a (cf. le même exercice sur les <a href="/raisonnement-et-vocabulaire-ensembliste#fonction-indicatrice-proprietes" target="_blank">propriétés des fonctions indicatrices</a>) :
    $$\mathbb 1_{A\Delta B} = (\mathbb 1_A - \mathbb 1_B)^2 = \|\mathbb 1_A - \mathbb 1_B\| = \max(\mathbb 1_A,\mathbb 1_B) - \min(\mathbb 1_A,\mathbb 1_B) = \mathbb 1_A + \mathbb 1_B - 2\mathbb 1_A \cdot \mathbb 1_B$$
    Si on raisonne modulo 2 (i.e. dans $\mathbb Z/2\mathbb Z$), on obtient
    $$\mathbb 1_{A\Delta B} = \mathbb 1_A + \mathbb 1_B.$$
    Tous les outils sont en place pour montrer que $(\mathcal{P}(E),\Delta)$ est un groupe abélien.<br><br>
    On se place dans $\mathbb Z/2\mathbb Z$.<br>
    $\Delta$ est une loi de composition interne sur $\mathcal{P}(E)$ car $A\Delta B\in\mathcal{P}(E)$ pour tout $A,B\in\mathcal{P}(E).$<br>
    Élément neutre : $\emptyset$ est l'élément neutre de $\Delta$ car pour tout $A\in\mathcal{P}(E)$, on a
    $$\mathbb 1_{A\Delta \emptyset} = \mathbb 1_A + \mathbb 1_{\emptyset} = \mathbb 1_A \iff A\Delta \emptyset = A.$$
    Inverse : pour tout $A\in\mathcal{P}(E)$, $A$ est son propre inverse car (modulo 2, dans $\mathbb Z/2\mathbb Z$)
    $$\mathbb 1_{A\Delta A} = \mathbb 1_A + \mathbb 1_A = 2\mathbb 1_A = 0 = \mathbb 1_{\emptyset} \iff A\Delta A = \emptyset.$$
    Commutativité : pour tous $A,B\in\mathcal{P}(E)$, on a immédiatement
    $$\mathbb 1_{A\Delta B} = \mathbb 1_A + \mathbb 1_B = \mathbb 1_B + \mathbb 1_A = \mathbb 1_{B\Delta A} \iff A\Delta B = B\Delta A.$$
    $\Delta$ est associative : pour tous $A,B,C\in\mathcal{P}(E)$, on a
    $$\begin{align*}
    \mathbb 1_{A\Delta (B\Delta C)} &= \mathbb 1_A + \mathbb 1_{B\Delta C}\\
    &= \mathbb 1_A + (\mathbb 1_B + \mathbb 1_C)\\
    &= \mathbb 1_A + \mathbb 1_B + \mathbb 1_C\\
    &= (\mathbb 1_A + \mathbb 1_B) + \mathbb 1_C\\
    &= \mathbb 1_{A\Delta B} + \mathbb 1_C\\
    &= \mathbb 1_{(A\Delta B)\Delta C}
    \end{align*}$$
    donc $(A\Delta B)\Delta C = A\Delta (B\Delta C) = A\Delta B\Delta C$.<br>
    Donc $(\mathcal{P}(E),\Delta)$ est un groupe abélien.<br><br>
    On vient de démontrer un résultat plus général :
    $$(\mathcal{P}(E),\Delta) \text{ est isomorphe à } ((\mathbb Z/2\mathbb Z)^E,+)$$
    qui est un groupe abélien, et $\mathbb 1: \mathcal{P}(E)\to (\mathbb Z/2\mathbb Z)^E$ est un isomorphisme de groupes.
</details>

---
