---
layout: default
title: Oraux MP/MPI
permalink: oraux-mp
redirect_from:
  - oraux-mpsi
  - oraux-mpi
---

---

<h3 id="beos-8418-2">
  <a href="#beos-8418-2" class="header">
  Mines-Ponts 2024 - Déterminant d'une somme de deux matrices</a>
</h3>

[Exercice traité ici.](determinants#determinant-somme-2-vandermonde)

**Mots-clés** : déterminant

**Source** : <a href="https://beos.prepas.org/sujet.php?id=8418" target="_blank">BEOS 8418</a>

---

<h3 id="beos-8272">
  <a href="#beos-8272" class="header">
  Mines-Ponts 2024 - Nombres ne contenant pas un chiffre donné</a>
</h3>

Soit $d$ un entier compris entre 0 et 9. On note $\mathbb{N}_{d}$ l'ensemble des entiers naturels non nuls ne contenant pas $d$ dans leur écriture décimale.

1. Montrer que $\mathbb{N}_{d}$ est en bijection avec $\mathbb{N}$.
2. Montrer que $\left(\frac{1}{n}\right)\_{n\in \mathbb{N}_{d}}$ est sommable.
3. Soit $n$ entier naturel non nul, on munit $\Omega_{n}=\\{1,\dots,n\\}$ de la probabilité uniforme. Déterminer la limite lorsque $n\to +\infty $ de la probabilité qu'un entier de $\Omega_{n}$ ne contienne pas le chiffre $d$. Interprétation ?

**Mots-clés** : dénombrabilité, sommabilité, probabilités, dénombrement

**Source** : <a href="https://beos.prepas.org/sujet.php?id=8272" target="_blank">BEOS 8272</a>

<details>
  <summary><b>Indications (fournies par l'examinateur durant l'épreuve)</b></summary>
    <ol>
      <li>Penser à la dénombrabilité.</li>
      <li>Trouver une partition bien choisie de $\mathbb{N}_{d}$.</li>
      <li>Raisonner en termes de cardinalités.</li>
    </ol>
</details>

<details>
  <summary><b>Solution</b></summary>
    <ol>
      <li>
        $\mathbb{N}_{d}$ est clairement une partie infinie de $\mathbb{N}$, donc $\mathbb{N}_{d}$ est dénombrable, i.e. en bijection avec $\mathbb{N}$.
      </li>
      <li>
        Soit $m\in\mathbb{N}^*$ et comptons (grossièrement) le nombre d'entiers de $\mathbb{N}_{d}$ à $m$ chiffres.<br>
        Pour chaque chiffre, on a au plus 9 choix (car on ne peut pas choisir $d$), donc il y a au plus $9^m$ entiers de $\mathbb{N}_{d}$ à $m$ chiffres.<br>
        <ol> Remarque : ce n'est pas exactement $9^m$ car un nombre ne peut pas commencer par un 0, mais on peut négliger ce détail puisque $9^m$ est une majoration suffisante pour conclure par la suite. Le nombre exact est $9^m$ pour $\mathbb{N}_{0}$ et $8\times 9^{m-1}$ pour les $\mathbb{N}_{d}$ avec $d\neq 0$.</ol>
        D'après le théorème de sommation par paquets pour des réels positifs, on a :
        $$\begin{align*}
        \sum_{n\in\mathbb{N}_{d}}\frac{1}{n}&=\sum_{m=1}^{+\infty}\left(\sum_{\substack{n\in\mathbb{N}_{d}\\10^{m-1}\leq n<10^m}}\frac{1}{n}\right)\leq\sum_{m=1}^{+\infty}\left(\sum_{\substack{n\in\mathbb{N}_{d}\\10^{m-1}\leq n<10^m}}\frac{1}{10^{m-1}}\right)\\
        &\leq\sum_{m=1}^{+\infty}\left(\frac{9^m}{10^{m-1}}\right)=10\sum_{m=1}^{+\infty}\left(\frac{9}{10}\right)^m=10\frac{9/10}{1-9/10}=90\\
        &<+\infty.
        \end{align*}$$
        Donc la famille $\displaystyle \left(\frac{1}{n}\right)_{n\in \mathbb{N}_{d}}$ est sommable.
      </li>
      <li>
        Soit $n\in\mathbb{N}^*$ et $m$ le nombre de chiffres de $n$ (remarque : $m=\lfloor\log_{10}(n)\rfloor+1$).<br>
        Notons $A_k$ l'ensemble des entiers de $\mathbb{N}_{d}$ à $k$ chiffres, i.e. $A_k=\mathbb{N}_{d}\cap\{10^{k-1},\dots,10^k-1\}$.<br>
        Ainsi, on a
        $$\displaystyle \Omega_n = \mathbb{N}_{d}\cap \{1,\dots,n\}\subseteq \mathbb{N}_{d}\cap\{1,\dots,10^{m}-1\}=\mathbb{N}_{d}\cap\bigsqcup_{k=1}^{m}\{10^{k-1},\dots,10^k-1\}=\bigsqcup_{k=1}^{m}A_k.$$
        Donc $\displaystyle \operatorname{Card}(\Omega_n)\leq\sum_{k=1}^{m}\operatorname{Card}(A_k)\leq\sum_{k=1}^{m}9^k=9\frac{9^m-1}{9-1}\leq 9^{m+1}$.<br>
        Ainsi, $\displaystyle 0\leq \mathbb{P}(\Omega_n) = \frac{\operatorname{Card}(\Omega_n)}{n}\leq\frac{9^{m+1}}{n}\leq\frac{9^{m+1}}{10^{m-1}}=90\left(\frac{9}{10}\right)^m\xrightarrow[n\to +\infty]{}0$ (car $m\to+\infty$ lorsque $n\to +\infty$).<br><br>
        L'interprétation est que la "probabilité" qu'un entier naturel non nul ne contienne pas le chiffre $d$ est nul.
      </li>
    </ol>
</details>

---

<h3 id="mon-oral-ens-ulsr">
  <a href="#mon-oral-ens-ulsr" class="header">
  Mon oral ENS Ulm/Lyon/Paris-Saclay/Rennes</a>
</h3>

Soit $\ f:\mathbb N\to\mathbb R$.<br>
On définit les applications $P$ et $D$ définies de $\mathcal F(\mathbb N,\mathbb R)$ dans $\mathcal F(\mathbb N,\mathbb R)$ par :

$$\begin{align*}
P(f):\mathbb N &\to\mathbb R \\
 x &\mapsto \frac12\left(f(x+1)+f(x)\right).
\end{align*}$$

et

$$\begin{align*}
D(f):\mathbb N &\to\mathbb R \\
 x &\mapsto f(x+1)-f(x).
\end{align*}$$

On note $f^2$ la fonction définie par $f^2(x)=(f(x))^2$ et $P^n = P\circ\dots\circ P$ ($n$ fois).

Montrer que $\forall x\in\mathbb N,\ \forall n\in\mathbb N^*,\ \forall f\in\mathcal F(\mathbb N,\mathbb R)$ :

$$P^n(f^2)(x)-(P^n(f)(x))^2\leq\frac{n}{4}P^{n-1}((D(f))^2)(x).$$

<details>
  <summary><b>Remarques</b></summary>
    Deux ans de prépa pour ça... Le cours ne sert à rien, faut juste savoir faire des calculs et ne pas se tromper.
</details>

<details>
  <summary><b>Indications</b></summary>
  <details>
    <summary><u>Indication solution 1</u></summary>
      Procéder par récurrence sur $n$ (oui oui, c'est vraiment l'indication qu'on m'a donnée lors de l'oral).
    </details>
    <details>
    <summary><u>Indication solution 2</u></summary>
      Voir $P$ et $D$ comme des opérateurs linéaires.<br>
      En notant $T(f)(x)=f(x+1)$, on a $D=T-\operatorname{Id}$ et $P=\dfrac12(T+\operatorname{Id})$.
    </details>
</details>

<details>
  <summary><b>Solutions</b></summary>
    <details>
      <summary><u>Solution 1 : par récurrence</u></summary>
        On va démontrer l'inégalité par récurrence sur $n$.
        <details>
          <summary>Initialisation</summary>
            Pour $n=1$, on a :
            $$\begin{align*}
            P(f^2)(x)-(P(f)(x))^2&=\frac12\left(f(x+1)^2+f(x)^2\right)-\left(\frac12\left(f(x+1)+f(x)\right)\right)^2\\
            &=\frac14\left(f(x+1)-f(x)\right)^2\\
            &=\frac14(D(f)(x))^2\\
            &=\frac14P^0((D(f))^2)(x).
            \end{align*}$$
        </details>
        <details>
          <summary>Hérédité</summary>
            Supposons que pour un certain $n\in\mathbb N^*$, on ait :
            $$P^n(f^2)(x)-(P^n(f)(x))^2\leq\frac{n}{4}P^{n-1}((D(f))^2)(x).$$
            On a alors :
            $$\begin{align*}
            P^{n+1}&(f^2)(x)-(P^{n+1}(f)(x))^2=P\left(P^n(f^2)\right)(x)-\left(P\left(P^n(f)\right)(x)\right)^2\\
            &=\frac12\left(P^n(f^2)(x+1)+P^n(f^2)(x)\right)-\left(\frac12\left(P^n(f)(x+1)+P^n(f)(x)\right)\right)^2\\
            &=\frac14\left(2P^n(f^2)(x+1)+2P^n(f^2)(x)-(P^n(f)(x+1))^2-2P^n(f)(x+1)P^n(f)(x)-(P^n(f)(x))^2\right)\\
            &=\frac14\Big(2P^n(f^2)(x+1)+2P^n(f^2)(x)-2(P^n(f)(x+1))^2-2(P^n(f)(x))^2\\
            &\quad +(P^n(f)(x+1))^2-2P^n(f)(x+1)P^n(f)(x)+(P^n(f)(x))^2\Big)\\
            &=\frac12\left(P^n(f^2)(x+1)-(P^n(f)(x+1))^2+P^n(f^2)(x)-(P^n(f)(x))^2\right)\\
            &\quad +\left(\frac12\left(P^n(f)(x+1)-P^n(f)(x)\right)\right)^2\\
            &\leq\frac12\frac{n}{4}\left(P^{n-1}((D(f))^2)(x+1)+P^{n-1}((D(f))^2)(x)\right)\\
            &\quad +\left(\frac12\left(P^n(f)(x+1)-P^n(f)(x)\right)\right)^2\qquad\qquad \text{(par hypothèse de récurrence)}\\
            &=\frac{n}{4}P^n((D(f))^2)(x)+\frac14\left(D(P^n(f))\right)^2(x)\\
            &\leq\frac{n}{4}P^n((D(f))^2)(x)+\frac14P^n((D(f))^2)(x) \qquad\qquad \text{($*$)}\\
            &=\frac{n+1}{4}P^n((D(f))^2)(x).
            \end{align*}$$
            D'où l'hérédité, sous réserve de justifier l'inégalité $(*)$ :
            $$\displaystyle\left(D(P^n(f))\right)^2(x)\leq P^n((D(f))^2)(x).$$
            On procède à nouveau par récurrence sur $n$.
            <details>
              <summary>Lemme</summary>
              $$\forall a,b,c\in\mathbb R,\ (a-c)^2\leq 2(a-b)^2+2(b-c)^2.$$
              Preuve :
              $$\begin{align*}
              (a-c)^2\leq 2(a-b)^2+2(b-c)^2 &\Longleftrightarrow a^2-2ac+c^2\leq 2a^2-4ab+2b^2+2b^2-4bc+2c^2\\
              &\Longleftrightarrow 0\leq a^2-4ab+4b^2-4bc+c^2+2ac\\
              &\Longleftrightarrow 0\leq (a-2b+c)^2.
              \end{align*}$$
            </details>
            <details>
              <summary>Initialisation</summary>
                Pour $n=1$, on a :
                $$\begin{align*}
                \left(D(P(f))\right)^2(x)&=\left(P(f)(x+1)-P(f)(x)\right)^2\\
                &=\left(\frac12\left(f(x+2)+f(x+1)\right)-\frac12\left(f(x+1)+f(x)\right)\right)^2\\
                &=\frac14\left(f(x+2)-f(x)\right)^2
                \end{align*}$$
                et
                $$\begin{align*}
                P((D(f))^2)(x)&=\frac12\left((D(f)(x+1))^2+(D(f)(x))^2\right)\\
                &=\frac12\left((f(x+2)-f(x+1))^2+(f(x+1)-f(x))^2\right).
                \end{align*}$$
                On a alors, en utilisant le lemme avec $a=f(x)+2, b=f(x+1)$ et $c=f(x+2)$ :
                $$\left(D(P(f))\right)^2(x)=\frac14\left(f(x+2)-f(x)\right)^2\leq\frac12\left((f(x+2)-f(x+1))^2+(f(x+1)-f(x))^2\right)=P((D(f))^2)(x).$$
            </details>
            <details>
              <summary>Hérédité</summary>
                Supposons que pour un certain $n\in\mathbb N^*$, on ait :
                $$\left(D(P^n(f))\right)^2(x)\leq P^n((D(f))^2)(x).$$
                On a alors :
                $$\begin{align*}
                &\left(D(P^{n+1}(f))\right)^2(x)=\left(P^{n+1}(f)(x+1)-P^{n+1}(f)(x)\right)^2\\
                &=\left(P(P^n(f))(x+1)-P(P^n(f))(x)\right)^2\\
                &=\left(\frac12\left(P^n(f)(x+2)+P^n(f)(x+1)\right)-\frac12\left(P^n(f)(x+1)+P^n(f)(x)\right)\right)^2\\
                &=\frac14\left(P^n(f)(x+2)-P^n(f)(x)\right)^2\\
                &\leq\frac12\left(P^n(f)(x+2)-P^n(f)(x+1)\right)^2+\frac12\left(P^n(f)(x+1)-P^n(f)(x)\right)^2 \qquad \text{(par le lemme)}\\
                &=\frac12\left(D(P^n(f))\right)^2(x+1)+\frac12\left(D(P^n(f))\right)^2(x)\\
                &\leq\frac12P^n((D(f))^2)(x+1)+\frac12P^n((D(f))^2)(x)\qquad\qquad \text{(par hypothèse de récurrence)}\\
                &=P^{n+1}((D(f))^2)(x).
                \end{align*}$$
                D'où le résultat.
            </details>
            Par récurrence, on a donc bien :
            $$\forall x\in\mathbb N,\ \forall n\in\mathbb N^*,\ \forall f\in\mathcal F(\mathbb N,\mathbb R),\ P^n(f^2)(x)-(P^n(f)(x))^2\leq\frac{n}{4}P^{n-1}((D(f))^2)(x).$$
        </details>
    </details>
    <details>
      <summary><u>Solution 2 : avec les opérateurs</u></summary>
        En remarquant que $P$ et $D$ sont des opérateurs linéaires dans l'espace vectoriel des suites réelles, cela nous incite à raisonner avec les opérateurs. Cela simplifie grandement les calculs et la preuve est plus élégante, notamment car elle n'utilise pas la récurrence.
        <details>
          <summary>Notations préliminaires</summary>
            On pose $E=\mathcal F(\mathbb N,\mathbb R)$ (on peut le voir comme l'espace vectoriel des suites réelles).<br>
            $(E,+,\times)$ est un anneau commutatif où $f\times g$ est défini par $(f\times g)(x)=f(x)g(x)$.<br>
            $(\mathcal F(E,E),+,\times)$ est un anneau commutatif où $\times$ est défini par $(A\times B)(f)=A(f)\times B(f)$.<br>
            $(\mathcal F(E,E),\circ)$ est un monoïde où $\circ$ est la composition d'applications.<br>
            $(\mathcal F(E,E),\leq)$ est un ensemble ordonné où $\leq$ est défini par
            $$A\leq B\Longleftrightarrow\forall f\in E,\ A(f)\leq B(f)\Longleftrightarrow \forall f\in E,\ \forall x\in\mathbb N,\ A(f)(x)\leq B(f)(x).$$
            On note $T,I,C\in\mathcal F(E,E)$ les opérateurs définis par :
            $$\begin{align*}
            T(f):\mathbb N &\to\mathbb R \\
            x &\mapsto f(x+1),\\
            I(f):\mathbb N &\to\mathbb R \\
            x &\mapsto f(x),\\
            C(f):\mathbb N &\to\mathbb R \\
            x &\mapsto (f(x))^2.
            \end{align*}$$
            Ici, $T$ est l'opération de translation, $I$ est l'opération d'identité et $C$ est l'opération de mise au carré.<br>
            On a $\displaystyle P=\frac12(I+T)$ et $D=T-I$ (ce sont des opérateurs linéaires) et $C=I\times I$.<br>
        </details>
        <details>
          <summary>Réécriture de l'inégalité</summary>
            On note, pour $F\in\mathcal F(E,E)$ et $n\in\mathbb N^*$, $F^n$ l'application $F\circ\cdots\circ F$ ($n$ fois).<br>
            L'inégalité à démontrer
            $$\forall x\in\mathbb N,\ \forall n\in\mathbb N^*,\ \forall f\in\mathcal F(\mathbb N,\mathbb R),\ P^n(f^2)(x)-(P^n(f)(x))^2\leq\frac{n}{4}P^{n-1}((D(f))^2)(x)$$
            s'écrit donc
            $$P^n\circ C - C\circ P^n\leq\frac{n}{4}P^{n-1}\circ C\circ D.$$
            On peut simplifier davantage avec le commutateur défini dans $\mathcal F(E,E)$ par $[A,B]=A\circ B-B\circ A$ :
            $$[P^n,C]\leq\frac{n}{4}P^{n-1}\circ C\circ D.$$
        </details>
        <details>
          <summary>Démonstration</summary>
            Pour rendre les calculs plus clairs, l'exposant $n$ désignera le $n$-ième itéré de la composition (vu dans $(\mathcal F(E,E),\circ)$) et l'exposant $2$ désignera la mise au carré (dans l'anneau commutatif $(\mathcal F(E,E),+,\times)$).<br>
            Ainsi, ici, $C=I\times I=I^2$.<br><br>
            On utilise les résultats suivants, vrais pour $A,B\in\mathcal F(E,E)$ :
            <ol>
              <li>
                $T\circ (A\times B)=(T\circ A)\times (T\circ B)$
              </li>
              <li>
                $P\circ D = D\circ P\quad$ ($P=\frac12(T+I)$ et $D=T-I$ commutent)
              </li>
              <li>
                $2(A^2+B^2)-(A+B)^2=(A-B)^2$
              </li>
              <li>
                $C\circ A = A^2 \geq 0$
              </li>
              <li>
                $A\geq 0 \Rightarrow P\circ A \geq 0$
              </li>
            </ol>
          <details>
            <summary>Étape 1 : $[P,C]$</summary>
              $$\begin{align*}
              [P,C]&=P\circ C-C\circ P\\
              &=\left(\frac12(T+I)\right)\circ I^2-C\circ\left(\frac12(T+I)\right)\\
              &=\frac12(T^2+I^2)-\left(\frac12(T+I)\right)^2 \quad \text{(par 1.)}\\
              &=\frac14(T-I)^2 \quad \text{(par 3.)}\\
              &=\frac14D^2\\
              &=\frac14C\circ D.
              \end{align*}$$
              On obtient une relation intéressante : $\displaystyle [P,C]=\dfrac14C\circ D$.<br>
              Cette relation montre aussi le cas $n=1$ de l'inégalité à démontrer.
          </details>
          <details>
            <summary>Étape 2 : $[P^n,C]$</summary>
              Soit $n\in\mathbb N^*$.
              $$\begin{align*}
              [P^{n},C]&=P^{n}\circ C-C\circ P^{n}\\
              &=\sum_{k=0}^{n-1}\left(P^{k+1}\circ C\circ P^{n-1-k}-P^{k}\circ C\circ P^{n-k}\right) \qquad \text{(téléscopage)}\\
              &=\sum_{k=0}^{n-1}P^k \circ \left(P\circ C - C\circ P\right) \circ P^{n-1-k}\\
              &=\sum_{k=0}^{n-1}P^k \circ [P,C] \circ P^{n-1-k}\\
              &=\frac14\sum_{k=0}^{n-1}P^k \circ C\circ D \circ P^{n-1-k} \qquad \text{(par l'étape 1 : $[P,C]=\dfrac14C\circ D$)}\\
              &\leq \frac14\sum_{k=0}^{n-1}P^{n-1}\circ C\circ D \qquad \text{($*$) (c'est ce qu'on aimerait avoir)}\\
              &=\frac{n}{4}P^{n-1}\circ C\circ D.
              \end{align*}$$
              Il reste à montrer ($*$) : pour tout $k\in\{0,\ldots,n-1\}$, on a $P^k\circ C\circ D \circ P^{n-1-k}\leq P^{n-1}\circ C\circ D$.<br>
              Il suffit de démontrer la chaîne d'inégalités suivante :
              $$C\circ D \circ P^{n-1}\leq P\circ C\circ D \circ P^{n-2-k} \leq \cdots \leq P^{n-1}\circ C\circ D,$$
              i.e. pour tout $k\in\{0,\ldots,n-2\}$ :
              $$\begin{align*}
              &P^k \circ C\circ D \circ P^{n-1-k}\leq P^{k+1}\circ C\circ D \circ P^{n-2-k}\\
              &\Longleftrightarrow P^k\circ (C\circ D \circ P)\circ P^{n-2-k}\leq P^k\circ (P\circ C\circ D)\circ P^{n-2-k}\\
              &\Longleftrightarrow P^k \circ [P,C\circ D] \circ P^{n-2-k}\geq 0.
              \end{align*}$$
          </details>
          <details>
            <summary>Étape 3 : $[P,C\circ D]$</summary>
            $$\begin{align*}
            [P, C \circ D] &= P \circ C \circ D - C \circ D \circ P\\
            &= P \circ D^2 - (D \circ P)^2 \qquad \text{(par associativité de $\circ$)}\\
            &= P \circ D^2 - (P \circ D)^2 \qquad \text{(par 2.)}\\
            &= \frac{1}{2} (T+I) \circ D^2 - \left(\frac{1}{2} (T+I) \circ D\right)^2\\
            &= \frac{1}{2} ((T \circ D)^2 + D^2) - \left(\frac{1}{2} (T \circ D + D)\right)^2 \qquad \text{(par 1.)}\\
            &= \frac{1}{4} (T \circ D - D)^2 \qquad \text{(par 3.)}\\
            &= \frac{1}{4} ((T-I) \circ D)^2\\
            &= \frac{1}{4} C \circ D \circ D.
            \end{align*}$$
            On a alors
            $$P^k \circ [P,C\circ D] \circ P^{n-2-k} = \frac{1}{4} P^k \circ C \circ D \circ D \circ P^{n-2-k}.$$
            D'après les résultats 4. et 5. on a $P^k\circ C\circ (D \circ D \circ P^{n-2-k})\geq 0$, donc $P^k \circ [P,C\circ D] \circ P^{n-2-k}\geq 0$.<br>
            D'où $(*)$ (étape 2) et donc l'inégalité voulue :
            $$[P^n,C]\leq\frac{n}{4}P^{n-1}\circ C\circ D.$$
          </details>
          <details>
            <summary>Étape 4 : Résumé et conclusion</summary>
            Avec les opérateurs précédemment définis, l'inégalité à démontrer est équivalente à :
            $$[P^n,C]\leq\frac{n}{4}P^{n-1}\circ C\circ D.$$
            On calcule alors :<br>
            <li>
              $[P,C]=\dfrac14C\circ D$.
            </li>
            <li>
            $\displaystyle[P^{n},C]=\sum_{k=0}^{n-1}P^k \circ [P,C] \circ P^{n-1-k}=\frac14\sum_{k=0}^{n-1}P^k \circ C\circ D \circ P^{n-1-k}$.
            </li>
            <li>
            Pour démontrer l'inégalité de l'énoncé, il suffit que $\displaystyle P^k \circ C\circ D \circ P^{n-1-k}\leq P^{n-1}\circ C\circ D$.<br>
            Pour cela, on montre l'inégalité suivante :
            $$P^k \circ C\circ D \circ P^{n-1-k}\leq P^{k+1}\circ C\circ D \circ P^{n-2-k} \Longleftrightarrow P^k \circ [P,C\circ D] \circ P^{n-2-k}\geq 0.$$
            </li>
            <li>
              $[P,C\circ D]=\dfrac14C \circ D \circ D$ et donc
              $$P^k \circ [P,C\circ D] \circ P^{n-2-k}=\frac{1}{4} P^k \circ C \circ D \circ D \circ P^{n-2-k}\geq 0.$$
            </li>
            Sans récurrence, on a démontré l'inégalité voulue.
          </details>
        </details>
    </details>
</details>

---
