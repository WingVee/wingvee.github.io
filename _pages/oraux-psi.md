---
layout: default
title: Oraux PSI
permalink: oraux-psi
---

---

<h3 id="beos-8362">
  <a href="#beos-8362" class="header">
  Centrale-Supélec 2024 - Extrema de $(x^2+y^2)^x$</a>
</h3>

Soit $\ f:\mathbb R^2\to\mathbb R$ définie pour tout $(x,y)\in\mathbb R^2$ par

$$f(x,y) = \begin{cases}
1 & \text{ si } (x,y) = (0,0), \\
(x^2+y^2)^x & \text{sinon}.
\end{cases}$$

1. Étudier les variations de $x\mapsto x^x$ sur $\mathbb R_+^*$.
2. Montrer que $\ f$ est continue sur $\mathbb R^2$.
3. Déterminer les points critiques de $\ f$.
4. Étudier les extrema locaux de $\ f$ sur $\mathbb R^2$.

**Mots-clés** : fonction de deux variables, extrema

**Source** : <a href="https://beos.prepas.org/sujet.php?id=8362" target="_blank">BEOS 8362</a>

<details>
  <summary><b>Indications</b></summary>
    <ol>
      <li>Écrire $x^x = e^{x\ln x}$.</li>
      <li>Remarquer que $|x| \leq (x^2+y^2)^{1/2}$ et utiliser les croissances comparées.</li>
      <li>Calculer les dérivées partielles sur $\mathbb R^2\setminus\{(0,0)\}$. Pour $(0,0)$, étudier $\displaystyle \frac{\partial f}{\partial x}(x,0)$.</li>
      <li>Deux méthodes sont possibles : étudier la hessienne, ou faire un calcul asymptotique $f(x+h,y+k) - f(x,y)$ où $(x,y)$ est un point critique.</li>
    </ol>
</details>

<details>
  <summary><b>Solution</b></summary>
    <ol>
      <li>
        Notons $g:x\in\mathbb R_+^*\mapsto x^x\in\mathbb R$.<br>
        On a $g(x) = e^{x\ln(x)}$, donc $\displaystyle g'(x) = \left(\ln(x)+\frac{x}{x}\right)e^{x\ln(x)} = (1+\ln(x))x^x$.<br>
        Or, $g(x) = e^{x\ln(x)} > 0$ pour tout $x > 0$.<br>
        Donc $g(x)$ est du même signe que $1+\ln(x)$, et $1+\ln(x) > 0 \iff x > \dfrac1e$.<br>
        Ainsi, $g$ est décroissante sur $\left]0,\dfrac1e\right]$ et croissante sur $\left[\dfrac1e,+\infty\right[$.
      </li>
      <li>
        Pour tout $(x,y)\neq(0,0)$, on a $\ f(x,y) = (x^2+y^2)^x = e^{x\ln(x^2+y^2)}$.<br>
        $f$ est alors clairement continue sur $\mathbb R^2\setminus\{(0,0)\}$.<br><br>
        Soit $(x,y)\in\mathbb R^2\setminus\{(0,0)\}$.<br>
        On a $|x\ln(x^2+y^2)| \leq |(x^2+y^2)^{1/2}\ln(x^2+y^2)|$.<br>
        En posant $h = x^2+y^2$, on a
        $$(x,y)\longrightarrow (0,0) \iff h \longrightarrow 0.$$
        Donc, par croissances comparées, on a
        $$|x\ln(x^2+y^2)| \leq |(x^2+y^2)^{1/2}\ln(x^2+y^2)| = |h^{1/2}\ln(h)| \xrightarrow[h\to 0]{} 0.$$
        Ainsi,
        $$f(x,y) = (x^2+y^2)^x = e^{x\ln(x^2+y^2)} \xrightarrow[(x,y)\to(0,0)]{} e^0 = 1 = f(0,0),$$
        i.e. $\ f$ est continue en $(0,0)$.<br>
        Donc $\ f$ est continue sur $\mathbb R^2$.
      </li>
      <li>
        Pour $(x,y)\neq(0,0)$, on a
        $$\frac{\partial f}{\partial x}(x,y) = \frac{\partial}{\partial x}\left((x^2+y^2)^x\right) = \frac{\partial}{\partial x}\left(e^{x\ln(x^2+y^2)}\right) = \left(\ln(x^2+y^2)+\frac{2x^2}{x^2+y^2}\right)(x^2+y^2)^x$$
        et
        $$\frac{\partial f}{\partial y}(x,y) = \frac{2xy}{x^2+y^2}(x^2+y^2)^x.$$
        Ainsi, puisque $(x^2+y^2)^x > 0$ pour tout $(x,y)\in\mathbb R^2$, on a
        $$\begin{cases}
        \dfrac{\partial f}{\partial x}(x,y) = 0 & \iff \ln(x^2+y^2)+\dfrac{2x^2}{x^2+y^2} = 0, \\ \\
        \dfrac{\partial f}{\partial y}(x,y) = 0 & \iff xy = 0.
        \end{cases}$$
        Si $y = 0$, alors $\displaystyle \ln(x^2) + 2 = 0 \iff x^2 = \frac1{e^2} \iff x = \pm\frac1e$.<br>
        Si $x = 0$, alors $\displaystyle \ln(y^2) = 0 \iff y = \pm 1$.<br><br>
        En $(0,0)$, on remarque que $\displaystyle \frac{\partial f}{\partial x}(x,0) = \left(\ln(x^2)+2\right)x^x \xrightarrow[x\to 0^{\pm}]{} -\infty$, donc $(0,0)$ n'est pas un point critique de $f$.<br><br>
        Ainsi, les points critiques de $\ f$ sont au nombre de 4 et sont $\displaystyle \left(\pm\frac1e,0\right)$ et $\displaystyle \left(0,\pm 1\right)$.
      </li>
      <li>
        <details>
          <summary><b>Méthode 1 : Étude de la hessienne / calcul des dérivées partielles secondes</b></summary>
            On a obtenu les dérivées partielles premières de $\ f$ en $(x,y)$ :
            $$\frac{\partial f}{\partial x}(x,y) = \left(\ln(x^2+y^2)+\frac{2x^2}{x^2+y^2}\right)(x^2+y^2)^x$$
            et
            $$\frac{\partial f}{\partial y}(x,y) = \frac{2xy}{x^2+y^2}(x^2+y^2)^x.$$
            Les dérivées partielles secondes sont alors :
            $$\begin{align*}
            \frac{\partial^2f}{\partial x^2}(x,y) &= \frac{\partial}{\partial x}\left(\ln(x^2+y^2)+\frac{2x^2}{x^2+y^2}\right)(x^2+y^2)^x + \left(\ln(x^2+y^2)+\frac{2x^2}{x^2+y^2}\right)\frac{\partial}{\partial x}\left((x^2+y^2)^x\right)\\
            &= \left(\frac{2x}{x^2+y^2}+\frac{4x(x^2+y^2)-4x^3}{(x^2+y^2)^2}\right)(x^2+y^2)^x + \left(\ln(x^2+y^2)+\frac{2x^2}{x^2+y^2}\right)^2(x^2+y^2)^x.\\
            \frac{\partial^2f}{\partial y^2}(x,y) &= \frac{\partial}{\partial y}\left(\frac{2xy}{x^2+y^2}\right)(x^2+y^2)^x + \frac{2xy}{x^2+y^2}\frac{\partial}{\partial y}\left((x^2+y^2)^x\right)\\
            &= \left(\frac{2x(x^2+y^2)-4xy^2}{(x^2+y^2)^2}\right)(x^2+y^2)^x + \left(\frac{2xy}{x^2+y^2}\right)^2(x^2+y^2)^x.\\
            \frac{\partial^2f}{\partial x\partial y}(x,y) &= \frac{\partial}{\partial x}\left(\frac{2xy}{x^2+y^2}\right)(x^2+y^2)^x + \frac{2xy}{x^2+y^2}\frac{\partial}{\partial x}\left((x^2+y^2)^x\right)\\
            &= \left(\frac{2y(x^2+y^2)-4x^2y}{(x^2+y^2)^2}\right)(x^2+y^2)^x + \left(\frac{2xy}{x^2+y^2}\right)\left(\ln(x^2+y^2)+\frac{2x^2}{x^2+y^2}\right)(x^2+y^2)^x.
            \end{align*}$$
            Ainsi, en $(0,\pm 1)$, on a
            $$\frac{\partial^2f}{\partial x^2}(0,\pm 1) = 0, \quad \frac{\partial^2f}{\partial y^2}(0,\pm 1) = 0, \quad \frac{\partial^2f}{\partial x\partial y}(0,\pm 1) = \pm 2.$$
            Donc $\displaystyle (0,\pm 1)$ est un point selle.<br>
            En $\displaystyle \left(\pm\frac1e,0\right)$, on a (on pose $\displaystyle x = \pm\frac1e$)
            $$\begin{align*}
            \frac{\partial^2f}{\partial x^2}(x,0) &= \left(\frac{2x}{x^2}+\frac{4x(x^2)-4x^3}{(x^2)^2}\right)(x^2)^x + \left(\ln(x^2)+\frac{2x^2}{x^2}\right)^2(x^2)^x\\
            &= \left(\frac2x+(-2+2)^2\right)(x^2)^x = \frac2x (x^2)^x = \pm 2e\ f(x,0).\\
            \frac{\partial^2f}{\partial y^2}(x,0) &= \left(\frac{2x(x^2)}{(x^2)^2}\right)(x^2)^x = \frac2x (x^2)^x = \pm 2e\ f(x,0).\\
            \frac{\partial^2f}{\partial x\partial y}(x,0) &= 0.
            \end{align*}$$
            Or $f(x,0)>0$, donc $\displaystyle \left(\frac1e,0\right)$ est un minimum local et $\displaystyle \left(-\frac1e,0\right)$ est un maximum local (tous stricts).
        </details>
        <details>
          <summary><b>Méthode 2 : Calcul asymptotique de $\ f(x+h,y+k)-f(x,y)$</b></summary>
            $\bullet\ $ Étudions le point critique $\displaystyle (0,1)$.<br>
            On a $\ f(0,1) = f(0,y) = 1$ pour tout $y\in\mathbb R$.<br>
            Soit $(h,k)\in\mathbb R^2$ au voisinage de $(0,0)$, on a
            $$\begin{align*}
            f(h,1+k) &= (h^2+(1+k)^2)^h\\
            &= (1+2k+o(\Vert(h,k)\Vert))^h\\
            &= e^{h\ln(1+2k+o(\Vert(h,k)\Vert))}\\
            &= 1 + h(2k+o(\Vert(h,k)\Vert)) + o(\Vert(h,k)\Vert^2)\\
            &= 1 + 2hk + o(\Vert(h,k)\Vert^2).
            \end{align*}$$
            Donc
            $$f(h,1+k) - f(0,1) = 2hk + o(\Vert(h,k)\Vert^2).$$
            $f$ admet alors un point selle en $(0,1)$ car $f(h,1+k) - f(0,1)$ change de signe en changeant de quadrant.<br>
            En effet, pour $\varepsilon$ au voisinage de $0$, on a
            $$f(\varepsilon,1+\varepsilon) - f(0,1) \sim 2\varepsilon^2 > 0 \quad\text{et}\quad f(-\varepsilon,1+\varepsilon) - f(0,1) \sim -2\varepsilon^2 < 0.$$
            <br>
            $\bullet\ $ Étudions le point critique $\displaystyle (0,-1)$.<br>
            En remarquant que $y\mapsto f(x,y)$ est paire pour tout $x\in\mathbb R$, la nature du point critique $\displaystyle (0,-1)$ est la même que celle du point critique $\displaystyle (0,1)$.<br>
            Donc $(0,-1)$ est un point selle de $\ f$.<br><br>
            $\bullet\ $ Étudions le point critique $\displaystyle \left(\frac1e,0\right)$.<br>
            On a $\displaystyle\ f\left(\frac1e,0\right) = \left(\frac1{e^2}\right)^{\frac1e}$.<br>
            Soit $(h,k)\in\mathbb R^2$ au voisinage de $(0,0)$, on a
            $$\begin{align*}
            f\left(\frac1e+h,k\right) &= \left(\left(\frac1e+h\right)^2+k^2\right)^{\frac1e+h}\\
            &= \left(\frac{1}{e^2}+\frac2e h+h^2+k^2\right)^{\frac1e}\left(\frac{1}{e^2}+\frac2e h+h^2+k^2\right)^h\\
            &= \left(\frac{1}{e^2}\right)^{\frac1e}(1+2eh+e^2h^2+e^2k^2)^{\frac1e}e^{h\ln\left(\frac{1}{e^2}+\frac2e h+h^2+k^2\right)}.\\
            \end{align*}$$
            Or,
            $$\begin{align*}
            (1+2eh+e^2h^2+e^2k^2)^{\frac1e} &= 1 + \frac1e(2eh+e^2h^2+e^2k^2) + \frac{\frac1e\left(\frac1e-1\right)}{2}(2eh)^2+o(\Vert(h,k)\Vert^2)\\
            &= 1 + 2h + eh^2 + ek^2 + 2e\left(\frac1e-1\right)h^2 + o(\Vert(h,k)\Vert^2)\\
            &= 1 + 2h + (2-e)h^2 + ek^2 + o(\Vert(h,k)\Vert^2)\\
            \end{align*}$$
            et
            $$\begin{align*}
            h\ln\left(\frac{1}{e^2}+\frac2e h+h^2+k^2\right) &= h\ln\left(\frac{1}{e^2}\right) + h\ln\left(1+2eh+e^2h^2+e^2k^2\right)\\
            &= -2h + h\ln(1 + 2eh + o(\Vert(h,k)\Vert))\\
            &= -2h + h(2eh + o(\Vert(h,k)\Vert))\\
            &= -2h + 2eh^2 + o(\Vert(h,k)\Vert^2),\\
            \end{align*}$$
            d'où
            $$\begin{align*}
            e^{h\ln\left(\frac{1}{e^2}+\frac2e h+h^2+k^2\right)} &= e^{-2h + 2eh^2 + o(\Vert(h,k)\Vert^2)}\\
            &= 1 - 2h + 2eh^2 + \frac12(2h)^2 + o(\Vert(h,k)\Vert^2)\\
            &= 1 - 2h + 2(e+1)h^2 + o(\Vert(h,k)\Vert^2).\\
            \end{align*}$$
            Ainsi,
            $$\begin{align*}
            f\left(\frac1e+h,k\right) &= f\left(\frac1e,0\right)\left(1 + 2h + (2-e)h^2 + ek^2 + o(\Vert(h,k)\Vert^2)\right)\left(1 - 2h + 2(e+1)h^2 + o(\Vert(h,k)\Vert^2)\right)\\
            &= f\left(\frac1e,0\right)\left(1 - 2h + 2(e+1)h^2 + 2h -4h^2 + (2-e)h^2 + ek^2 + o(\Vert(h,k)\Vert^2)\right)\\
            &= f\left(\frac1e,0\right)\left(1 + eh^2 + ek^2 + o(\Vert(h,k)\Vert^2)\right).
            \end{align*}$$
            Donc, puisque $\displaystyle\ f\left(\frac1e,0\right) > 0$, on a
            $$f\left(\frac1e+h,k\right) - f\left(\frac1e,0\right) = f\left(\frac1e,0\right)eh^2 + f\left(\frac1e,0\right)ek^2 + o(\Vert(h,k)\Vert^2)$$
            qui est strictement positif au voisinage de $(0,0)$ (sans compter $(0,0)$).<br>
            Donc $\displaystyle \left(\frac1e,0\right)$ est un minimum local strict de $\ f$.<br><br>
            $\bullet\ $ Étudions le point critique $\displaystyle \left(-\frac1e,0\right)$.<br>
            En modifiant judicieusement les signes, on montre que $\displaystyle \left(-\frac1e,0\right)$ est un maximum local de $f$.<br>
            On a $\displaystyle\ f\left(\pm\frac1e,0\right) = \left(\frac1{e^2}\right)^{\pm\frac1e}$.<br>
            Soit $(h,k)\in\mathbb R^2$ au voisinage de $(0,0)$, on a
            $$\begin{align*}
            f\left(\pm\frac1e+h,k\right) &= \left(\left(\pm\frac1e+h\right)^2+k^2\right)^{\pm\frac1e+h}\\
            &= \left(\frac{1}{e^2}\pm\frac2e h+h^2+k^2\right)^{\pm\frac1e}\left(\frac{1}{e^2}\pm\frac2e h+h^2+k^2\right)^h\\
            &= \left(\frac{1}{e^2}\right)^{\pm\frac1e}(1\pm2eh+e^2h^2+e^2k^2)^{\pm\frac1e}e^{h\ln\left(\frac{1}{e^2} \pm\frac2e h+h^2+k^2\right)}.\\
            \end{align*}$$
            Or,
            $$\begin{align*}
            (1\pm2eh+e^2h^2+e^2k^2)^{\pm\frac1e} &= 1 \pm \frac1e(\pm2eh+e^2h^2+e^2k^2) + \frac{\pm\frac1e\left(\pm\frac1e-1\right)}{2}(2eh)^2+o(\Vert(h,k)\Vert^2)\\
            &= 1 + 2h \pm eh^2 \pm ek^2 \pm 2e\left(\pm\frac1e-1\right)h^2 + o(\Vert(h,k)\Vert^2)\\
            &= 1 + 2h + (2\mp e)h^2 \pm ek^2 + o(\Vert(h,k)\Vert^2)\\
            \end{align*}$$
            et
            $$\begin{align*}
            h\ln\left(\frac{1}{e^2}\pm\frac2e h+h^2+k^2\right) &= h\ln\left(\frac{1}{e^2}\right) + h\ln\left(1\pm 2eh+e^2h^2+e^2k^2\right)\\
            &= -2h + h\ln(1 \pm 2eh + o(\Vert(h,k)\Vert))\\
            &= -2h + h(\pm 2eh + o(\Vert(h,k)\Vert))\\
            &= -2h \pm 2eh^2 + o(\Vert(h,k)\Vert^2),\\
            \end{align*}$$
            d'où
            $$\begin{align*}
            e^{h\ln\left(\frac{1}{e^2}\pm\frac2e h+h^2+k^2\right)} &= e^{-2h \pm 2eh^2 + o(\Vert(h,k)\Vert^2)}\\
            &= 1 - 2h \pm 2eh^2 + \frac12(2h)^2 + o(\Vert(h,k)\Vert^2)\\
            &= 1 - 2h + 2(\pm e+1)h^2 + o(\Vert(h,k)\Vert^2).\\
            \end{align*}$$
            Ainsi,
            $$\begin{align*}
            f\left(\pm\frac1e+h,k\right) &= f\left(\pm\frac1e,0\right)\left(1 + 2h + (2\mp e)h^2 \pm ek^2 + o(\Vert(h,k)\Vert^2)\right)\left(1 - 2h + 2(\pm e+1)h^2 + o(\Vert(h,k)\Vert^2)\right)\\
            &= f\left(\pm\frac1e,0\right)\left(1 - 2h + 2(\pm e+1)h^2 + 2h -4h^2 + (2\mp e)h^2 \pm ek^2 + o(\Vert(h,k)\Vert^2)\right)\\
            &= f\left(\pm\frac1e,0\right)\left(1 \pm eh^2 \pm ek^2 + o(\Vert(h,k)\Vert^2)\right).
            \end{align*}$$
            Donc, puisque $\displaystyle\ f\left(-\frac1e,0\right) > 0$, on a
            $$f\left(-\frac1e+h,k\right) - f\left(-\frac1e,0\right) = - f\left(-\frac1e,0\right)eh^2 - f\left(-\frac1e,0\right)ek^2 + o(\Vert(h,k)\Vert^2)$$
            qui est strictement négatif au voisinage de $(0,0)$ (sans compter $(0,0)$).<br>
            Donc $\displaystyle \left(-\frac1e,0\right)$ est un maximum local strict de $\ f$.
        </details>
        Donc en résumé, $\ f$ admet un minimum local strict en $\displaystyle \left(\frac1e,0\right)$ et un maximum local strict en $\displaystyle \left(-\frac1e,0\right)$, et des points selle en $\displaystyle (0,\pm 1)$.
      </li>
    </ol>
</details>

---
