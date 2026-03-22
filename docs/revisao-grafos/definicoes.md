# Definições Básicas

> Baseado em "Introdução à Teoria de Redes" — Alberto Saa, UNICAMP (2025)

---

## O que é um Grafo?

!!! abstract "Definição 1"
    Um **grafo** $G = (V, E)$ é uma estrutura composta por dois conjuntos:

    - $V = \{v_1, v_2, \ldots, v_n\}$ — conjunto de **vértices** (ou nós, ou sítios)
    - $E = \{e_1, e_2, \ldots, e_k\} \subset V \times V$ — conjunto de **arestas** (ligações, edges, links), sendo cada aresta $e_j(v_i, v_k)$ um par não ordenado de vértices distintos

### Terminologia básica

- Dois vértices são **adjacentes** se houver uma aresta que os conecte
- Duas arestas que se encontram em um vértice são **incidentes**
- **Ordem** de um grafo: $|G| = |V(G)|$ (número de vértices)
- **Tamanho**: $|E(G)|$ (número de arestas)
- Grafos sem auto-ligações (loops) nem múltiplas arestas entre o mesmo par são chamados **grafos simples**

---

## Representações Matriciais

### Matriz de Adjacência

A **matriz de adjacência** $A$ de um grafo é definida por:

$$
a_{ij} = \begin{cases} 1, & \text{se houver aresta } v_i \leftrightarrow v_j \\ 0, & \text{caso contrário} \end{cases}
$$

Propriedades:

- Matriz **simétrica** ($A = A^t$)
- Diagonal nula (grafo simples)
- Entradas 0 ou 1

### Matriz de Incidência

A **matriz de incidência** $M$ tem $n = |G|$ linhas e $k = |E(G)|$ colunas:

$$
m_{ij} = \begin{cases} 1, & \text{se a aresta } e_j \text{ contiver o vértice } v_i \\ 0, & \text{caso contrário} \end{cases}
$$

### Relação entre as matrizes

$$
MM^t = D + A
$$

onde $D = \text{diag}(d_1, d_2, \ldots, d_n)$ é a **matriz de graus**.

### Grau de um vértice

O **grau** $d_i$ do vértice $v_i$ é o número de arestas incidentes:

$$
d_i = \sum_{j=1}^{n} a_{ij}
$$

!!! tip "Lema do Handshaking"
    $$\sum_{i=1}^{n} d_i = 2|E(G)|$$

    O número de vértices com grau ímpar é sempre **par**.

### Matriz Laplaciana

$$
L = D - A
$$

- Simétrica, com diagonal dada pelos graus dos vértices
- Fundamental na teoria espectral de grafos

---

## Equivalência e Simetria

!!! abstract "Definição 2 — Isomorfismo"
    Dois grafos $G$ e $H$ são **isomorfos** se houver uma bijeção $f : V(G) \rightarrow V(H)$ tal que dois vértices $v_i, v_j \in V(G)$ são adjacentes se e somente se $f(v_i)$ e $f(v_j) \in V(H)$ também o forem.

**Teorema 1:** Dois grafos $G$ e $H$, com matrizes de adjacência $A_G$ e $A_H$, são isomorfos se e somente se houver uma **matriz de permutação** $P$ tal que:

$$
P^t A_G P = A_H
$$

!!! warning "Complexidade"
    Determinar se dois grafos são isomorfos é um problema da classe **NP** — verificar uma permutação dada é fácil, mas encontrar a permutação correta entre $n!$ possibilidades é computacionalmente custoso.

### Automorfismo (Simetria)

Um **automorfismo** é um isomorfismo de $G$ consigo mesmo ($G = H$):

$$
P^t A P = A
$$

Os automorfismos de um grafo formam um **grupo** (grupo de automorfismos).

---

## Grafos de Linha

Dado um grafo $G = (V, E)$, o **grafo de linha** $L_G$ tem:

- Vértices correspondentes às **arestas** de $G$
- Dois vértices de $L_G$ são adjacentes se as correspondentes arestas de $G$ são **incidentes**

**Teorema 3:** Se $G$ tem $n$ vértices e $\ell$ arestas, $L_G$ terá $\ell$ vértices e:

$$
q = \frac{1}{2} \text{Tr } D^2 - \ell
$$

arestas, onde $D$ é a matriz de graus.

**Teorema 4:** A matriz de adjacência do grafo de linha é:

$$
A = M^t M - 2I
$$
