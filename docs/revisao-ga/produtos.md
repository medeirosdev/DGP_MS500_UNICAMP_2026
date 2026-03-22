# Produtos entre Vetores

---

## Visão Geral dos Produtos

Em $\mathbb{R}^n$ existem diferentes tipos de "multiplicação" entre vetores, cada um capturando uma informação geométrica distinta:

| Produto | Notação | Resultado | Informação Geométrica |
|---------|---------|-----------|----------------------|
| Interno (escalar) | $\langle u, v \rangle$ ou $u \cdot v$ | Escalar | Projeção, ângulo |
| Vetorial (cross) | $u \times v$ | Vetor (só em $\mathbb{R}^3$) | Perpendicular, área orientada |
| Externo (wedge) | $u \wedge v$ | Bivetor | Plano orientado, área |
| Geométrico | $uv$ | Multivetor | Unifica todos os anteriores |

---

## Produto Interno (Escalar)

!!! abstract "Definição"
    O **produto interno** (ou produto escalar) em $\mathbb{R}^n$ é:

    $$u \cdot v = \langle u, v \rangle = \sum_{i=1}^{n} u_i v_i$$

### Propriedades

1. **Simetria:** $u \cdot v = v \cdot u$
2. **Bilinearidade:** $(\alpha u + \beta w) \cdot v = \alpha(u \cdot v) + \beta(w \cdot v)$
3. **Positividade:** $v \cdot v \geq 0$, com $v \cdot v = 0 \iff v = 0$

### Interpretação geométrica

$$
u \cdot v = \|u\| \, \|v\| \cos \theta
$$

- $u \cdot v > 0$: ângulo agudo
- $u \cdot v = 0$: vetores ortogonais
- $u \cdot v < 0$: ângulo obtuso

### Projeção ortogonal

A projeção de $u$ sobre $v$:

$$
\text{proj}_v u = \frac{u \cdot v}{v \cdot v} \, v = \frac{u \cdot v}{\|v\|^2} \, v
$$

### Relação com distâncias

$$
\|u - v\|^2 = \|u\|^2 - 2(u \cdot v) + \|v\|^2
$$

!!! tip "Conexão com DGP"
    No DGP, as distâncias entre pontos são o dado de entrada. A relação acima mostra que o produto interno pode ser extraído das distâncias, o que é a base da **matriz de Gram** e do método de **multidimensional scaling**.

---

## Produto Vetorial (Cross Product)

!!! warning "Exclusivo de $\mathbb{R}^3$"
    O produto vetorial só é definido em $\mathbb{R}^3$ (e $\mathbb{R}^7$, via octonions).

!!! abstract "Definição"
    Para $u, v \in \mathbb{R}^3$:

    $$u \times v = \begin{vmatrix} e_1 & e_2 & e_3 \\ u_1 & u_2 & u_3 \\ v_1 & v_2 & v_3 \end{vmatrix} = (u_2 v_3 - u_3 v_2) \, e_1 - (u_1 v_3 - u_3 v_1) \, e_2 + (u_1 v_2 - u_2 v_1) \, e_3$$

### Propriedades

1. **Antissimetria:** $u \times v = -(v \times u)$
2. **Bilinearidade:** $(\alpha u + \beta w) \times v = \alpha(u \times v) + \beta(w \times v)$
3. **$u \times u = 0$** para todo $u$
4. **Não é associativo:** $(u \times v) \times w \neq u \times (v \times w)$ em geral

### Interpretação geométrica

$$
\|u \times v\| = \|u\| \, \|v\| \sin \theta
$$

- O resultado é um **vetor perpendicular** ao plano definido por $u$ e $v$
- A direção segue a **regra da mão direita**
- O módulo é a **área do paralelogramo** formado por $u$ e $v$

### Produto misto (escalar triplo)

$$
u \cdot (v \times w) = \det \begin{pmatrix} u_1 & u_2 & u_3 \\ v_1 & v_2 & v_3 \\ w_1 & w_2 & w_3 \end{pmatrix}
$$

Resultado: **volume** do paralelepípedo formado por $u$, $v$ e $w$.

---

## Produto Externo (Wedge Product)

!!! abstract "Definição"
    O **produto externo** (ou produto wedge) $\wedge$ é uma operação que generaliza o produto vetorial para qualquer dimensão:

    $$u \wedge v$$

    O resultado é um **bivetor** — um objeto que representa um plano orientado com área.

### Propriedades

1. **Antissimetria:** $u \wedge v = -(v \wedge u)$
2. **Bilinearidade:** $(\alpha u + \beta w) \wedge v = \alpha(u \wedge v) + \beta(w \wedge v)$
3. **$u \wedge u = 0$** para todo $u$
4. **Associatividade:** $(u \wedge v) \wedge w = u \wedge (v \wedge w)$

### Em termos de uma base

Se $\{e_1, e_2, \ldots, e_n\}$ é base de $\mathbb{R}^n$, os **bivetores de base** são:

$$
e_i \wedge e_j, \quad i < j
$$

Para $u = \sum u_i e_i$ e $v = \sum v_j e_j$:

$$
u \wedge v = \sum_{i < j} (u_i v_j - u_j v_i) \, e_i \wedge e_j
$$

### Número de bivetores de base

$$
\binom{n}{2} = \frac{n(n-1)}{2}
$$

### $k$-vetores

O produto externo se estende a $k$ vetores, gerando **$k$-vetores** (ou $k$-blades):

$$
u_1 \wedge u_2 \wedge \cdots \wedge u_k
$$

- **0-vetor:** escalar
- **1-vetor:** vetor
- **2-vetor (bivetor):** plano orientado
- **3-vetor (trivetor):** volume orientado
- **$n$-vetor (pseudoescalar):** volume orientado em $\mathbb{R}^n$

O número de $k$-vetores de base em $\mathbb{R}^n$ é $\binom{n}{k}$.

### Relação com o produto vetorial em $\mathbb{R}^3$

Em $\mathbb{R}^3$, o produto vetorial e o produto externo estão relacionados pelo **dual de Hodge**:

$$
u \times v = \star(u \wedge v)
$$

O produto vetorial é o "dual" do bivetor — transforma um plano orientado no vetor perpendicular a ele.

---

## Produto Tensorial

!!! abstract "Definição"
    O **produto tensorial** $u \otimes v$ é uma operação que não impõe simetria nem antissimetria:

    $$(u \otimes v)_{ij} = u_i v_j$$

O resultado é uma **matriz** (tensor de ordem 2). Qualquer tensor pode ser decomposto em parte simétrica e antissimétrica:

$$
u \otimes v = \frac{1}{2}(u \otimes v + v \otimes u) + \frac{1}{2}(u \otimes v - v \otimes u)
$$

A parte simétrica está relacionada ao produto interno e a parte antissimétrica ao produto externo.

---

## Resumo Comparativo

| Propriedade | $u \cdot v$ | $u \times v$ | $u \wedge v$ |
|-------------|-------------|--------------|--------------|
| Resultado | Escalar | Vetor | Bivetor |
| Simetria | Simétrico | Antissimétrico | Antissimétrico |
| Dimensões | Qualquer $n$ | Apenas $\mathbb{R}^3$ | Qualquer $n$ |
| Associativo | — | Não | Sim |
| Mede | Ângulo/projeção | Área + direção normal | Área + plano orientado |
| $v$ com $v$ | $\|v\|^2$ | $0$ | $0$ |
