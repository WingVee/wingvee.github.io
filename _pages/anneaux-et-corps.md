---
layout: default
title: Anneaux et corps
permalink: anneaux-et-corps
redirect_from:
  - anneaux
  - corps
---

---

<h3 id="nombres-dyadiques">
  <a href="#nombres-dyadiques" class="header">
  Nombres dyadiques</a>
</h3>

Un nombre réel $x$ est dit **dyadique** (aussi appelé fraction dyadique ou rationnel dyadique) s'il s'écrit sous la forme $\displaystyle x = \frac{m}{2^n}$ avec $m\in\mathbb{Z}$ et $n\in\mathbb{N}$. C'est en quelque sorte l'équivalent en base 2 des nombres décimaux.<br>
On note $D$ l'ensemble des nombres dyadiques :

$$D = \left\{\frac{m}{2^n},\ (m,n)\in\mathbb{Z}\times\mathbb{N}\right\}.$$

1. Montrer que l'ensemble des nombres dyadiques $D$ est un sous-anneau de $(\mathbb{Q},+,\times)$.
2. Est-ce que $D$ est un corps ?
3. Expliciter les éléments inversibles de $D$.

<details>
  <summary><b>Indications</b></summary>
  <details>
    <summary><u>1. Anneau</u></summary>
      Pour montrer qu'une partie $B$ d'un anneau $(A,+,\times)$ est un sous-anneau, il suffit de montrer ce qui suit :
      $$1\in B, \quad \forall a,b\in B,\ a+b, -a,\ a\times b\in B.$$
  </details>
  <details>
    <summary><u>2. Corps ?</u></summary>
      Trouver un élément de $D$ qui n'a pas d'inverse dans $D$.
  </details>
  <details>
    <summary><u>3. Inversibles</u></summary>
      Un élément $x\in D$ est inversible lorsqu'il existe $y\in D$ tel que $x\times y = 1$.<br>
      Écrire $\displaystyle x=\frac{m}{2^n}$ et $\displaystyle y=\frac{m'}{2^{n'}}$ et résoudre l'équation $x\times y = 1$.
  </details>
</details>

<details>
  <summary><b>Solution</b></summary>
  <ol>
    <li>
      <u>Anneau :</u><br>
      Soit $x = \displaystyle \frac{m}{2^n}$ et $y = \displaystyle \frac{m'}{2^{n'}}$ deux nombres dyadiques. On a :
      <ul>
        <li>$1 = \displaystyle \frac{1}{2^0}\in D$.</li>
        <li>$\displaystyle x+y = \frac{m}{2^n} + \frac{m'}{2^{n'}} = \frac{m2^{n'} + m'2^n}{2^{n+n'}}\in D$.</li>
        <li>$\displaystyle -x = \frac{-m}{2^n}\in D$.</li>
        <li>$\displaystyle x\times y = \frac{m}{2^n}\times \frac{m'}{2^{n'}} = \frac{mm'}{2^{n+n'}}\in D$.</li>
      </ul>
      Donc $D$ est un sous-anneau de $(\mathbb{Q},+,\times)$.
    </li>
    <li>
      <u>Corps ?</u><br>
      L'élément $\displaystyle x = 3 = \frac{3}{2^0}$ est un nombre dyadique, mais il n'a pas d'inverse dans $D$ car $\displaystyle \frac{1}{3}\notin D$.<br>
      Donc $D$ n'est pas un corps.
    </li>
    <li>
      <u>Inversibles :</u><br>
      Un élément $x = \displaystyle \frac{m}{2^n}\in D$ est inversible dans $D$ lorsqu'il existe $y = \displaystyle \frac{m'}{2^{n'}}\in D$ tel que $x\times y = 1$.<br>
      On a alors $\displaystyle \frac{m}{2^n}\times \frac{m'}{2^{n'}} = \displaystyle \frac{mm'}{2^{n+n'}} = 1$, i.e. $mm' = 2^{n+n'}$.<br>
      Donc $m$ divise $2^{n+n'}$. Or, les diviseurs de $2^{n+n'}$ sont de la forme $\pm 2^k$ avec $0\leq k\leq n+n'$.<br>
      On a alors $m = \pm 2^k$ et donc $x = \pm 2^{k-n}$, i.e. $x$ est au signe près une puissance de 2 ou une inverse d'une puissance de 2.<br>
      La réciproque est immédiate : si $x = \pm 2^k$ avec $k\in\mathbb{Z}$, alors $x$ est inversible dans $D$, d'inverse $\displaystyle \pm 2^{-k}\in D$.<br><br>
      Ainsi, l'ensemble des éléments inversibles de $D$ est :
      $$U(D) = \left\{\pm 2^k,\ k\in\mathbb{Z}\right\}.$$
    </li>
  </ol>
</details>

---
