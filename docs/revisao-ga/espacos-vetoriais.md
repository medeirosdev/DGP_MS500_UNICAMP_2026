# Espaços Vetoriais e Formas Bilineares

---

## Espaço Vetorial

!!! abstract "Definição"
    Um **espaço vetorial** $V$ sobre um corpo $\mathbb{F}$ (tipicamente $\mathbb{R}$) é um conjunto munido de duas operações:

    - **Adição:** $+ : V \times V \rightarrow V$
    - **Multiplicação por escalar:** $\cdot : \mathbb{F} \times V \rightarrow V$

    satisfazendo os axiomas de comutatividade, associatividade, elemento neutro, inverso aditivo, distributividade e compatibilidade com escalares.

### Base e Dimensão

- Um conjunto $\{e_1, e_2, \ldots, e_n\}$ é uma **base** de $V$ se for linearmente independente e gerar $V$
- A **dimensão** de $V$ é o número de vetores em qualquer base: $\dim V = n$
- Todo vetor $v \in V$ se escreve de forma única como $v = \sum_{i=1}^n v_i \, e_i$

---

## Formas Bilineares

!!! abstract "Definição"
    Uma **forma bilinear** é uma função $B : V \times V \rightarrow \mathbb{R}$ que é linear em cada argumento:

    - $B(\alpha u + \beta v, w) = \alpha B(u, w) + \beta B(v, w)$
    - $B(u, \alpha v + \beta w) = \alpha B(u, v) + \beta B(u, w)$

### Forma Bilinear Simétrica

Uma forma bilinear é **simétrica** se:

$$
B(u, v) = B(v, u), \quad \forall \, u, v \in V
$$

### Matriz de Gram

Dada uma base $\{e_1, \ldots, e_n\}$, a **matriz de Gram** de $B$ é:

$$
G_{ij} = B(e_i, e_j)
$$

Se $B$ é simétrica, $G$ é uma **matriz simétrica**.

---

## Positividade

A classificação de formas bilineares simétricas depende do comportamento de $B(v, v)$:

| Tipo | Condição | Exemplo |
|------|----------|---------|
| **Positiva definida** | $B(v, v) > 0$ para todo $v \neq 0$ | Produto interno euclidiano |
| **Positiva semidefinida** | $B(v, v) \geq 0$ para todo $v$ | Pode ter vetores não nulos com $B(v,v) = 0$ |
| **Negativa definida** | $B(v, v) < 0$ para todo $v \neq 0$ | $-\langle v, v \rangle$ |
| **Negativa semidefinida** | $B(v, v) \leq 0$ para todo $v$ | |
| **Indefinida** | $B(v, v)$ pode ser positivo ou negativo | Métrica de Minkowski |

### Assinatura

Pelo **Teorema de Sylvester** (Lei da Inércia), toda forma bilinear simétrica pode ser diagonalizada e a **assinatura** $(p, q, r)$ é um invariante:

- $p$ = número de autovalores positivos
- $q$ = número de autovalores negativos
- $r$ = número de autovalores nulos (nullidade)

$$
B(v, v) = \sum_{i=1}^{p} (v_i')^2 - \sum_{i=p+1}^{p+q} (v_i')^2
$$

numa base apropriada.

!!! tip "Critério de Sylvester"
    Uma forma bilinear simétrica é **positiva definida** se e somente se todos os **menores principais** da sua matriz de Gram forem positivos:

    $$\det G_1 > 0, \quad \det G_2 > 0, \quad \ldots, \quad \det G_n > 0$$

---

## Espaços com Produto Interno

!!! abstract "Definição"
    Um **produto interno** em $V$ é uma forma bilinear simétrica **positiva definida**:

    $$\langle \cdot, \cdot \rangle : V \times V \rightarrow \mathbb{R}$$

    satisfazendo:

    1. **Simetria:** $\langle u, v \rangle = \langle v, u \rangle$
    2. **Linearidade:** $\langle \alpha u + \beta v, w \rangle = \alpha \langle u, w \rangle + \beta \langle v, w \rangle$
    3. **Positividade:** $\langle v, v \rangle \geq 0$, com igualdade sse $v = 0$

### Norma induzida

$$
\|v\| = \sqrt{\langle v, v \rangle}
$$

### Distância induzida

$$
d(u, v) = \|u - v\| = \sqrt{\langle u - v, u - v \rangle}
$$

### Desigualdade de Cauchy-Schwarz

$$
|\langle u, v \rangle| \leq \|u\| \cdot \|v\|
$$

com igualdade sse $u$ e $v$ são linearmente dependentes.

### Ângulo entre vetores

$$
\cos \theta = \frac{\langle u, v \rangle}{\|u\| \cdot \|v\|}
$$

### Ortogonalidade

Dois vetores são **ortogonais** se $\langle u, v \rangle = 0$. Uma base onde todos os vetores são ortogonais entre si e têm norma 1 é uma **base ortonormal**:

$$
\langle e_i, e_j \rangle = \delta_{ij}
$$

---

## Espaços Quadráticos

De forma mais geral, podemos considerar uma **forma quadrática**:

$$
Q : V \rightarrow \mathbb{R}, \quad Q(v) = B(v, v)
$$

A forma bilinear pode ser recuperada da forma quadrática por **polarização**:

$$
B(u, v) = \frac{1}{2}\big[Q(u + v) - Q(u) - Q(v)\big]
$$

O par $(V, Q)$ é chamado **espaço quadrático**. Se $Q$ é positiva definida, temos um espaço com produto interno. Se não, temos espaços mais gerais que surgem naturalmente na Álgebra Geométrica.

### Espaço $\mathbb{R}^{p,q}$

O espaço $\mathbb{R}^{p,q}$ é $\mathbb{R}^{p+q}$ munido da forma quadrática com assinatura $(p, q)$:

$$
Q(v) = v_1^2 + \cdots + v_p^2 - v_{p+1}^2 - \cdots - v_{p+q}^2
$$

Casos importantes:

| Espaço | Assinatura | Nome |
|--------|-----------|------|
| $\mathbb{R}^{n,0}$ | $(n, 0)$ | Espaço Euclidiano |
| $\mathbb{R}^{1,3}$ | $(1, 3)$ | Espaço-tempo de Minkowski |
| $\mathbb{R}^{4,1}$ | $(4, 1)$ | Espaço conformal 3D |
