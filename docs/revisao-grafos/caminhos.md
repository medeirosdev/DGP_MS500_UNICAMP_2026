# Passeios, Caminhos e Ciclos

> Baseado em "Introdução à Teoria de Redes" — Alberto Saa, UNICAMP (2025)

---

## Definições

| Conceito | Descrição |
|----------|-----------|
| **Passeio** | Sequência de vértices conectados por arestas |
| **Caminho** | Passeio onde todos os vértices são diferentes (exceto possivelmente o primeiro e o último) |
| **Ciclo** | Caminho onde os vértices inicial e final coincidem |
| **Árvore** | Grafo sem nenhum ciclo |

O **comprimento** é sempre contado em número de passos (arestas percorridas).

---

## Potências da Matriz de Adjacência

As potências de $A$ fornecem informação sobre passeios no grafo:

$$
a_{ij}^{(2)} = \sum_{k=1}^{n} a_{ik} a_{kj}
$$

A entrada $(i, j)$ de $A^2$ corresponde ao **número de passeios de 2 passos** entre $v_i$ e $v_j$.

Em particular:

$$
\text{Tr } A^2 = \sum_{k=1}^{n} d_k = 2|E(G)|
$$

Para $A^3$:

$$
a_{ij}^{(3)} = \sum_{k=1}^{n} \sum_{\ell=1}^{n} a_{ik} a_{k\ell} a_{\ell j}
$$

Os elementos da diagonal de $A^3$ contam o número de **ciclos de 3 passos** (triângulos) que contêm cada vértice:

$$
\text{Tr } A^3 = 6 N_\Delta(G)
$$

onde $N_\Delta(G)$ é o número de triângulos no grafo.

!!! note "Passeios vs Caminhos"
    As entradas de $A^k$ contam **passeios**, não caminhos. Um passeio de $k$ passos que não é um caminho sempre engloba um caminho de $\ell < k$ passos.

---

## Conectividade

Um grafo é **conexo** se sempre houver um caminho conectando quaisquer pares de seus vértices.

**Componente conexa:** subconjunto maximal conexo de $G$.

Para grafos desconexos, as matrizes de adjacência e Laplaciana têm forma **bloco-diagonal** — cada bloco corresponde a uma componente conexa.

---

## Grafos Bipartidos

!!! abstract "Definição"
    Um grafo é **bipartido** se seus vértices puderem ser separados em dois conjuntos disjuntos $V_1$ e $V_2$ tais que vértices de $V_1$ se conectam apenas a vértices de $V_2$, e vice-versa.

**Propriedade fundamental:** Um grafo é bipartido **se e somente se** não contiver nenhum ciclo ímpar.

A matriz de adjacência de um grafo bipartido tem a forma:

$$
A = \begin{pmatrix} 0 & B \\ B^t & 0 \end{pmatrix}
$$

o que implica:

$$
A^2 = \begin{pmatrix} BB^t & 0 \\ 0 & B^tB \end{pmatrix}, \quad
A^3 = \begin{pmatrix} 0 & BB^tB \\ B^tBB^t & 0 \end{pmatrix}
$$

Em geral, $A^k$ é bloco-diagonal para $k$ par e bloco-antidiagonal para $k$ ímpar.

---

## Grafos como Espaços Métricos

!!! abstract "Definição 3 — Distância em grafos"
    A **distância** $\text{dist}(v_i, v_j)$ entre dois vértices pertencentes a uma parte conexa de um grafo é o **comprimento do menor caminho** entre $v_i$ e $v_j$.

Esta noção satisfaz as propriedades de uma **métrica**:

1. $\text{dist}(v_i, v_j) \geq 0$, com igualdade sse $v_i = v_j$
2. $\text{dist}(v_i, v_j) = \text{dist}(v_j, v_i)$ (simetria)
3. $\text{dist}(v_i, v_j) \leq \text{dist}(v_i, v_k) + \text{dist}(v_k, v_j)$ (desigualdade triangular)

**Definição equivalente via matrizes:**

$$
\text{dist}(v_i, v_j) = \text{menor inteiro positivo } k \text{ tal que } a_{ij}^{(k)} \neq 0
$$

### Estruturas métricas

| Conceito | Definição |
|----------|-----------|
| **Bola** $B_m(v)$ | $\{v' \in V(G) : \text{dist}(v, v') \leq m\}$ |
| **Excentricidade** | $\text{exc}(v) = \max_{v' \in V(G)} \text{dist}(v, v')$ |
| **Raio** | $\min_{v} \text{exc}(v)$ — mínima excentricidade |
| **Diâmetro** | $\max_{v} \text{exc}(v)$ — máxima excentricidade (maior distância entre dois vértices) |
| **Vértices centrais** | Vértices que realizam o raio |
| **Vértices periféricos** | Vértices que realizam o diâmetro |

!!! tip "Conexão com o DGP"
    A noção de grafos como espaços métricos é diretamente relevante ao Distance Geometry Problem, onde o grafo $G = (V, E)$ tem arestas ponderadas por distâncias e o objetivo é encontrar uma realização em $\mathbb{R}^K$.
