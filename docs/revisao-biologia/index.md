# Revisão de Biologia

Revisão dos conceitos biológicos fundamentais para compreender as aplicações do Distance Geometry Problem na determinação de estruturas moleculares.

---

## Aminoácidos

Aminoácidos são as unidades básicas que compõem as proteínas. Existem **20 aminoácidos padrão** encontrados nas proteínas, cada um com uma estrutura comum:

- Um **grupo amino** ($-NH_2$) — o N-terminus
- Um **grupo carboxila** ($-COOH$) — o C-terminus
- Um **carbono alfa** ($C_\alpha$) central
- Uma **cadeia lateral** ($R$) — que diferencia cada aminoácido

Os 20 aminoácidos são classificados por suas propriedades:

### Apolares (hidrofóbicos)
Glicina (Gly), Alanina (Ala), Valina (Val), Leucina (Leu), Isoleucina (Ile), Prolina (Pro), Fenilalanina (Phe), Metionina (Met), Triptofano (Trp)

### Polares (hidrofílicos, sem carga)
Serina (Ser), Treonina (Thr), Cisteína (Cys), Tirosina (Tyr), Asparagina (Asn), Glutamina (Gln)

### Carregados positivamente (básicos)
Lisina (Lys), Arginina (Arg), Histidina (His)

### Carregados negativamente (ácidos)
Ácido aspártico (Asp), Ácido glutâmico (Glu)

!!! info "Elementos químicos relevantes"
    Os principais elementos presentes nos aminoácidos são: **H** (hidrogênio), **C** (carbono), **N** (nitrogênio), **O** (oxigênio), **S** (enxofre) e **P** (fósforo).

---

## Ligação Peptídica

A **ligação peptídica** é a ligação covalente que une dois aminoácidos. Ela ocorre por uma **reação de condensação** (desidratação):

1. O grupo **carboxila** ($-COOH$) de um aminoácido reage com o grupo **amino** ($-NH_2$) do aminoácido seguinte
2. Ocorre a liberação de uma molécula de **água** ($H_2O$)
3. Forma-se a ligação **C-N** entre os dois aminoácidos

$$
\text{Aminoácido}_1 + \text{Aminoácido}_2 \rightarrow \text{Dipeptídeo} + H_2O
$$

!!! note "Propriedades da ligação peptídica"
    - É uma ligação **planar** e **rígida** (caráter parcial de dupla ligação)
    - A rotação ocorre em torno dos ângulos **phi** ($\phi$) e **psi** ($\psi$), nos carbonos alfa
    - Essas restrições geométricas são fundamentais para o DGP

Cadeias de aminoácidos conectados por ligações peptídicas formam:

- **Dipeptídeo** — 2 aminoácidos
- **Oligopeptídeo** — poucos aminoácidos
- **Polipeptídeo** — muitos aminoácidos
- **Proteína** — um ou mais polipeptídeos com função biológica

---

## Proteínas

Proteínas são macromoléculas formadas por **sequências de aminoácidos** conectados por ligações peptídicas. A sequência específica de aminoácidos determina a estrutura e função da proteína.

### Níveis de estrutura

| Nível | Descrição |
|-------|-----------|
| **Primária** | Sequência linear de aminoácidos |
| **Secundária** | Padrões locais: $\alpha$-hélices e folhas-$\beta$ |
| **Terciária** | Estrutura 3D completa da cadeia polipeptídica |
| **Quaternária** | Arranjo de múltiplas cadeias polipeptídicas |

### Funções das proteínas

- **Imunidade** — anticorpos (ex: resposta contra SARS-CoV-2)
- **Hormônios** — insulina, hormônio do crescimento, prolactina
- **Catálise** — enzimas (digestão, fotossíntese, respiração)
- **Transporte** — hemoglobina (oxigênio), citocromo (elétrons), quinesina (carga celular)
- **Estrutura** — queratina (cabelo/unhas), colágeno (tecido conectivo), actina/miosina (músculos)

---

## Protein Folding Problem

O **Protein Folding Problem** (problema do enovelamento de proteínas) consiste em prever a estrutura tridimensional de uma proteína a partir da sua sequência de aminoácidos.

O fluxo central é:

$$
\text{DNA} \rightarrow \text{RNA} \rightarrow \text{Proteína (sequência)} \rightarrow \text{Estrutura 3D}
$$

!!! tip "Nobel de Química 2024"
    O Nobel de Química de 2024 foi concedido a **David Baker**, **Demis Hassabis** e **John M. Jumper** por suas contribuições revolucionárias no campo da predição e design de estruturas de proteínas, incluindo o **AlphaFold**.

### Conexão com o DGP

O DGP aparece naturalmente neste contexto: dados experimentais de **Ressonância Magnética Nuclear (NMR)** fornecem **distâncias entre átomos** da proteína. O problema consiste em calcular a estrutura 3D a partir dessas distâncias — exatamente o Distance Geometry Problem.
