---
layout: default
title: Oraux
permalink: oraux
redirect_from:
    - oral
---

---

<h3 id="beos-7214-1">
  <a href="#beos-7214-1" class="header">
  PC X-ESPCI 2023 - Vitesse de convergence d'une suite récurrente</a>
</h3>

On définit une suite réelle $(u_n)\_{n \in \mathbb{N}}$ par $u_0 > 0$ et la relation de récurrence $u_{n+1} = u_n - e^{-\frac 1{u_n}}$.

1. Montrer que cette suite est bien définie, puis qu'elle converge. Préciser sa limite.
2. Pour tout $\alpha > 0$, montrer que la suite $(n^{\alpha} u_n)_{n \in \mathbb{N}^*}$ tend vers $+\infty$.

**Mots-clés** : suite récurrente, calculs asymptotiques

**Source** : <a href="https://beos.prepas.org/sujet.php?id=7214" target="_blank">BEOS 7214</a>

<details>
  <summary><b>Remarques</b></summary>
    Ce résultat découle du résultat plus général traité dans <a href="calculs-asymptotiques#vitesse-de-convergence-suite-recurrente">cet exercice</a>.
</details>

<details>
  <summary><b>Indications</b></summary>
    <ol>
      <li>Écrire $u_{n+1} = f(u_n)$ et étudier $f$.</li>
      <li>Montrer qu'il s'agit d'obtenir $\displaystyle \frac{1}{u_n^{1/\alpha}} = o(n)$.<br>
      Montrer que $\displaystyle \frac{1}{u_{n+1}^{1/\alpha}} = \frac{1}{u_n^{1/\alpha}} + o(u_n^{\beta-1/\alpha})$ pour tout $\beta > 0$.</li>
    </ol>
</details>

<details>
  <summary><b>Solution</b></summary>
    <ol>
      <li>
        <u>Bonne définition de la suite :</u><br>
        Posons $f(x) = x - e^{-\frac 1{x}}$ définie sur $\mathbb{R}_+^*$.<br>
        Soit $x > 0$. On a
        $$\begin{align*}
        f(x) > 0 &\iff x > e^{-\frac 1{x}}\\
        &\iff \ln(x) > -\frac 1{x}\\
        &\iff -\ln(x) < \frac 1{x}\\
        &\iff \ln\left(\frac 1x\right) < \frac 1x.
        \end{align*}$$
        Or, l'inégalité $\ln(y) \leq y-1 < y$ est vérifiée pour tout $y > 0$, donc $\ln\left(\frac 1x\right) < \frac 1x$ pour tout $x > 0$.<br>
        Ainsi, $u_{n+1} = f(u_n)$ est bien définie pour tout $n\in\mathbb{N}$ car $u_0 > 0$ et $\ f(x) > 0$ pour tout $x > 0$.<br><br>
        <u>Convergence de la suite et limite :</u><br>
        On a $u_{n+1} - u_n = -e^{-\frac 1{u_n}} < 0$, donc $(u_n)$ est (strictement) décroissante.<br>
        Ainsi, la suite $(u_n)$ est décroissante et minorée par $0$, donc elle converge vers une limite $\ell\geq 0$.<br>
        On remarque que $\ f$ est continue sur $\mathbb{R}_+^*$ et est prolongeable par continuité en $0$ en posant $f(0) = 0$.<br>
        Par continuité de $\ f$ (sur $\mathbb R$), on a $\ell = f(\ell)$. Or, $f(x) < x$ pour tout $x > 0$, donc $\ell = 0$.<br>
        Donc $u_n \underset{n\to+\infty}{\longrightarrow} 0$.
      </li>
      <li>
        Soit $\alpha > 0$. On a l'équivalence suivante (avec $u_n > 0$) :
        $$\begin{align*}
        n^{\alpha}u_n \xrightarrow[n\to +\infty]{} +\infty &\iff \frac{1}{n^{\alpha}u_n} \xrightarrow[n\to +\infty]{} 0\\
        &\iff \frac{1}{n u_n^{1/\alpha}} \xrightarrow[n\to +\infty]{} 0\\
        &\iff \frac{1}{n u_n^{1/\alpha}} = o(1)\\
        &\iff \frac{1}{u_n^{1/\alpha}} = o(n).
        \end{align*}$$
        Nous allons démontrer cette dernière affirmation. Faisons un développement asymptotique :
        $$\begin{align*}
        \frac{1}{u_{n+1}^{1/\alpha}} &= \frac{1}{\left(u_n - e^{-\frac 1{u_n}}\right)^{1/\alpha}}\\
        &= \frac{1}{u_n^{1/\alpha}}\left(1 - \frac{1}{u_n}e^{-\frac 1{u_n}}\right)^{-1/\alpha}\\
        &= \frac{1}{u_n^{1/\alpha}}\left(1 + o(u_n^{\beta})\right)^{-1/\alpha}  \qquad \text{pour tout } \beta > 0\ (\text{croissances comparées})\\
        &=\frac{1}{u_n^{1/\alpha}} + o(u_n^{\beta-1/\alpha}).
        \end{align*}$$
        En choisissant $\beta = 1/\alpha$, on a $\displaystyle \frac{1}{u_{n+1}^{1/\alpha}} - \frac{1}{u_n^{1/\alpha}} = o(1)$, donc par télescopage :
        $$\frac{1}{u_n^{1/\alpha}} = \frac{1}{u_0^{1/\alpha}} + o(n) = o(n).$$
        Ce qui conclut la démonstration.
      </li>
    </ol>
</details>

<details>
  <summary><b>Pour aller plus loin</b></summary>
    <ul>
      <li>
        <a href="calculs-asymptotiques#vitesse-de-convergence-suite-recurrente">Vitesse de convergence d'une suite récurrente</a>
      </li>
    </ul>
</details>

---

<h3 id="mon-oral-ens-ulsr">
  <a href="#mon-oral-ens-ulsr" class="header">
  Mon oral ENS Ulm/Lyon/Paris-Saclay/Rennes</a>
</h3>

Soit $f:\mathbb N\to\mathbb R$.<br>
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
