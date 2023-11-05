# Anotações sobre Programação Orientada a Objetos

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

Um objeto é uma "coisa" que você deseja **guardar ou processar dados sobre**.

Cada objeto é uma **instância** de uma classe na memória do computador.

## Classe
A classe possibilita a criação de objetos que compartilham características comuns.

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

Código escrito para definir os atributos/propriedades e operações/métodos de um objeto.

É um *template* para a criação de objetos.

## Instanciação

```C++
Livro livro_mem_pos;
```

Se refere à criação de um objeto a partir de uma classe.

Quando os objetos são criados, seus atributos podem ter valores atribuídos, tornando cada objeto do mesmo tipo uma entidade única.

```C++
livro_mem_pos.titulo = "Memórias Póstumas de Brás Cubas";
livro_mem_pos.autor = "Joaquim Maria Machado de Assis";
livro_mem_pos.ano_publicacao = 1881;
livro_mem_pos.preco = 22.50;
```

Cada atributo é escrito na classe com uma variável pública ou um procedimento de propriedade.

```cpp
class Livro {
   public:
    void definirPreco(double preco) {
        this->preco = preco;
        std::cout << "Preço de livro alterado.\n";
    };
};
```

A combinação dos valores dos atributos atuais de um objeto é conhecida como o **estado** do objeto.

É possível atribuir valores a atributos **enquanto** um objeto é instanciado através de um método especial conhecido como **construtor**.

```C++
Livro(std::string t, std::string a, int y)
    : titulo(t), autor(a), ano_publicacao(y), preco(0){};
```
```C++
Livro new_livro("Mais Um Livro de Autoajuda", "Caio Rolando da Rocha", 2022);
```

## Abstração

Simplificação da realidade.

## Encapsulação

Também conhecido como *ocultação de informação*.

Se refere à prática de esconder os dados e a complexidade do funcionamento interno de um objeto e permitir o acesso somente por meio de *interfaces* controladas.

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

Para escrever código que cria um objeto à partir de uma classe, atribui valores a seus atributos e utiliza seus métodos, não é estritamente necessário entender o funcionamento interno da classe.

É necessário saber o nome da classe, seus atributos e métodos disponíveis, e os dados que precisam ser fornecidos quando esses métodos são utilizados.

Tudo o que um programador estritamente precisa saber é a **interface da classe**.

A encapsulação simplifica a utilização de objetos e garante que os dados e operações encapsulados estão seguros.

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

Qualquer classe derivada de outra é chamada **subclasse** ou **classe derivada**.

Aquela classe da qual outras classes são derivadas é uma **superclasse**. 

Nota-se que existem dois tipos de superclasse:
- a superclasse **direta**, que é herdada explicitamente (um nível acima na hierarquia),
- e a superclasse **indireta**, herdada de dois ou mais níveis acima na hierarquia.

Frequentemente, a herança defina uma relação de "é um" ou "tipo de" entre objetos.

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

A declaração de uma subclasse não afeta o código de sua super classe. A herança preserva a integridade da superclasse.