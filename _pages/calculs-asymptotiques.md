---
layout: default
title: Calculs asymptotiques
permalink: calculs-asymptotiques
---

---

<h3 id="equivalent-partie-fractionnaire-n-e">
  <a href="#equivalent-partie-fractionnaire-n-e" class="header">
  Équivalent de la partie fractionnaire de $n!e$</a>
</h3>

1. Pour $x\in\mathbb{R}$, on note $\\{x\\}$ la partie fractionnaire de $x$, c'est-à-dire $\\{x\\} = x - \lfloor x\rfloor$.<br>
Trouver un équivalent de $\\{n!e\\}$ lorsque $n\to+\infty$.
2. Application : calculer $\displaystyle\lim_{n\to+\infty} n\sin(2\pi n!e)$.

<details>
  <summary><b>Remarques</b></summary>
    La question 1 de cet exercice semblerait avoir été donné à l'oral PC X-ESPCI 2022 (voir <a href="https://beos.prepas.org/sujet.php?id=6933" target="_blank">BEOS 6933</a>).
</details>

<details>
  <summary><b>Indications</b></summary>
    Montrer que
    $$\{n!e\} = \left\{\sum_{k=1}^{+\infty}\frac{1}{(n+1)(n+2)\cdots(n+k)}\right\}.$$
    Puis, encadrer la somme par deux termes équivalents.
</details>

<details>
  <summary><b>Solution</b></summary>
    <ol>
      <li>
        En utilisant le fait que $\{x+k\} = \{x\}$ pour tout $x\in\mathbb{R}$ et $k\in\mathbb{Z}$, on a
        $$\begin{align*}
        \{n!e\} &= \left\{n!\sum_{k=0}^{+\infty}\frac{1}{k!}\right\}\\
        &= \left\{\frac{n!}{0!} + \frac{n!}{1!} + \frac{n!}{2!} + \cdots + \frac{n!}{n!} + \frac{n!}{(n+1)!} + \frac{n!}{(n+2)!} + \cdots\right\}\\
        &= \left\{\frac{n!}{(n+1)!} + \frac{n!}{(n+2)!} + \cdots\right\}\\
        &= \left\{\frac{1}{n+1} + \frac{1}{(n+1)(n+2)} + \cdots\right\}\\
        &= \left\{\sum_{k=1}^{+\infty}\frac{1}{(n+1)(n+2)\cdots(n+k)}\right\}.
        \end{align*}$$
        On remarque que
        $$\frac{1}{n+1} \leq \sum_{k=1}^{+\infty}\frac{1}{(n+1)(n+2)\cdots(n+k)} \leq \sum_{k=1}^{+\infty}\frac{1}{(n+1)^{k}} = \frac{1}{n}.$$
        Donc, $\displaystyle\frac{1}{n+1} \leq \{n!e\} \leq \frac{1}{n}$, d'où
        $$\{n!e\} \sim \frac1n.$$

      </li>
      <li>
        En remarquant que pour tout $x\in\mathbb{R}$, on a $\sin(2\pi x) = \sin(2\pi(\{x\} + \lfloor x\rfloor)) = \sin(2\pi\{x\})$, et que $\sin(x)\sim x$ lorsque $x\to 0$, on a
        $$n\sin(2\pi n!e) = n\sin(2\pi\{n!e\}) \sim n\cdot 2\pi\{n!e\} \sim n\cdot 2\pi\frac1n = 2\pi.$$
        Donc $\displaystyle\lim_{n\to+\infty} n\sin(2\pi n!e) = 2\pi$.
      </li>
    </ol>
</details>

---

<h3 id="vitesse-de-convergence-suite-recurrente">
	<a href="#vitesse-de-convergence-suite-recurrente" class="header">
	Vitesse de convergence d'une suite récurrente</a>
</h3>

Soit $(u_n)_{n\in\mathbb{N}}$ une suite de réels strictement positifs définie par $u_0 > 0$ et pour tout $n\in\mathbb{N}$,

$$u_{n+1} = f(u_n)$$

où $\ f:\mathbb{R}\_+\to\mathbb{R}_+$ est une fonction vérifiant les conditions suivantes :

1. $f$ est continue,
2. $f(0) = 0$,
3. $0 < f(x) < x$ pour tout $x > 0$,
4. $f(x) = x - ax^{k+1} + \mathcal{O}(x^{k+2})$ au voisinage de $0$, avec $a > 0$ et $k\in\mathbb{N}^*$.

L'objectif de l'exercice est de montrer que

$$\sqrt[k]n u_n \underset{n\to+\infty}{\longrightarrow} \frac{1}{\sqrt[k]{ka}}.$$

Autrement dit, la vitesse de convergence de la suite $(u_n)$ est de l'ordre de $\displaystyle\frac{1}{\sqrt[k]{nka}}$. <br>
Remarque : Le résultat reste vrai pour tout réel $k > 0$.

Bien qu'il est possible de le démontrer sans questions subsidiaires pour un public aguerri, voici des questions pour guider la réflexion :

1. Montrer que $u_n \underset{n\to+\infty}{\longrightarrow} 0$.
2. Soit $\alpha\in\mathbb{R}$. Établir que $u_{n+1}^\alpha = u_n^\alpha - \alpha au_n^{\alpha + k} + \mathcal{O}(u_n^{\alpha + k + 1})$.
3. Conclure.
4. Application : $0 < u_0 < \frac{\pi}{2}$ et $u_{n+1} = \sin(u_n)$. Calculer la limite de $\sqrt{n}u_n$.

<details>
  <summary><b>Indications</b></summary>
    <ol>
      <li>
        Étudier la monotonie de la suite $(u_n)$.
      </li>
      <li>
        Développer $f(u_n)^\alpha$ à l'ordre $1$, en sachant que $u_n \underset{n\to+\infty}{\longrightarrow} 0$.
      </li>
      <li>
        Choisir $\alpha$ judicieusement et utiliser le lemme de Cesàro.
      </li>
      <li>
        Montrer que les hypothèses du théorème sont vérifiées et faire un DL de $\sin$.
      </li>
    </ol>
</details>

<details>
  <summary><b>Solution</b></summary>
    <ol>
      <li>
        Puisque $0 < f(x) < x$ pour tout $x > 0$, on a $0 < u_{n+1} < u_n$ pour tout $n\in\mathbb{N}$, donc $(u_n)$ est (strictement) décroissante et minorée par $0$.<br>
        Ainsi, $(u_n)$ converge vers une limite $\ell\geq 0$.<br>
        Par continuité de $f$, on a $\ell = f(\ell)$. Or, $f(x) < x$ pour tout $x > 0$, donc $\ell = 0$.<br>
        Donc $u_n \underset{n\to+\infty}{\longrightarrow} 0$.
      </li>
      <li>
        On a
        $$\begin{align*}
        u_{n+1}^\alpha &= f(u_n)^\alpha\\
        &= (u_n - au_n^{k+1} + \mathcal{O}(u_n^{k+2}))^\alpha\\
        &= u_n^\alpha \left(1 - au_n^k + \mathcal{O}(u_n^{k+1})\right)^\alpha\\
        &= u_n^\alpha \left(1 - \alpha au_n^k + \mathcal{O}(u_n^{k+1})\right)\\
        &= u_n^\alpha - \alpha au_n^{\alpha + k} + \mathcal{O}(u_n^{\alpha + k + 1}).
        \end{align*}$$
      </li>
      <li>
        En choisissant $\alpha = -k$, on obtient
        $$u_{n+1}^{-k} - u_n^{-k} = ka + \mathcal{O}(u_n).$$
        Par télescopage, on a
        $$u_n^{-k} - u_0^{-k} = nka + \mathcal{O}\left(\sum_{i=0}^{n-1} u_i\right).$$
        En divisant par $n$,
        $$\frac{1}{nu_n^k} = ka + \frac{1}{nu_0^k} + \mathcal{O}\left(\frac{1}{n}\sum_{i=0}^{n-1} u_i\right).$$
        D'après le lemme de Cesàro, puisque $u_n \underset{n\to+\infty}{\longrightarrow} 0$, on a
        $$\frac{1}{n}\sum_{i=0}^{n-1} u_i \underset{n\to+\infty}{\longrightarrow} 0.$$
        Donc
        $$\frac{1}{nu_n^k} = ka + o(1) \underset{n\to+\infty}{\longrightarrow} ka.$$
        Ainsi
        $$\sqrt[k]n u_n \underset{n\to+\infty}{\longrightarrow} \frac{1}{\sqrt[k]{ka}}.$$
      </li>
      <li>
        Avec $\ f = \sin$, on a bien $f$ continue sur $\mathbb{R}_+$, $\ f(0) = 0$, $0 < f(x) < x$ pour tout $\displaystyle 0 < x \leq \frac{\pi}{2}$, et
				$$f(x) = x - \frac{x^3}{6} + \mathcal{O}(x^4)$$
				au voisinage de $0$, donc $\displaystyle a = \frac{1}{6}$ et $k = 2$ ici.<br>
				Ainsi
				$$\sqrt{n}u_n \underset{n\to+\infty}{\longrightarrow} \frac{1}{\sqrt{2\times\frac{1}{6}}} = \sqrt{3}.$$
      </li>
    </ol>
</details>

<details>
  <summary><b>Pour aller plus loin</b></summary>
    <ul>
      <li>
        <a href="oraux#beos-7214-1">PC X-ESPCI 2023 - Vitesse de convergence d'une suite récurrente</a>
      </li>
    </ul>
</details>

---
