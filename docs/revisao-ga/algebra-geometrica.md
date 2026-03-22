# Álgebra Geométrica (Clifford)

---

## Motivação

A Álgebra Geométrica (GA) unifica os produtos interno e externo em uma única operação — o **produto geométrico** — e fornece uma linguagem algébrica poderosa para manipular objetos geométricos de qualquer dimensão.

!!! info "Nomes"
    A Álgebra Geométrica também é chamada de **Álgebra de Clifford**, em homenagem a William Kingdon Clifford (1878). O nome "Álgebra Geométrica" enfatiza a interpretação geométrica.

---

## Álgebra de Clifford $\mathcal{G}(V, Q)$

!!! abstract "Definição"
    Dado um espaço quadrático $(V, Q)$ de dimensão $n$, a **Álgebra de Clifford** $\mathcal{G}(V, Q)$ (ou $Cl(V, Q)$) é a álgebra associativa gerada por $V$ com a relação fundamental:

    $$v^2 = Q(v) \quad \forall \, v \in V$$

    ou equivalentemente, para vetores de base $e_i$:

    $$e_i e_j + e_j e_i = 2 B(e_i, e_j)$$

    onde $B$ é a forma bilinear associada a $Q$.

### Notação por assinatura

Para $\mathbb{R}^{p,q}$, a álgebra é denotada $\mathcal{G}_{p,q}$ ou $Cl_{p,q}(\mathbb{R})$:

$$
e_i^2 = \begin{cases} +1 & \text{se } i = 1, \ldots, p \\ -1 & \text{se } i = p+1, \ldots, p+q \end{cases}
$$

$$
e_i e_j = -e_j e_i \quad \text{para } i \neq j
$$

---

## Produto Geométrico

!!! abstract "Definição"
    O **produto geométrico** de dois vetores $u, v \in V$ é:

    $$uv = u \cdot v + u \wedge v$$

    onde:

    - $u \cdot v = \frac{1}{2}(uv + vu)$ — parte simétrica (escalar)
    - $u \wedge v = \frac{1}{2}(uv - vu)$ — parte antissimétrica (bivetor)

### Propriedades

1. **Associativo:** $(uv)w = u(vw)$
2. **Distributivo:** $u(v + w) = uv + uw$
3. **Não comutativo** em geral
4. **$v^2 = v \cdot v = Q(v)$** — o quadrado de um vetor é um escalar

### Inversão de vetores

Se $v^2 = v \cdot v \neq 0$, o vetor $v$ é **invertível**:

$$
v^{-1} = \frac{v}{v^2} = \frac{v}{v \cdot v}
$$

---

## Estrutura da Álgebra

### Multivetores

Um elemento geral da álgebra é um **multivetor** — combinação linear de $k$-vetores de diferentes graus:

$$
M = \underbrace{\alpha}_{\text{escalar}} + \underbrace{v}_{\text{vetor}} + \underbrace{B}_{\text{bivetor}} + \underbrace{T}_{\text{trivetor}} + \cdots
$$

### Base da álgebra $\mathcal{G}_n$

Para $\mathcal{G}(\mathbb{R}^n)$ com base $\{e_1, \ldots, e_n\}$:

| Grau | Elementos de base | Quantidade |
|------|------------------|------------|
| 0 | $1$ (escalar) | $\binom{n}{0} = 1$ |
| 1 | $e_1, e_2, \ldots, e_n$ | $\binom{n}{1} = n$ |
| 2 | $e_{12}, e_{13}, \ldots, e_{(n-1)n}$ | $\binom{n}{2}$ |
| 3 | $e_{123}, e_{124}, \ldots$ | $\binom{n}{3}$ |
| $\vdots$ | $\vdots$ | $\vdots$ |
| $n$ | $e_{12\cdots n}$ (pseudoescalar) | $\binom{n}{n} = 1$ |

**Dimensão total:**

$$
\dim \mathcal{G}_n = \sum_{k=0}^{n} \binom{n}{k} = 2^n
$$

!!! example "Exemplos"
    - $\mathcal{G}_1$: dimensão $2$ — escalares + vetores em 1D
    - $\mathcal{G}_2$: dimensão $4$ — $\{1, e_1, e_2, e_{12}\}$
    - $\mathcal{G}_3$: dimensão $8$ — $\{1, e_1, e_2, e_3, e_{12}, e_{13}, e_{23}, e_{123}\}$

---

## Pseudoescalar

O **pseudoescalar** $I$ é o $n$-vetor de base:

$$
I = e_1 e_2 \cdots e_n = e_{12\cdots n}
$$

Propriedades:

- $I^2 = (-1)^{n(n-1)/2}$ no caso euclidiano
- Em $\mathcal{G}_2$: $I = e_{12}$, $I^2 = -1$ (comporta-se como $i$ dos complexos!)
- Em $\mathcal{G}_3$: $I = e_{123}$, $I^2 = -1$

### Dual de Hodge

O dual de um $k$-vetor $A$ é:

$$
A^* = AI^{-1}
$$

Em $\mathcal{G}_3$, o dual de um bivetor é um vetor — esta é a conexão com o produto vetorial:

$$
u \times v = -(u \wedge v) I^{-1}
$$

---

## Operações sobre Multivetores

### Reversão

A **reversão** $\tilde{M}$ inverte a ordem dos vetores em cada produto:

$$
\widetilde{e_i e_j \cdots e_k} = e_k \cdots e_j e_i
$$

Para um $k$-vetor: $\tilde{A}_k = (-1)^{k(k-1)/2} A_k$

### Involução de grau (conjugação principal)

$$
\hat{A}_k = (-1)^k A_k
$$

### Conjugação de Clifford

$$
\bar{A}_k = (-1)^{k(k+1)/2} A_k
$$

### Projeção de grau

$\langle M \rangle_k$ extrai a parte de grau $k$ de um multivetor $M$.

---

## Exemplos Fundamentais

### $\mathcal{G}_2 \cong$ Números Complexos (via pares)

Na álgebra $\mathcal{G}_2$, o pseudoescalar $I = e_{12}$ satisfaz $I^2 = -1$.

Os elementos da forma $z = a + bI$ (escalar + pseudoescalar) se comportam exatamente como **números complexos**.

### $\mathcal{G}_3$ e Rotações

Em $\mathcal{G}_3$, rotações são expressas usando **rotores**:

$$
R = e^{-B\theta/2}
$$

onde $B$ é o bivetor que define o plano de rotação e $\theta$ o ângulo. O vetor rotacionado é:

$$
v' = R v \tilde{R}
$$

!!! tip "Vantagem sobre matrizes"
    Rotores generalizam os **quaternions** e evitam o problema de gimbal lock. Funcionam em **qualquer dimensão**, não apenas $\mathbb{R}^3$.

### Reflexões

A reflexão de $u$ em relação ao plano perpendicular a $n$ (com $\|n\| = 1$):

$$
u' = -n u n
$$

Toda rotação é composição de duas reflexões (Teorema de Cartan-Dieudonné).
