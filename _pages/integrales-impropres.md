---
layout: default
title: Intégrales impropres
permalink: integrales-impropres
redirect_from:
  - intégrales-impropres
---

---

<h3 id="integrale-de-dirichlet-semi-convergence">
  <a href="#integrale-de-dirichlet-semi-convergence" class="header">
  Semi-convergence de l'intégrale de Dirichlet</a>
</h3>

Montrer que l'intégrale $\displaystyle \int_0^{+\infty}\frac{\sin x}{x}\,\mathrm{d}x$ est semi-convergente.

<details>
  <summary><b>Indications</b></summary>
    <details>
      <summary><u>Convergence</u></summary>
        Intégration par parties.
    </details>
    <details>
      <summary><u>Pas de convergence absolue</u></summary>
        Découper l'intégrale en parties et minorer chacune d'elles.
    </details>
</details>

<details>
  <summary><b>Solution</b></summary>
    Pour montrer que l'intégrale de Dirichlet est semi-convergente, il suffit de montrer qu'elle est convergente, mais qu'elle n'est pas absolument convergente.<br><br>
    <b>L'intégrale est convergente.</b><br>
    La fonction sinus cardinal définie par $\displaystyle \operatorname{sinc}(x) = \frac{\sin x}{x}$ est bien continue sur $\mathbb R_+^*$ et se prolonge par continuité en $0$ en posant $\operatorname{sinc}(0) = 1$. Donc $\operatorname{sinc}$ est intégrable sur $]0,1]$.<br>
    Soit $M>1$. Par intégration par parties :
    $$\int_1^M \frac{\sin x}{x}\,\mathrm{d}x = \left[-\frac{\cos x}{x}\right]_1^M - \int_1^M \frac{\cos x}{x^2}\,\mathrm{d}x.$$
    Or, $\displaystyle \frac{\cos M}{M} \underset{M\to+\infty}{\longrightarrow} 0$ et $\displaystyle \int_1^{+\infty} \frac{\cos x}{x^2}\,\mathrm{d}x$ est absolument convergente car $\displaystyle \left|\frac{\cos x}{x^2}\right| \leq \frac{1}{x^2}$ qui est bien intégrable sur $[1,+\infty[$ (intégrale de Riemann).<br>
    Ainsi, l'intégrale de Dirichlet $\displaystyle \int_0^{+\infty}\frac{\sin x}{x}\,\mathrm{d}x$ est convergente.<br><br>
    <b> L'intégrale est n'est pas absolument convergente.</b><br>
    Soit $n\in\mathbb N^*$. On peut découper l'intégrale suivante en $n$ parties (où $\sin$ a un signe constant) :
    $$\int_0^{n\pi}\left|\frac{\sin x}{x}\right|\,\mathrm{d}x = \sum_{k=1}^n \int_{(k-1)\pi}^{k\pi} \left|\frac{\sin x}{x}\right|\,\mathrm{d}x = \sum_{k=1}^n u_k$$
    avec $u_k = \displaystyle \int_{(k-1)\pi}^{k\pi} \frac{|\sin x|}{x}\,\mathrm{d}x \geq \frac{1}{k\pi}\int_{(k-1)\pi}^{k\pi} \left|\sin x\right|\,\mathrm{d}x$ car $\displaystyle \frac{1}{x} \geq \frac{1}{k\pi}$ pour $x\in [(k-1)\pi,k\pi]$.<br>
    Or, $\displaystyle \int_{(k-1)\pi}^{k\pi} |\sin x|\,\mathrm{d}x = \int_{0}^{\pi} |\sin x|\,\mathrm{d}x = \int_{0}^{\pi} \sin x\,\mathrm{d}x = 2$ (en remarquant par exemple que $x\mapsto|\sin x|$ est périodique de période $\pi$).<br>
    Donc
    $$\int_0^{n\pi}\left|\frac{\sin x}{x}\right|\,\mathrm{d}x \geq \sum_{k=1}^n \frac{2}{k\pi} = \frac{2}{\pi}\sum_{k=1}^n \frac{1}{k}.$$
    Or, la série harmonique est divergente.<br>
    Ainsi, l'intégrale de Dirichlet $\displaystyle \int_0^{+\infty}\frac{\sin x}{x}\,\mathrm{d}x$ n'est pas absolument convergente.
</details>

---
