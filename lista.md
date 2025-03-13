# Instruções
- Faça uma cópia deste arquivo .md para um repositório próprio
- Resolva as 8 questões objetivas assinalando a alternativa correta e **justificando sua resposta.**
- Resolva as 2 questões dissertativas escrevendo no próprio arquivo .md
- Lembre-se de utilizar as estruturas de código como ``esta aqui com ` `` ou
```javascript
//esta aqui com ```
let a = "olá"
let b = 10
print(a)
```
- Resolva as questões com uso do Visual Studio Code ou ambiente similar.
- Teste seus códigos antes de trazer a resposta para cá.
- Cuidado com o uso de ChatGPT (e similares), pois entregar algo só para ganhar nota não fará você aprender. Não seja dependente da máquina!
- Ao final, publique seu arquivo lista_01.md com as respostas em seu repositório, e envie o link pela Adalove. 

# Questões objetivas
**1) Considerando a execução do código abaixo, indique a alternativa correta e justifique sua resposta.**
```javascript
console.log(x);
var x = 5;
console.log(y);
let y = 10;
```
a) A saída será undefined seguido de erro 

b) A saída será 5 seguido de 10

c) A saída será undefined seguido de undefined

d) A saída será erro em ambas as linhas que utilizam console.log

A resposta é a **letra a)**. <br>
    Ambas as **variáveis** precisariam estar **definidas antes do console.log**, dessa forma, ele conseguiria puxar a variável e mostrar algo no terminal. Como ambas as variáveis foram **definidas depois**, o console.log **não identifica elas**, e nem define o valor certo no visor. <br>
A variavel **x é global**, e por isso da **undefined**, contudo como a var **y**, está definida com **let**, quando colocamos o código para rodar é como se ele **não existisse**, já que não foi definido no escopo (única coisa importante). <br>

**código do jogo corrigido:**
```javascript
var x = 5;
console.log(x);
let y = 10;
console.log(y);
```

**2) O seguinte código JavaScript tem um erro que impede sua execução correta. Analise e indique a opção que melhor corrige o problema. Justifique sua resposta.**

```javascript
function soma(a, b) {
    if (a || b === 0) {
        return "Erro: número inválido";
    }
    return a + b;
}
console.log(soma(2, 0));
```

a) Substituir if (a || b === 0) por if (a === 0 || b === 0)

b) Substituir if (a || b === 0) por if (a === 0 && b === 0)

c) Substituir if (a || b === 0) por if (a && b === 0)

d) Remover completamente a verificação if (a || b === 0)

Resposta **letra a).**  <br>
    Porque **(a || b === 0)**, nesse caso a **var a**, está sendo analizado separadamente de b===0, o código não verifica a variavel **a**, só esta verificando a **var b**, portanto a saída nesse caso seria 2, mesmo se **var a** fosse 0. A melhor forma de resolver esse problema é agregando **a === 0**, assim **ambas as variaveis serão verificadas** corretamente. <br>

______
**3) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
function calcularPreco(tipo) {
    let preco;

    switch(tipo) {
        case "eletrônico":
            preco = 1000;
        case "vestuário":
            preco = 200;
            break;
        case "alimento":
            preco = 50;
            break;
        default:
            preco = 0;
    }

    return preco;
}

console.log(calcularPreco("eletrônico"));
```

a) O código imprime 1000.

b) O código imprime 200.

c) O código imprime 50.

d) O código gera um erro.

A resposta é a **letra b)**. <br>
    Na minha primeira analise, ponderei que fosse **1000**, porém revendo a estrutura do código é possivel reparar a **ausência do break**, e sem o break ele continua imprimindo as variáveis até o proximo case. E por que aparece 200 no terminal e não 50? Porque no primeiro **break** que ele encontra ele **para**. <br>

**código corrigido:**
```javascript
function calcularPreco(tipo) {
    let preco;

    switch(tipo) {
        case "eletrônico":
            preco = 1000;
            break;
        case "vestuário":
            preco = 200;
            break;
        case "alimento":
            preco = 50;
            break;
        default:
            preco = 0;
    }

    return preco;
}

console.log(calcularPreco("eletrônico"));
```
______
**4) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
let numeros = [1, 2, 3, 4, 5];

let resultado = numeros.map(x => x * 2).filter(x => x > 5).reduce((a, b) => a + b, 0);

console.log(resultado);
```
a) 0

b) 6

c) 18

d) 24

A resposta é a letra d), 
Em consideração ao primeiro array, vetor, o jS map cria um array novo (x => x*2) só que multiplicando todos os elementos por 2, no filter(x => x > 5). Ele filtra apenas os elementos desse novo array que são maiores que 5 e no reduce((a, b) => a + b, 0);

Ele soma todos os elementos desse array filtrado, resultando em 24, que é a resultado de 4+8+10, que é o array filtrado.

______
**5) Qual será o conteúdo do array lista após a execução do código? Indique a alternativa correta e justifique sua resposta.**

```javascript
let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga");
console.log(lista);
```
a) ["banana", "maçã", "uva", "abacaxi", "manga", "laranja"]

b) ["banana", "abacaxi", "manga"]

c) ["banana", "abacaxi", "manga", "laranja"]

d) ["banana", "maçã", "uva", "abacaxi", "manga"]

**A resposta é a letra c)**. <br>
Nesse caso **splice()**, serve para remover/substituir elementos existentes, não existentes e como nesse caso, adicionando dois elementos ao array.  EM **lista.splice(1, 2)** o primeiro numero remete à **posição** que ele substitui e o segundo numero remete sobre **quantos elementos do array serão substituidos**. <br>

```javascript
let lista = ["banana", **"maçã", "uva"** "laranja"]; 
```
// nesse caso maça está na primeira posição. <br>

```javascript
lista.splice(1, 2, "abacaxi", "manga");
```

// E como foi pedido aqui, no segundo numero o valor sendo 2. Ele quer que dois elementos do array sejam substituídos. <br>

Portanto ao imprimir a lista os elementos que aparecem no terminal são **"Maça, abacaxi, manga, uva".** <br>
______
**6) Abaixo há duas afirmações sobre herança em JavaScript. Indique a alternativa correta e justifique sua resposta**

I. A herança é utilizada para compartilhar métodos e propriedades entre classes em JavaScript, permitindo que uma classe herde os métodos de outra sem a necessidade de repetir código.  

II. Em JavaScript, a herança é implementada através da palavra-chave `extends`.


a) As duas afirmações são verdadeiras, e a segunda justifica a primeira.

b) As duas afirmações são verdadeiras, mas a segunda não justifica a primeira.

c) A primeira afirmação é verdadeira, e a segunda é falsa.

d) A primeira afirmação é falsa, e a segunda é verdadeira.

A Resposta é a **letra a)**. <br>
**A segunda justifica a primeira**, porque existe uma hierarquia de pais e filhos e os **filhos são uma extensão**, dos pais. Pelo motivo de que quando ele fala que uma classe herda os métodos de outra, ela faz isso "extendendo" o que seria a primeira classe a partir de complementos.
______
**7) Dado o seguinte código. Indique a alternativa correta e justifique sua resposta.**

```javascript
class Pessoa {
  constructor(nome, idade) {
    this.nome = nome;
    this.idade = idade;
  }

  apresentar() {
    console.log(`Olá, meu nome é ${this.nome} e tenho ${this.idade} anos.`);
  }
}

class Funcionario extends Pessoa {
  constructor(nome, idade, salario) {
    super(nome, idade);
    this.salario = salario;
  }

  apresentar() {
    super.apresentar();
    console.log(`Meu salário é R$ ${this.salario}.`);
  }
}
```


I) A classe Funcionario herda de Pessoa e pode acessar os atributos nome e idade diretamente.  
II) O método `apresentar()` da classe Funcionario sobrepõe o método `apresentar()` da classe Pessoa, mas chama o método da classe pai usando `super`.  
III) O código não funciona corretamente, pois Funcionario não pode herdar de Pessoa como uma classe, já que o JavaScript não suporta herança de classes.

Quais das seguintes afirmações são verdadeiras sobre o código acima?

a) I e II são verdadeiras.

b) I, II e III são verdadeiras.

c) Apenas II é verdadeira.

d) Apenas I é verdadeira.

A resposta é a **letra a)**. pois o código está correto e o método apresentar() da classe Funcionario de fato sobrescreve o método apresentar() da classe Pessoa. Isso é um conceito do polimorfismo na POO.
______

**8) Analise as afirmações a seguir. Indique a alternativa correta e justifique sua resposta.**

**Asserção:** O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras diferentes.  
**Razão:** Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.

a) A asserção é falsa e a razão é verdadeira.

b) A asserção é verdadeira e a razão é falsa.

c) A asserção é verdadeira e a razão é verdadeira, mas a razão não explica a asserção.

d) A asserção é verdadeira e a razão é verdadeira, e a razão explica a asserção.

Resposta **letra c)**. <br>
Ambas estão corretas, a **assercão é verdadeira**, e a **razão é verdadeira**, no entanto a proposição de razão não justifica a proposição de asserção. Existem duas maneiras de implementar o polimorfismo, tanto com a sobrecarga de métodos quanto com a sobrescrita de método, no entanto o mais ultilizado é a sobrescrita de métodos, que se embaseia nas classes e os metodos. <br>
A sobrecarga deve ser usada quando a mesma ação será realizada com dados de entrada diferentes, e portanto de formas ligeiramente diferentes. <br>

______

# Questões dissertativas
9) O seguinte código deve retornar a soma do dobro dos números de um array, mas contém erros. Identifique os problemas e corrija o código para que funcione corretamente. Adicione comentários ao código explicado sua solução para cada problema.

```javascript
function somaArray(numeros) {

    for (i = 0; i < numeros.size; i++) {
        soma = (2*numeros[i]);
    }
    return soma;
}
console.log(somaArray([1, 2, 3, 4]));
```

# **Correção do código: **

```javascript
function somaArray(numeros) {

    let soma = 0;
    for (i = 0; i < numeros.length; i++) {
        soma += numeros[i]*2;
    }
    return soma;
}
console.log(somaArray([1, 2, 3, 4]));
```

1. Primeiro erro, é **numeros.size**, sendo o correto, **numeros.length**. 

2. Depois precisei colocar **let soma = 0;** antes do **for**, para inicializar a variável antes do laço de repetição, e conseguir chamar o número.
   
3.Para retornar a soma do dobro dos números de um array, escrevemos, **soma = soma + numeros[i]*2**; (isto pode ser simplificado em: soma += numeros[i]*2, onde o **+=**, funciona para **otimizar o código**). 

4.Ele seleciona o numero conforme a sua posição e depois multiplica ele por dois. Então os **números = [1,2,3,4]**, passam a ser **= (2,4,6,8)**. 

5. E por último, por conta do **console.log**, que quer mostrar a soma entre os números finais, aparecerá no terminal o valor da **somaArray = 20.** 

____
10) Crie um exemplo prático no qual você tenha duas classes:

- Uma classe `Produto` com atributos `nome` e `preco`, e um método `calcularDesconto()` que aplica um desconto fixo de 10% no preço do produto.
- Uma classe `Livro` que herda de `Produto` e modifica o método `calcularDesconto()`, aplicando um desconto de 20% no preço dos livros.

Explique como funciona a herança nesse contexto e como você implementaria a modificação do método na classe `Livro`.

```javascript
class Produto {
    constructor(nome, preco) {
        this.nome = nome
        this.preco = preco
    }

    calcularDesconto() {
        return this.preco - (this.preco *(10/100))
    }
}

class Livro extends Produto {
    constructor(nome, preco) {
        super(nome, preco)
    }

    calcularDesconto() {
        return this.preco - (this.preco*(20/100))
    }
}

livro = new Livro('Livro', 100)
console.log(livro.calcularDesconto())

produto = new Produto('Produto', 100)
console.log(produto.calculoDesconto())

```

**Resposta:** A herança é um recurso que permite criar um objeto especial com base em outro, os objetos são chamados com protype, a quantidade mínima que precisa ser herdada é um objeto para cada objeto. Com a herança conseguimos **otimizar o código**. Além de permitir a criação de subclasse, a **modificando** especificamente a subclasse **sem adulterar a classe base.** Para implementar o método livro, refiz a função, calcularDesconto(),   multipicando por 20, dividindo por 100. 

