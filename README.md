## Nota: sob construção 🏗️

# Anotações sobre Programação Orientada a Objetos

### Índice

1. [Programação Orientada a Objetos](#programação-orientada-a-objetos)
   1. [Objeto](#objeto)
   1. [Classe](#classe)
   1. [Instanciação](#instanciação)
   1. [Abstração](#abstração)
   1. [Encapsulamento](#encapsulamento)
   1. [Herança](#herança)
   1. [Polimorfismo](#polimorfismo)
2. [C++](#c)
   1. [Compilação](#compilação)
      1. [Pré-Processamento](#1-pré-processamento)
      1. [Compilação](#2-compilação)
      1. [Assembling](#3-assembling)
      1. [Linking](#4-linking)

# Programação Orientada a Objetos

## Objeto

Também pode ser chamado de **entidade**.

Um objeto é uma "coisa" do mundo real.

```
Um carro, uma casa, um livro.
```

Um objeto pode ser algo não-físico.

```
Uma consulta médica, uma reserva de hotel, uma conta bancária.
```

Um objeto é algo que você deseja **guardar ou processar dados sobre**.

Cada objeto é uma **instância** de uma classe na memória do computador.

## Classe

A classe possibilita a criação de objetos que compartilham características
comuns.

```C++
class Livro {
   public:
    // Atributos
    std::string titulo;
    std::string autor;
    int ano_publicacao;
    double preco;

    // Métodos
    void abrir(){};
    void fechar(){};
    void lerPagina(int numeroPagina){};
};
```

Código escrito para definir os atributos/propriedades e operações/métodos de um
objeto.

É um _template_ para a criação de objetos.

## Instanciação

```C++
Livro livro_mem_pos;
```

Se refere à criação de um objeto a partir de uma classe.

Quando os objetos são criados, seus atributos podem ter valores atribuídos,
tornando cada objeto do mesmo tipo uma entidade única.

```C++
livro_mem_pos.titulo = "Memórias Póstumas de Brás Cubas";
livro_mem_pos.autor = "Joaquim Maria Machado de Assis";
livro_mem_pos.ano_publicacao = 1881;
livro_mem_pos.preco = 22.50;
```

Cada atributo é escrito na classe com uma variável pública ou um procedimento de
propriedade.

```cpp
class Livro {
   public:
    void definirPreco(double preco) {
        this->preco = preco;
        std::cout << "Preço de livro alterado.\n";
    };
};
```

A combinação dos valores dos atributos atuais de um objeto é conhecida como o
**estado** do objeto.

É possível atribuir valores a atributos **enquanto** um objeto é instanciado
através de um método especial conhecido como **construtor**.

```C++
class Livro {
   public:
    Livro(std::string t, std::string a, int y)
        : titulo(t), autor(a), ano_publicacao(y), preco(0){};
};
```

```C++
Livro new_livro("Mais Um Livro de Autoajuda", "Caio Rolando da Rocha", 2022);
```

## Abstração

A abstração é a omissão de detalhes para que apenas as informações mais
essenciais sejam mantidas.

Podemos criar uma classe abstrata que possui os atributos e métodos comuns entre
um grupo de objetos que herdarão essa classe.

Podemos ter, por exemplo, diversos instrumentos musicais com o método "tocar",
sendo que todos executam esse método de forma diferente e específica ao
instrumento.

Por definição, uma classe abstrata deve possuir pelo menos um método virtual.

```C++
class Instrumento {
   public:
    virtual void tocar() = 0  // Função virtual
};

class Guitarra : public Instrumento {
   public:
    void tocar() override {
        std::cout << "Tocando a guitarra" << std::endl;
    }
};

class Piano : public Instrumento {
   public:
    void tocar() override {
        std::cout << "Tocando o piano" << std::endl;
    }
};
```

A lógica específica que cada instrumento implementa para ser tocado é omitida e
todos os instrumentos podem ser tocados pela chamada de um mesmo método, sem
que o usuário se preocupe com o que está acontecendo por trás da execução, isso
é abstração.

## Encapsulamento

Também conhecido como _ocultação de informação_.

Se refere à prática de esconder os dados e a complexidade do funcionamento
interno de um objeto e permitir o acesso somente por meio de _interfaces_
controladas.

```C++
class ContaBancaria {
   private:
    double saldo;
    int numero_conta;

   public:
    ContaBancaria(double saldo_inicial, int numero)
        : saldo(saldo_inicial), numero_conta(numero) {
    }

    void depositar(double valor) {
        saldo += valor;
    }

    void sacar(double valor) {
        if (valor <= saldo) {
            saldo -= valor;
        }
    }

    int getNumeroConta() const {
        return numero_conta;
    }
};
```

Para escrever código que cria um objeto à partir de uma classe, atribuir valores
a seus atributos e utilizar seus métodos, não é estritamente necessário
entender o funcionamento interno da classe.

É necessário saber o nome da classe, seus atributos e métodos disponíveis, e os
dados que precisam ser fornecidos quando esses métodos são utilizados. Isto é,
é necessário saber a **interface da classe**.

A encapsulação simplifica a utilização de objetos e garante que os dados e
operações encapsulados estão seguros.

## Herança

É o conceito onde uma classe deriva seus métodos e atributos de outra classe.

Herança pode resultar numa hierarquia de classes.

```C++
class DispositivoEletronico {
   public:
    void ligar(){};
    void desligar(){};
};

class Televisao : public DispositivoEletronico {
   public:
    void assistir(){};
};

int main() {
    Televisao tv_da_sala;
    tv_da_sala.ligar();
    tv_da_sala.assistir();
    tv_da_sala.desligar();
    return 0;
}
```

A classe no começo da hierarquia de herança se chama **classe base**.

Qualquer classe derivada de outra é chamada **subclasse** ou
**classe derivada**.

Aquela classe da qual outras classes são derivadas é uma **superclasse**.

Nota-se que existem dois tipos de superclasse:

- a superclasse **direta**, que é herdada explicitamente (um nível acima na
  hierarquia),
- e a superclasse **indireta**, herdada de dois ou mais níveis acima na
  hierarquia.

Frequentemente, a herança define uma relação de "é um" ou "tipo de" entre
objetos.

```C++
// Na geometria um retângulo ->é um<- quadrilátero.
class Retangulo : public Quadrilatero {
    // ...
}
```

```C++
// Um programador é um ->tipo de<- funcionário que é um ->tipo de<- pessoa.
class Funcionario : public Pessoa {
    // ...
}

class Programador : public Funcionario {
    // ...
}
```

A declaração de uma subclasse não afeta o código de sua super classe.

A herança preserva a integridade da superclasse.

## Polimorfismo

Polimorfismo se refere à habilidade de um objeto assumir múltiplas formas.

Na prática isso se refere à habilidade de uma linguagem de programação de
processar objetos diferentemente de acordo com sua classe ou tipo de dados.

Isso significa que uma classe pode implementar um método herdado de sua própria
maneira, e é então possível utilizar classes diferentes através da mesma
_interface_.

Como um exemplo real, ao invés de dizer

> Eu comprei um Samsung S20 novo!

você poderia dizer

> Eu comprei um celular novo!

Essa frase continuaria sendo verdadeira se você tivesse comprado um iPhone 11 ou
um Redmi Note 9.

A flexibilidade (polimorfismo) da palavra "celular" significa que você não
precisa especificar exatamente o tipo de celular a que você se refere.

```C++
class Veiculo {
   public:
    virtual void mover() = 0;
    /* O método mover() é abstrato & puro, isso é, as
    subclasses precisam o implementar para utilizá-lo */
};

class Carro : public Veiculo {
   public:
    int numeroPortas;
    void mover() override {
        // Lógica para mover um carro
    }
};

class Aviao : public Veiculo {
   public:
    double envergaduraAsa;
    void mover() override {
        // Lógica para mover um avião
    }
};

class Barco : public Veiculo {
   public:
    float comprimento;
    void mover() override {
        // Lógica para mover um barco
    }
};
```

Cada uma das subclasses possui dados diferentes de tipos diferentes.

Ao faze-las serem responsáveis pelos seus dados e pela implementação do método
`mover()`, é possível alcançar o polimorfismo.

Para qualquer instância das classes Carro, Aviao ou Barco, é possível utilizar,
por exemplo,

```C++
nome_do_objeto.mover()
```

# C++

## Compilação

O compilador recebe arquivos que contém código escrito em C++ e gera um arquivo
que pode ser executado pelo computador. Existem duas partes principais desse
processo: a compilação e a vinculação (_linking_).

É importante ressaltar a diferença entre os arquivos _header_ (.h/.hh/.hpp) e os
arquivos _source_ (.cpp/.cxx/.cc). Arquivos _header_ contém o código que
descreve as funcionalidades presentes, e os arquivos _source_ contém a
implementação dessas funcionalidades.

### 1. Pré-processamento

O trabalho do pré-processador é passar pelas palavras-chaves de
pré-processamento, como o `#define` e o `#include`, e aplicar as devidas
mudanças no código.

O `#define` é usado para substituição de texto e o `#include` para incluir o
conteúdo de outros arquivos no arquivo atual. Digamos que você possui os
seguintes arquivos a serem compilados:

```C++
//header.h
int soma(int a, int b){
    return a + b;
}
```

```C++
//main.cpp
#include <header.h>
#define inteiro int

inteiro main(){
}
```

O pré-processador criará o seguinte arquivo:

```C++
int soma(int a, int b){
    return a + b;
}

int main(){
}
```

O pré-processador também lida com as palavras-chaves de compilação condicional.
Que permitem que certas partes do código só sejam incluídas no arquivo final
caso uma condição seja verdadeira.

```cpp
#if 0
int main(){
}
#endif
```

No exemplo acima, o pré-processador removeria todo o código, já que a condição
não é verdadeira (0 equivale a falso).

### 2. Compilação

Após o pré-processador gerar o arquivo "traduzido" que contém apenas código em
C++, o compilador percorre as linhas desse arquivo e as converte em código
objeto (geralmente assembly). O compilador também verifica erros de sintaxe e
otimiza o código.

### 3. Assembling

O assembler transforma o código objeto gerado pelo compilador em código de
máquina (binário). O assembler também lida com os símbolos locais, que são as
variavéis e funções de cada arquivo individual. Eles são chamados de símbolos
porque até essa etapa eles não estão vinculados com seus respectivos endereços e
são apenas _placeholders_, é trabalho do assembler vincular os símbolos locais
de cada arquivo com seus endereços. É importante ressaltar que a vinculação
entre diferentes arquivos não é feita nessa etapa.

### 4. Linking

O linker então faz a tarefa de combinar os vários arquivos objeto gerados em um
único arquivo executável. Ele vincula os símbolos globalmente e verifica se
todas as referências estão corretas.
