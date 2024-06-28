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

<h3 id="centrale-pc-2023-III-A">Centrale PC 2023 Mathématiques 2 partie III.A</h3>

Cet exercice est adapté de la partie **III.A** de l'épreuve de <a href="https://www.concours-centrale-supelec.fr/CentraleSupelec/2023/PC/M045.pdf" target="_blank">mathématiques 2 de Centrale PC 2023</a>.

Les variables aléatoires considérées sont des variables aléatoires discrètes définies sur un même espace probabilisé $(\Omega,\mathcal{A},\mathbb{P})$.

Soit $p\in\,]0,1[$.

Soit $X$ une variable aléatoire à valeurs dans $\mathbb{N}^*$ suivant la loi géométrique de paramètre $p$, i.e.

$$\forall n\in\mathbb{N}^*,\ \mathbb{P}(X=n)=p(1-p)^{n-1}.$$

Soit $Y$ une variable aléatoire à valeurs dans $\mathbb{N}$ telle que, pour tout $n\in\mathbb{N}^*$, la loi conditionnelle de $Y$ sachant $(X=n)$ est la loi de Poisson de paramètre $n$, i.e.

$$\forall n\in\mathbb{N}^*,\ \forall k\in\mathbb{N},\ \mathbb{P}(Y=k|X=n)=\frac{n^k}{k!}e^{-n}.$$

<ol>
  <li>
    Déterminer la loi conjointe de $(X,Y)$.
    <details>
      <summary><b>Solution</b></summary>
        Soient $n\in\mathbb N^*$ et $k\in\mathbb N$. On a :
        $$\mathbb P(X=n,Y=k)=\mathbb P(Y=k|X=n)\mathbb P(X=n)=\frac{n^k}{k!}e^{-n}p(1-p)^{n-1}.$$
    </details>
  </li>
  <li>
    Calculer $\mathbb P(Y=0)$ et montrer que, pour tout $k\in\mathbb N^*$,
    $$\mathbb P(Y=k)=\frac{p}{(1-p)k!}\,f_k\left(\frac{1-p}{e}\right),$$
    où l'on note $\displaystyle f_k : x \mapsto \sum_{n=1}^{+\infty} n^kx^n$. On pourra admettre que $f_k$ est bien définie sur $]-1,1[$ (on peut également le démontrer, ce qui est fait dans la 1ère partie du même sujet Centrale à la question 4).
    <details>
      <summary><b>Solution</b></summary>
        D'après la formule des probabilités totales appliquée au système complet d'événements $(X=n)_{n\in\mathbb N^*}$, et d'après la question précédente, on a pour tout $k\in\mathbb N$ :
        $$\mathbb P(Y=k)=\sum_{n=1}^{+\infty} \mathbb P(X=n,Y=k)=\sum_{n=1}^{+\infty} \frac{n^k}{k!}e^{-n}p(1-p)^{n-1}.$$
        Pour $k=0$, on a, en sachant que $\displaystyle 0<\frac{1-p}{e}<1$ :
        $$\mathbb P(Y=0)=\sum_{n=1}^{+\infty} e^{-n}p(1-p)^{n-1}=\frac{p}{e}\sum_{n=1}^{+\infty} \left(\frac{1-p}{e}\right)^{n-1}=\frac{p}{e}\frac{1}{1-\frac{1-p}{e}}=\frac{p}{e+p-1}.$$
        Pour $k\in\mathbb N^*$, on a :
        $$\begin{align*}
        \mathbb P(Y=k)&=\sum_{n=1}^{+\infty} \frac{n^k}{k!}e^{-n}p(1-p)^{n-1}\\
        &=\frac{p}{(1-p)k!}\sum_{n=1}^{+\infty} n^k\left(\frac{1-p}{e}\right)^n\\
        &=\frac{p}{(1-p)k!}\,f_k\left(\frac{1-p}{e}\right).
        \end{align*}$$
    </details>
  </li>
  <li>
    Vérifier que l'on a bien $\displaystyle \sum_{k=0}^{+\infty} \mathbb P(Y=k) = 1$.
    <details>
      <summary><b>Solution</b></summary>
        On a :
        $$\begin{align*}
        \sum_{k=0}^{+\infty} \mathbb P(Y=k)&=\mathbb P(Y=0)+\sum_{k=1}^{+\infty} \mathbb P(Y=k)\\
        &=\frac{p}{e+p-1}+\sum_{k=1}^{+\infty} \frac{p}{(1-p)k!}\,f_k\left(\frac{1-p}{e}\right)\\
        &=\frac{p}{e+p-1}+\sum_{k=1}^{+\infty} \frac{p}{(1-p)k!}\sum_{n=1}^{+\infty} n^k\left(\frac{1-p}{e}\right)^n\\
        &=\frac{p}{e+p-1}+\frac{p}{(1-p)} \sum_{k=1}^{+\infty} \sum_{n=1}^{+\infty} \frac{n^k}{k!}\left(\frac{1-p}{e}\right)^n\\
        &=\frac{p}{e+p-1}+\frac{p}{(1-p)} \sum_{n=1}^{+\infty} \sum_{k=1}^{+\infty} \frac{n^k}{k!}\left(\frac{1-p}{e}\right)^n \qquad \text{(sommes à termes positifs)}\\
        &=\frac{p}{e+p-1}+\frac{p}{(1-p)} \sum_{n=1}^{+\infty} \left(\frac{1-p}{e}\right)^n \sum_{k=1}^{+\infty} \frac{n^k}{k!}\\
        &=\frac{p}{e+p-1}+\frac{p}{(1-p)} \sum_{n=1}^{+\infty} \left(\frac{1-p}{e}\right)^n (e^n-1)\\
        &=\frac{p}{e+p-1}+\frac{p}{(1-p)}\left(\sum_{n=1}^{+\infty} \left(1-p\right)^n - \sum_{n=1}^{+\infty} \left(\frac{1-p}{e}\right)^n\right)\\
        &=\frac{p}{e+p-1}+\frac{p}{(1-p)}\left(\frac{1-p}{1-(1-p)}-\frac{\frac{1-p}{e}}{1-\frac{1-p}{e}}\right)\\
        &=\frac{p}{e+p-1}+\frac{p}{(1-p)}\frac{1-p}{p}-\frac{p}{(1-p)}\frac{1-p}{e+p-1}\\
        &=\frac{p}{e+p-1}+1-\frac{p}{e+p-1}\\
        &=1.
        \end{align*}$$
    </details>
  </li>
  <li>
    Montrer que $Y$ admet une espérance et la calculer.<br>
    On pourra admettre (la question 2 du sujet Centrale) que pour tout $x\in\,]-1,1[$, on a
    $$\displaystyle f_1(x) = \sum_{n=0}^{+\infty} nx^n = \frac{x}{(1-x)^2}.$$
    <details>
      <summary><b>Solution</b></summary>
        $Y$ est à valeurs positives, donc $Y$ admet une espérance si et seulement si $\displaystyle \sum_{k=0}^{+\infty} k\,\mathbb P(Y=k)$ est finie.
        $$\begin{align*}
        \sum_{k=0}^{+\infty} k\,\mathbb P(Y=k)&=\sum_{k=1}^{+\infty} k\frac{p}{(1-p)k!}\,f_k\left(\frac{1-p}{e}\right)\\
        &=\frac{p}{1-p}\sum_{k=1}^{+\infty} \frac{1}{(k-1)!}\,\sum_{n=1}^{+\infty} n^k\left(\frac{1-p}{e}\right)^n\\
        &=\frac{p}{1-p}\sum_{n=1}^{+\infty} \left(\frac{1-p}{e}\right)^n\sum_{k=1}^{+\infty} \frac{n^k}{(k-1)!} \qquad \text{(sommes à termes positifs)}\\
        &=\frac{p}{1-p}\sum_{n=1}^{+\infty} \left(\frac{1-p}{e}\right)^n ne^n\\
        &=\frac{p}{1-p}\sum_{n=1}^{+\infty} n(1-p)^n\\
        &=\frac{p}{1-p} \frac{1-p}{(1-(1-p))^2} \qquad \text{(d'après la formule admise)}\\
        &=\frac{1}{p} < +\infty.
        \end{align*}$$
        Ainsi, $Y$ admet une espérance et $\displaystyle E(Y)=\frac{1}{p}$.
    </details>
  </li>
  <li>
    Montrer que $Y$ admet une variance et la calculer.<br>
    On pourra admettre (la question 12 du sujet Centrale) que pour tout $x\in\,]-1,1[$, on a
    $$\displaystyle f_2(x) = \sum_{n=0}^{+\infty} n^2x^n = \frac{x^2+x}{(1-x)^3}.$$
    <details>
      <summary><b>Solution</b></summary>
        D'après la formule de König-Huygens (sous réserve d'existence) : $V(Y)=E(Y^2)-(E(Y))^2$.<br>
        On en déduit que $Y$ admet une variance si et seulement si $\displaystyle \sum_{k=0}^{+\infty} k^2\,\mathbb P(Y=k)$ est finie.
        $$\begin{align*}
        \sum_{k=0}^{+\infty} k^2\,\mathbb P(Y=k)&=\sum_{k=1}^{+\infty} k^2\frac{p}{(1-p)k!}\,f_k\left(\frac{1-p}{e}\right)\\
        &=\frac{p}{1-p}\sum_{k=1}^{+\infty} \frac{k}{(k-1)!}\,\sum_{n=1}^{+\infty} n^k\left(\frac{1-p}{e}\right)^n\\
        &=\frac{p}{1-p}\sum_{n=1}^{+\infty} \left(\frac{1-p}{e}\right)^n\sum_{k=0}^{+\infty} \frac{k+1}{k!}\,n^{k+1} \qquad \text{(sommes à termes positifs)}\\
        &=\frac{p}{1-p}\sum_{n=1}^{+\infty} \left(\frac{1-p}{e}\right)^n \left(\sum_{k=1}^{+\infty} \frac{1}{(k-1)!}\,n^{k+1} + \sum_{k=0}^{+\infty} \frac{1}{k!}\,n^{k+1}\right)\\
        &=\frac{p}{1-p}\sum_{n=1}^{+\infty} \left(\frac{1-p}{e}\right)^n \left(n^2e^n + ne^n\right)\\
        &=\frac{p}{1-p}\left(f_2(1-p)+f_1(1-p)\right) \qquad \text{(où $1-p\in\,]-1,1[$)}\\
        &=\frac{p}{1-p}\left(\frac{(1-p)^2+(1-p)}{(1-(1-p))^3}+\frac{1-p}{(1-(1-p))^2}\right)\\
        &=\frac{1-p+1}{p^2}+\frac{1}{p}\\
        &=\frac{2}{p^2} < +\infty.
        \end{align*}$$
        Ainsi, $Y$ admet une variance et $\displaystyle V(Y)=E(Y^2)-(E(Y))^2=\frac{2}{p^2}-\frac{1}{p^2}=\frac{1}{p^2}$.
    </details>
  </li>
</ol>

---
