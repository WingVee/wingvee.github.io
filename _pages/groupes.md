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
