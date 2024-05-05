# Álgebra Linear

## Sistemas Lineares

### Equações Lineares

Uma equação linear é uma equação que pode ser colocada na forma padrão:
$$ a_1x_1 + a_2x_2 + \dots + a_nx_n = b$$
Onde:\
$x_1, x_2, \dots, x_n$ são incógnitas/variáveis\
$a_1, a_2, \dots,  a_n$ são os coeficientes\
$b$ é um número real chamado de termo independente

#### Resolvendo

Uma equação linear na forma $a_1x_1 + a_2x_2 + \dots + a_nx_n = b$ com $n$ incógnitas e coeficientes $a_n$ não todos nulos e $b$ um número real, pode ser resolvida isolando uma das incógnitas (com coeficiente diferente de zero) e substituindo quaisquer valores para as demais incógnitas, agora chamadas de **variáveis livres**.

$$ 10x + 20y = 50 \Rightarrow 10x = 50 - 20y$$
Atribuindo $y = 2$:
$$ 10x = 50 - 20 \cdot 2$$
$$ 10x = 50 - 40$$
$$ 10x = 10 $$
$$ x = 1$$

Ou seja, temos que quando $y = 2$, $x=1$, mas essa é apenas uma das infinitas soluções dessa equação.

#### Teorema 1.1

Uma equação degenerada $0x_1 + 0x_2 + \dots + 0x_n = b$ com $n$ incógnitas e $b$ um número real:

I. Não tem solução se $b \neq 0$\
II. Tem infinitas soluções se $b = 0$

### Sistemas Lineares

Um sistema linear é um conjunto finito de equações lineares que tem uma quantidade finita de variáveis. Por exemplo:

$$
\begin{cases}
2a + 4b -6c = 10\\
4a + 2b + 2c = 16\\
2a + 8b - 4c = 24
\end{cases}
$$

Podemos representar esse sistema através de matrizes:

$$
\begin{bmatrix}
2 & 4 & -6\\
4 & 2 & 2\\
2 & 8 & -4
\end{bmatrix}
\begin{bmatrix}
a \\
b \\
c
\end{bmatrix}=
\begin{bmatrix}
10 \\
16 \\
24
\end{bmatrix}
$$

Cada uma dessas matrizes recebe um nome especial:

**1. Matriz de coeficientes:** a matriz dos coeficientes das incógnitas.

$$
\begin{bmatrix}
2 & 4 & -6\\
4 & 2 & 2\\
2 & 8 & -4
\end{bmatrix}
$$

**2. Matriz das incógnitas:** matriz coluna formada pelas incógnitas do sistema.

$$
\begin{bmatrix}
a \\
b \\
c
\end{bmatrix}
$$

**3. Matriz dos termos independentes:** matriz coluna formada pelos termos independentes do sistema.

$$
\begin{bmatrix}
10 \\
16 \\
24
\end{bmatrix}
$$

**4. Matriz aumentada:** formada pelos coeficientes das incógnitas e pelos termos independentes, útil para descobrir o valor das incógnitas através do escalonamento.

$$
\begin{bmatrix}
2 & 4 & -6 &10\\
4 & 2 & 2 & 16\\
2 & 8 & -4 & 24
\end{bmatrix}\\\
$$

#### Sistemas Homogêneos

Quando temos um sistema de equações lineares com todas as equações igualando a zero, damos a esse sistema o nome de sistema homogêneo. Por exemplo:

$$
\begin{cases}
a - 4b - 3c= 0\\
4a - b + 2c = 0\\
3a + b - c = 0
\end{cases}
$$

Todo sistema linear homogêneo tem pelo menos uma solução denominada solução trivial. Por exemplo, a solução trivial do sistema acima é $(0, 0, 0)$.

#### Classificação de Sistemas Lineares

**Sistema Possível Determinado (SPD):** o sistema é possível e possui uma única solução, ou seja, um único conjunto de valores para as variáveis que atende todas as equações ao mesmo tempo.

**Sistema Possível Indeterminado (SPI):** existem infinitas soluções (geralmente acontece por causa de uma divisão de zero por algum número).

**Sistema Impossível (SI):** não existem soluções, ou seja, não existe nenhum conjunto de valores para as variáveis que atenda o sistema inteiro.

#### Teorema 1.2

Se um sistema na forma escalonada apresentar a
equação degenerada $0x_1 + 0x_2 + 0x_3 + \ldots + 0x_n = b$, então:

$I.$ Se $b = 0$, essa equação pode ser omitida do sistema sem modificar o conjunto solução;

$II.$ Se $b \neq 0$, o sistema não tem solução.

#### Teorema 1.3

Um sistema na forma escalonada pode apresentar:

$I.$ Solução única se o número de variáveis for igual ao número de equações;

$II.$ Infinitas soluções se o número de equações for menor que o número de variáveis. Nesse caso, teremos variáveis livres.

#### Sistemas Equivalentes

Dois sistemas são ditos equivalentes quando as equações envolvem as mesmas variáveis e admitem a(s) mesma(s) solução(ões).

#### Resolvendo Sistemas Lineares

Existem dois métodos principais para a solução de sistemas lineares:

**Método de eliminação de Gauss:** fazer o escalonamento incompleto da matriz, e então substituir as variáveis nas equações para obter o conjunto solução.
Exemplo:

$$
\begin{bmatrix}
1 & 1 & -1 & \vert & -2 \\
2 & -1 & 1 & \vert & 5 \\
-1 & 2 & 2 & \vert & 1 \\
\end{bmatrix}
$$

Escalonando a matriz, obtemos:

$$
\begin{bmatrix}
1 & 1 & -1 & \vert & 2 \\
0 & 1 & -1 & \vert & -3 \\
0 & 0 & 1 & \vert & 2 \\
\end{bmatrix} \\
$$

Que equivale ao seguinte sistema de equações:

$$
\begin{cases}
x + y - z = 2\\
y - z = -3\\
z = 2
\end{cases}
$$

Agora podemos substituir o valor de $z$ na segunda equação e obter o valor de $y$ e então substituir ambos na primeira equação para obter o valor de $x$. Chegando no conjunto $(5,-1,2)$.

**Método de Gauss-Jordan:** similar ao método de Gauss, mas escalonamos completamente a matriz do sistema. Resolvendo o sistema anterior através de Gauss-Jordan:

$$
\begin{bmatrix}
1 & 1 & -1 & \vert & -2 \\
2 & -1 & 1 & \vert & 5 \\
-1 & 2 & 2 & \vert & 1 \\
\end{bmatrix}
$$

Escalonando completamente:

$$
\begin{bmatrix}
1 & 0 & 0 & \vert & 5 \\
0 & 1 & 0 & \vert & -1 \\
0 & 0 & 1 & \vert & 2 \\
\end{bmatrix}
$$

Podemos ver que o conjunto obtido foi o mesmo, $(5, -1, 2)$.

## Espaços Vetoriais

Um espaço vetorial $V$ sobre um corpo $F$ (geralmente $\mathbb{R}$ ou $\mathbb{C}$) é um conjunto não vazio de vetores no qual são definidas duas operações:

**Soma** $(+): V * V \rightarrow V$\
**Multiplicação por escalar** $(*): R * V \rightarrow V$

De modo que para quaisquer $u, v$ e $w$ $\in V$ e $a$ e $b \in\mathbb{R}$ as seguintes propriedades são verdadeiras:

### Propriedades da Adição

A1 - Associatividade da Adição:

$$\quad (u + v) + w = u + (v + w)$$

A2 - Comutatividade da Adição:

$$
\quad u + v = v + u
$$

A3 - Elemento neutro da adição:

$$\text{Existe} \space 0 \in V \text{ tal que }, \space u + 0 = u$$

A4 - Elemento oposto aditivo:

$$
\forall u \in V, \space \text{existe } (-u) \text{ tal que } u + (-u) = \mathbf{0}
$$

### Propriedades da Multiplicação

M1 - Distributividade da multiplicação (escalar):

$$
a\cdot(u+v) =a \cdot u + a \cdot v
$$

M2 - Distributividade da multiplicação (vetor):

$$
u \cdot (a+b)=a \cdot u + b \cdot u
$$

M3 - Associatividade da multiplicação escalar:

$$
a \cdot (b \cdot u) = (a \cdot b) \cdot u
$$

M4 - Elemento neutro da multiplicação:

$$
1 \cdot u = u
$$

### Vetores no $R^n$

Um vetor no R^n é um conjunto ordenado de n números reais, representado como:
$$\vec{v} = (v_1, v_2, \ldots, v_n)$$
Onde $v_1, v_2, \ldots, v_n$ são as componentes do vetor $\vec{v}$.

### Subespaços Vetoriais

Se $V$ é um espaço vetorial e quisermos mostrar que o subconjunto $W$ de $V$ é um subespaço vetorial, as propriedades $A_1$, $A_2$, $M_1$, $M_2$, $M_3$ e $M_4$ são válidas automaticamente para $W$ se forem válidas para os vetores de $V$, dizemos que são propriedades **hereditárias**.

Porém, o subconjunto pode não conter o vetor nulo ou não conter o vetor oposto de um vetor qualquer, portanto precisamos garantir a validade dessas propriedades.

#### Teorema 2.1

Seja $V$ um espaço vetorial. Um subconjunto $W$, não vazio, é um subespaço vetorial de $V$ se forem satisfeitas as seguintes condições:

$$
\text{1. Para todo } u, v \in W, \space \text{tem-se: u + v} \in W\\
\text{2. Para todo } u \in W \text{ e } a \in \mathbb{R}, \space \text{tem-se: } a \cdot u \in W
$$

Ou seja, a soma entre dois vetores do subespaço sempre resulta em um vetor que também está no subespaço. O mesmo se segue para a multiplicação de um vetor do subespaço por um escalar real.

Com isso, garantimos todas as oito propriedades do subespaço vetorial.

### Combinação Linear

Uma combinação linear de vetores $\vec{v}_1, \vec{v}_2, \ldots, \vec{v}_n$ em um espaço vetorial $V$ é uma expressão da forma:
$$\alpha_1\vec{v}_1 + \alpha_2\vec{v}_2 + \ldots + \alpha_n\vec{v}_n$$

Onde $\alpha_1, \alpha_2, \ldots, \alpha_n$ são escalares.
Um conjunto de vetores ${\vec{v}_1, \vec{v}_2, \ldots, \vec{v}_n}$ é linearmente dependente (LD) se existe uma combinação linear não trivial (onde pelo menos um dos escalares é diferente de zero) que resulta no vetor nulo $\vec{0}$. Caso contrário, é linearmente independente (LI).

### Subespaços Gerados

O
