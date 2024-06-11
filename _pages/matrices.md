---
layout: default
title: Matrices
permalink: matrices
redirect_from:
    - matrice
---

---

<h3 id="groupe-gln-divise-somme-trace">Le cardinal d'un sous-groupe fini de $GL_n(\mathbb{R})$ divise la somme des traces de ses éléments</h3>

Soit $G$ un sous-groupe fini de $GL_n(\mathbb{R})$. Montrer que $\vert G\vert$ divise $\displaystyle\sum_{M\in G}\operatorname{Tr}(M)$.

<details>
  <summary><b>Indications</b></summary>
    <details>
    <summary><u>Indication 1</u></summary>
        Considérer la matrice $\displaystyle A = \frac{1}{\vert G\vert}\sum_{M\in G}M$.
    </details>
    <details>
    <summary><u>Indication 2</u></summary>
        Quelles sont les matrices (vues comme endomorphismes) ayant pour trace un entier ?
    </details>
    <details>
    <summary><u>Indication 3</u></summary>
        Calculer $A^2$.
    </details>
</details>

<details>
  <summary><b>Solution</b></summary>
    Posons $\displaystyle A = \frac{1}{\vert G\vert}\sum_{M\in G}M$.<br>
    Par linéarité de la trace, remarquons que $\vert G\vert$ divise $\displaystyle\sum_{M\in G}\operatorname{Tr}(M)$ si et seulement si $\operatorname{Tr}(A)$ est un entier.<br>
    Nous allons montrer que $A$ est un projecteur, i.e. $A^2 = A$. Puis en utilisant le fait que la trace d'un projecteur est son rang, on aura bien $\operatorname{Tr}(A)$ est un entier et donc $\vert G\vert$ divise $\displaystyle\sum_{M\in G}\operatorname{Tr}(M)$.<br><br>

    Montrons que $A^2 = A$. On a tout d'abord
    $$A^2 = \left(\frac{1}{\vert G\vert}\sum_{M\in G}M\right)^2 = \frac{1}{\vert G\vert^2}\sum_{N\in G}\sum_{M\in G}NM.$$

    Montrons que pour tout $N\in G$, on a $\displaystyle\sum_{M\in G}NM = \sum_{M\in G}M$.<br>
    Puisque $G$ est un groupe, l'application suivante est bien définie et est bijective :
    $$\begin{align*}
        \varphi : G &\longrightarrow G \\
        M &\longmapsto NM.
    \end{align*}$$

    Ainsi, par changement de variable dans la somme, on a
    $$\sum_{M\in G}NM = \sum_{M\in G}M.$$

    Donc
    $$A^2 = \frac{1}{\vert G\vert^2}\sum_{N\in G}\sum_{M\in G}NM = \frac{1}{\vert G\vert^2}\sum_{N\in G}\sum_{M\in G}M = \frac{1}{\vert G\vert}\sum_{M\in G}M = A,$$
    ce qui conclut la preuve de l'exercice.
</details>

---
