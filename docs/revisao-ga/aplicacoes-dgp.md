# Aplicações ao DGP

---

## Geometria Conformal e o DGP

Uma das aplicações mais poderosas da Álgebra Geométrica ao Distance Geometry Problem é através do **modelo conformal**, que utiliza o espaço $\mathbb{R}^{n+1,1}$.

### Espaço Conformal

Para trabalhar com geometria em $\mathbb{R}^n$, o modelo conformal acrescenta **duas dimensões extras**:

- $e_+$ com $e_+^2 = +1$
- $e_-$ com $e_-^2 = -1$

Definimos os vetores especiais:

$$
e_o = \frac{1}{2}(e_- - e_+) \quad \text{(origem)}
$$

$$
e_\infty = e_- + e_+ \quad \text{(ponto no infinito)}
$$

com as propriedades:

$$
e_o^2 = 0, \quad e_\infty^2 = 0, \quad e_o \cdot e_\infty = -1
$$

### Representação de pontos

Um ponto $x \in \mathbb{R}^n$ é representado no espaço conformal como:

$$
X = x + \frac{1}{2}\|x\|^2 e_\infty + e_o
$$

!!! tip "Distâncias no modelo conformal"
    A distância entre dois pontos $x$ e $y$ é codificada diretamente pelo **produto interno conformal**:

    $$X \cdot Y = -\frac{1}{2}\|x - y\|^2$$

    Isso torna o DGP uma questão de **álgebra** no espaço conformal.

---

## Matriz de Gram e Distâncias

### Matriz de distâncias ao quadrado

Dada uma configuração de pontos $x_1, \ldots, x_n \in \mathbb{R}^K$:

$$
D_{ij} = \|x_i - x_j\|^2 = \|x_i\|^2 - 2 x_i \cdot x_j + \|x_j\|^2
$$

### Matriz de Gram

A **matriz de Gram** $G$ é definida por:

$$
G_{ij} = x_i \cdot x_j = \langle x_i, x_j \rangle
$$

Relação com a matriz de distâncias (centrando os pontos no baricentro):

$$
G = -\frac{1}{2} J D J
$$

onde $J = I - \frac{1}{n}\mathbf{1}\mathbf{1}^t$ é a **matriz de centralização**.

### Propriedades da Matriz de Gram

- $G$ é **simétrica positiva semidefinida**
- $\text{rank}(G) = K$ (dimensão do espaço de realização)
- Os pontos podem ser recuperados por **decomposição espectral**: $G = X^t X$, onde $X$ é a matriz de coordenadas

!!! abstract "Teorema (Schoenberg)"
    Uma matriz $D$ de distâncias ao quadrado admite realização em $\mathbb{R}^K$ se e somente se a matriz de Gram $G = -\frac{1}{2}JDJ$ é **positiva semidefinida** com $\text{rank}(G) \leq K$.

---

## DGP na Linguagem da GA

### Formulação clássica

Dado um grafo $G = (V, E)$ com pesos $d : E \rightarrow (0, \infty)$, encontrar $x : V \rightarrow \mathbb{R}^K$ tal que:

$$
\|x_u - x_v\| = d_{u,v} \quad \forall \{u, v\} \in E
$$

### Formulação conformal

No modelo conformal, cada ponto $x_i$ vira $X_i$ e a condição de distância se traduz em:

$$
X_i \cdot X_j = -\frac{1}{2} d_{ij}^2
$$

As restrições geométricas viram **restrições algébricas lineares** no espaço conformal.

---

## Objetos Geométricos na GA Conformal

A GA conformal permite representar objetos geométricos como **multivetores**:

| Objeto | Representação |
|--------|--------------|
| Ponto | $X = x + \frac{1}{2}\|x\|^2 e_\infty + e_o$ |
| Par de pontos | $X_1 \wedge X_2$ |
| Circunferência | $X_1 \wedge X_2 \wedge X_3$ |
| Esfera | $X_1 \wedge X_2 \wedge X_3 \wedge X_4$ |
| Plano | Esfera passando por $e_\infty$ |
| Reta | Circunferência passando por $e_\infty$ |

### Interseções

A interseção de objetos geométricos corresponde ao **meet** (dual do join) na álgebra:

$$
A \vee B = (A^* \wedge B^*)^*
$$

Isso permite resolver geometricamente o DGP: encontrar a interseção de esferas definidas pelas restrições de distância.

---

## Branch and Prune com GA

O algoritmo **Branch and Prune (BP)** para o DGP pode ser formulado usando GA conformal:

1. **Branch:** Dados 3 pontos anteriores e distâncias conhecidas, o próximo ponto está na interseção de 3 esferas — no máximo **2 soluções** (reflexão)
2. **Prune:** Distâncias adicionais eliminam uma das soluções

Na GA conformal, a interseção de esferas é computada algebricamente via produto wedge e dualidade, resultando em implementações elegantes e eficientes.
