# Teoria Espectral de Grafos

> Baseado em "Introdução à Teoria de Redes" — Alberto Saa, UNICAMP (2025)

---

## Espectro da Matriz de Adjacência

O **espectro** de um grafo é o conjunto de autovalores da sua matriz de adjacência $A$. Como $A$ é simétrica real, todos os autovalores são **reais**.

Propriedades importantes:

- $\text{Tr } A = \sum \lambda_i = 0$ (diagonal nula)
- $\text{Tr } A^2 = \sum \lambda_i^2 = 2|E(G)|$
- $\text{Tr } A^3 = \sum \lambda_i^3 = 6 N_\Delta(G)$

---

## Espectro da Matriz Laplaciana

A **Laplaciana** $L = D - A$ tem propriedades espectrais importantes:

- Todos os autovalores são **não negativos** ($\lambda_i \geq 0$)
- O menor autovalor é sempre $\lambda_1 = 0$, com autovetor $\mathbf{1} = (1, 1, \ldots, 1)^t$
- A **multiplicidade** de $\lambda = 0$ é igual ao número de **componentes conexas** do grafo

!!! info "Laplaciana sem sinal"
    A matriz $D + A = MM^t$ é chamada **signless Laplacian** e também surge em diversas aplicações.

---

## Matrizes Normalizadas

A **Laplaciana normalizada** é definida como:

$$
\mathcal{L} = D^{-1/2} L \, D^{-1/2} = I - D^{-1/2} A \, D^{-1/2}
$$

A **matriz de adjacência normalizada:**

$$
\mathcal{A} = D^{-1/2} A \, D^{-1/2}
$$

de modo que $\mathcal{L} = I - \mathcal{A}$.

---

## Espectro e Simetrias

Grafos isomorfos possuem o **mesmo espectro** (tanto de $A$ quanto de $L$). Isso decorre do fato de que matrizes similares têm os mesmos autovalores.

!!! warning "Atenção"
    O inverso **não** é verdadeiro: grafos com o mesmo espectro não são necessariamente isomorfos. Grafos com o mesmo espectro são chamados **co-espectrais**.

O espectro pode ser usado como **invariante** para mostrar que dois grafos **não** são isomorfos — basta mostrar que seus espectros diferem.
