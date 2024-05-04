# Álgebra Linear

## Sistemas Lineares
### Equações Lineares
Uma equação linear é uma equação que pode ser colocada na forma padrão:
$$ a_1x_1 + a_2x_2 + \dots + a_nx_n = b$$
Onde:\
$x_1, x_2, \dots,  x_n$ são incógnitas/variáveis\
$a_1, a_2, \dots,  a_n$ são os coeficientes\
$b$ é um número real chamado de termo independente

### Resolvendo
Uma equação linear na forma $a_1x_1 + a_2x_2 + \dots + a_nx_n = b$ com $n$ incógnitas e coeficientes $a_n$ não todos nulos e $b$ um número real, pode ser resolvida isolando uma das incógnitas (com coeficiente diferente de zero) e substituindo quaisquer valores para as demais incógnitas, agora chamadas de **variáveis livres**.

$$ 10x + 20y = 50 \Rightarrow 10x = 50 - 20y$$
Atribuindo $y = 2$:
$$ 10x = 50 - 20*2$$
$$ 10x = 50 - 40$$
$$ 10x = 10 $$
$$ x = 1$$

Ou seja, temos que quando $y = 2$, $x=1$, mas essa é apenas uma das infinitas soluções dessa equação.

### Teorema 1.1
Uma equação degenerada $0x_1 + 0x_2 + \dots + 0x_n = b$ com $n$ incógnitas e $b$ um número real:

I. Não tem solução se $b \neq 0$\
II. Tem infinitas soluções se $b = 0$

### Sistemas Lineares
Um sistema linear é um conjunto finito de equações lineares. Que tem uma quantidade finita. Por exemplo:
$\begin{cases}
a_{11}x_1 + a_{12}x_2 + \ldots + a_{1n}x_n = b_1\\
a_{21}x_1 + a_{22}x_2 + \ldots + a_{2n}x_n = b_2\\
a_{m1}x_1 + a_{m2}x_2 + \ldots + a_{mn}x_n = b_m
\end{cases}$

Em que:\
$x_1, x_2, x_3, \ldots, x_n$ são incógnitas ou variáveis;

$a_{ij}$ com $i \in \{1, 2, \ldots, m\}$ e $j \in \{1, 2, \ldots, n\}$ são os coeficientes das incógnitas; e

$b_1, b_2, b_3, \ldots, b_m$ são os termos independentes.


Se você observar bem, verá que podemos representar o sistema acima por meio de matrizes. Ou seja:

$$
\begin{equation*}
\begin{bmatrix}
a_{11} & a_{12} & \cdots & a_{1n} \\
a_{21} & a_{22} & \cdots & a_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
a_{m1} & a_{m2} & \cdots & a_{mn}
\end{bmatrix}
\begin{bmatrix}
x_1 \\
x_2 \\
\vdots \\
x_n
\end{bmatrix}
=
\begin{bmatrix}
b_1 \\
b_2 \\
\vdots \\
b_m
\end{bmatrix}
\end{equation*}
$$

Essas matrizes recebem nomes especiais:

**1. Matriz de coeficientes**: matriz
formada pelos coeficientes das
incógnitas.
$$
\begin{bmatrix}
a_{11} & a_{12} & \cdots & a_{1n} \\
a_{21} & a_{22} & \cdots & a_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
a_{m1} & a_{m2} & \cdots & a_{mn}
\end{bmatrix}
$$

**2. Matriz das incógnitas**: matriz
coluna formada pelas incógnitas do
sistema.
$$
\begin{bmatrix}
x_1 \\
x_2 \\
\vdots \\
x_n
\end{bmatrix}
$$

3. 
