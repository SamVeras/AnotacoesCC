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
a\\
b\\
c
\end{bmatrix}
$$

**3. Matriz dos termos independentes:** matriz coluna formada pelos termos independentes do sistema.

$$
\begin{bmatrix}
10\\
16\\
24
\end{bmatrix}
$$

**4. Matriz aumentada:** formada pelos coeficientes das incógnitas e pelos termos independentes, útil para descobrir o valor das incógnitas através do escalonamento.

$$
\begin{bmatrix}
2 & 4 & -6 & 10\\
4 & 2 & 2 & 16\\
2 & 8 & -4 & 24
\end{bmatrix}
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

**Método de Gauss-Jordan:** similar ao método de Gauss, mas escalonamos completamente a matriz do sistema. Resolvendo

## Vetores no $R^n$

### Definição

Um vetor no R^n é um conjunto ordenado de n números reais, representado como:
$$\vec{v} = (v_1, v_2, \ldots, v_n)$$
Onde $v_1, v_2, \ldots, v_n$ são as componentes do vetor $\vec{v}$.

### Operações com Vetores

**Igualdade:** Dois vetores $\vec{u}$ e $\vec{v}$ são iguais se, e somente se, suas componentes correspondentes forem iguais.

**Adição de Vetores:** A soma de dois vetores $\vec{u}$ e $\vec{v}$ é um vetor $\vec{w}$ tal que $\vec{w} = \vec{u} + \vec{v}$, onde as componentes de $\vec{w}$ são a soma das componentes correspondentes de $\vec{u}$ e $\vec{v}$.

**Multiplicação por Escalar:** O produto de um escalar $k$ por um vetor $\vec{v}$ é um vetor $\vec{w}$ tal que $\vec{w} = k\vec{v}$, onde as componentes de $\vec{w}$ são $k$ vezes as componentes correspondentes de $\vec{v}$.

**Norma Euclidiana:** A norma euclidiana de um vetor $\vec{v} = (v_1, v_2, \ldots, v_n)$ é dada por:
$$|\vec{v}| = \sqrt{v_1^2 + v_2^2 + \ldots + v_n^2}$$

### Espaços Vetoriais

Um espaço vetorial $V$ sobre um corpo $F$ (geralmente $\mathbb{R}$ ou $\mathbb{C}$) é um conjunto não vazio de vetores que satisfaz as seguintes propriedades:

**Fechado para adição**: Para quaisquer $\vec{u}, \vec{v} \in V$, temos $\vec{u} + \vec{v} \in V$.

**Existência do elemento neutro aditivo**: Existe um vetor $\vec{0} \in V$ tal que $\vec{u} + \vec{0} = \vec{u}$ para todo $\vec{u} \in V$.

**Existência do oposto aditivo**: Para todo $\vec{u} \in V$, existe $(-\vec{u}) \in V$ tal que $\vec{u} + (-\vec{u}) = \vec{0}$.
Fechado para multiplicação por escalar: Para todo $\vec{u} \in V$ e todo $\alpha \in F$, temos $\alpha\vec{u} \in V$.
Distributividade da multiplicação escalar em relação à adição de vetores: Para quaisquer $\vec{u}, \vec{v} \in V$ e $\alpha, \beta \in F$, temos $\alpha(\vec{u} + \vec{v}) = \alpha\vec{u} + \alpha\vec{v}$ e $(\alpha + \beta)\vec{u} = \alpha\vec{u} + \beta\vec{u}$.

#### Exemplos de Espaços Vetoriais

O conjunto $\mathbb{R}^n$ de todas as n-uplas de números reais é um espaço vetorial sobre $\mathbb{R}$.
O conjunto de todas as matrizes $m \times n$ com entradas em $\mathbb{R}$ é um espaço vetorial sobre $\mathbb{R}$.
O conjunto de todos os polinômios de grau $\leq n$ com coeficientes em $\mathbb{R}$ é um espaço vetorial sobre $\mathbb{R}$.

Subespaços Vetoriais
Um subconjunto $W$ de um espaço vetorial $V$ é um subespaço vetorial de $V$ se, e somente se, $W$ satisfaz as seguintes propriedades:

$\vec{0} \in W$
Se $\vec{u}, \vec{v} \in W$, então $\vec{u} + \vec{v} \in W$
Se $\vec{u} \in W$ e $\alpha \in F$, então $\alpha\vec{u} \in W$

### Combinação Linear e Dependência / Independência Linear

Uma combinação linear de vetores $\vec{v}_1, \vec{v}_2, \ldots, \vec{v}_n$ em um espaço vetorial $V$ é uma expressão da forma:
$$\alpha_1\vec{v}_1 + \alpha_2\vec{v}_2 + \ldots + \alpha_n\vec{v}_n$$

Onde $\alpha_1, \alpha_2, \ldots, \alpha_n$ são escalares.
Um conjunto de vetores ${\vec{v}_1, \vec{v}_2, \ldots, \vec{v}_n}$ é linearmente dependente se existe uma combinação linear não trivial (onde pelo menos um dos escalares é diferente de zero) que resulta no vetor nulo $\vec{0}$. Caso contrário, é linearmente independente.

Espero que essas informações adicionais complementem seu resumo de forma adequada. Sinta-se à vontade para me perguntar caso tenha dúvidas ou precise de mais detalhes sobre esses tópicos.
