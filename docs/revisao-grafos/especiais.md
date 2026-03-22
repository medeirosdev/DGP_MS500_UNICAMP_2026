# Grafos Especiais e Aplicações

> Baseado em "Introdução à Teoria de Redes" — Alberto Saa, UNICAMP (2025)

---

## Grafos Orientados e Ponderados

### Grafos Orientados (Digrafos)

Em um **grafo orientado**, as arestas possuem direção: a aresta $v_i \rightarrow v_j$ é diferente de $v_j \rightarrow v_i$.

- A matriz de adjacência **não é necessariamente simétrica**
- Distingue-se entre **grau de entrada** e **grau de saída**

### Grafos Ponderados

Em um **grafo ponderado**, cada aresta possui um **peso** (ou valor) associado. A matriz de adjacência passa a conter os pesos nas entradas ao invés de 0/1.

!!! tip "Relevância para o DGP"
    No DGP, o grafo é ponderado: os pesos das arestas são as **distâncias** entre átomos, obtidas por NMR ou outros experimentos.

---

## Grafos Notáveis

### Grafo Completo ($K_n$)

- Todo par de vértices é adjacente
- $|E| = \binom{n}{2} = \frac{n(n-1)}{2}$
- Todos os vértices têm grau $n-1$ (grafo regular)

### Grafo Estrela ($S_n$)

- Um vértice central conectado a $n-1$ vértices folha
- Vértice central com grau $n-1$, demais com grau 1

### Grafo Ciclo ($C_n$)

- $n$ vértices conectados em um ciclo
- Grafo regular de grau 2
- $|E| = n$

### Grafo Caminho ($P_n$)

- $n$ vértices conectados em sequência sem fechar ciclo
- Vértices das extremidades com grau 1, demais com grau 2
- $|E| = n - 1$

### Grafos Regulares

Um grafo é **regular** de grau $k$ se todos os vértices têm o mesmo grau $k$.

Se um grafo com $n$ vértices é regular com grau $k$, então $nk$ é necessariamente **par**, com $n \geq k + 1$.

---

## Passeios Eulerianos e Caminhos Hamiltonianos

| Conceito | Descrição |
|----------|-----------|
| **Passeio Euleriano** | Percorre todas as **arestas** exatamente uma vez |
| **Caminho Hamiltoniano** | Percorre todos os **vértices** exatamente uma vez |

Um grafo conexo admite um passeio Euleriano sse todos os vértices têm grau par.

---

## Problemas 2SAT e Grafos Orientados

### Grafo de Implicações

Problemas de satisfatibilidade booleana (2SAT) podem ser modelados usando **grafos de implicações** — grafos orientados onde as arestas representam implicações lógicas entre variáveis.

### Ordem Topológica

Em um grafo orientado **acíclico** (DAG), é possível ordenar os vértices de modo que toda aresta aponta "para frente" — esta é a **ordem topológica**.

---

## Medidas de Centralidade

Medidas que quantificam a "importância" de um vértice no grafo:

- **Centralidade de grau** — número de conexões
- **Centralidade de intermediação** (betweenness) — frequência com que o vértice aparece em caminhos mínimos
- **Centralidade de proximidade** (closeness) — inverso da distância média aos demais vértices
- **Centralidade de autovetor** — baseada nos autovalores da matriz de adjacência

---

## Clusters e Transitividade

O **coeficiente de clustering** mede a tendência dos vizinhos de um vértice de também serem vizinhos entre si.

### Conectividade Algébrica e Vetor de Fiedler

O **segundo menor autovalor** da Laplaciana ($\lambda_2$) é chamado de **conectividade algébrica** (ou valor de Fiedler). Ele mede quão "bem conectado" o grafo é:

- $\lambda_2 = 0$ sse o grafo é desconexo
- Quanto maior $\lambda_2$, mais difícil é "desconectar" o grafo

O autovetor correspondente é o **vetor de Fiedler**, utilizado em particionamento de grafos.

---

## Grafos Aleatórios

### Grafos de Erdős-Rényi $G(n, p)$

Modelo onde cada aresta entre $n$ vértices existe com probabilidade $p$, independentemente.

Propriedades de $G(n, p)$:

- **Triângulos:** número esperado = $\binom{n}{3} p^3$
- **Conectividade:** limiar em $p \sim \frac{\ln n}{n}$
- **Distância típica:** $\sim \frac{\ln n}{\ln(np)}$
- **Paradoxo das amizades:** em média, seus amigos têm mais amigos que você

### Grafos de Barabási-Albert

Modelo de **ligação preferencial** (preferential attachment):

- Novos vértices se conectam preferencialmente a vértices com alto grau
- Gera distribuição de graus em **lei de potência** (scale-free)
- Modela redes reais: internet, redes sociais, redes de citações

**Distâncias em redes livres de escala** são tipicamente muito curtas — fenômeno de **mundo pequeno** (small world).
