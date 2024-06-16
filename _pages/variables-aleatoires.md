---
layout: default
title: Variables aléatoires
permalink: variables-aleatoires
redirect_from:
  - variables-aléatoires
---

---

<h3 id="truquer-deux-dés-loi-uniforme">Truquer deux dés à 6 faces pour obtenir une loi uniforme</h3>

Est-il possible de truquer deux dés (indépendants) à 6 faces de manière à ce que la variable aléatoire $X$ qui associe à chaque lancer la somme des deux dés suive la uniforme sur $\\{2,\ldots,12\\}$ ?

<details>
  <summary><b>Indications</b></summary>
    Utiliser les fonctions génératrices.
</details>

<details>
  <summary><b>Solution</b></summary>
    Notons $X_1$ et $X_2$ les variables aléatoires associées aux deux dés.<br>
    Posons $X=X_1+X_2$ la variable aléatoire qui associe à chaque lancer la somme des deux dés.<br>
    Supposons par l'absurde que les dés sont truqués de telle sorte que $X$ suive la loi uniforme sur $\{2,\ldots,12\}$.<br><br>

    La fonction génératrice de $X$ est donnée par
    $$G_X(t)=\mathbb{E}[t^X]=\sum_{k=2}^{12}t^k\mathbb{P}(X=k)=\frac{1}{11}\sum_{k=2}^{12}t^k.$$

    Or, $X_1$ et $X_2$ sont indépendantes, donc on a la propriété de factorisation des fonctions génératrices :
    $$G_X(t)=G_{X_1+X_2}(t)=G_{X_1}(t)G_{X_2}(t)=\sum_{i=1}^6t^iP(X_1=i)\sum_{j=1}^6t^jP(X_2=j).$$

    Ainsi, en notant $a_i=P(X_1=i)$ et $b_j=P(X_2=j)$ pour $i,j\in\{1,\ldots,6\}$, et en simplifiant par $t^2$, on a :
    $$\frac{1}{11}(1+\ldots+t^{10})=(a_1+\ldots+a_6t^5)(b_1+\ldots+b_6t^5).$$

    Il est clair que $a_6$ et $b_6$ sont non nuls car $a_6b_6=1/11$.<br>
    Le membre de droite est alors un produit de deux polynômes de degré 5 (impair) donc admet au moins une racine réelle.<br>
    En revanche, $\displaystyle 1+\ldots+t^{10}=\frac{t^{11}-1}{t-1}$ n'a pas de racine réelle, ce qui est une contradiction.<br><br>

    Ainsi, il est impossible de truquer deux dés à 6 faces de manière à ce que la somme des deux dés suive la loi uniforme sur $\{2,\ldots,12\}$.
</details>

---
