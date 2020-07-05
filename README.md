# golang-tutorial
Hello world!

## Introdução
### Breve histórico
Go é uma linguagem de programação desenvolvida pelo Google. O projeto foi iniciado em 2007 por Robert Griesemer, Rob Pike e Ken Thompson, e lançada em código aberto no ano de 2009. Go é multiplataforma e roda nos sistemas operacionais Windows, Linux, Mac OS X e FreeBSD. É uma linguagem focada em produtividade, concorrência e escalabilidade.

#### Instalação
Para utilizar o Go, faça a instalação em sua máquina seguindo as instruções do site oficial:

[Go Lang - Install](https://golang.org/doc/install)

## Variáveis e Tipos de Dados
Go é uma linguagem de tipos estáticos.

Vamos ver de forma bem rápida os tipos de dados nativos do Go, ao mesmo tempo que vemos formas de declarar variáveis e constantes e escrever comentários no código.

Podemos declarar uma variável usando a sintaxe com a palavra reservada `var`. Já a constante utiliza a palavra `const`:

```go
var nomeDaVariavel tipo = valor
const nomeDaConstante tipo = valor
```

Uma constante pode ser declarada sem tipo - ele será inferido no momento que receber um valor.

### Inteiros e Floats
Inteiros podem ser números positivos, negativos ou zero.

```go
// este eh um comentario em go
var ano int = 2020

// podemos declarar a variavel
var zeroAbsoluto int
// e inicializar depois
zeroAbsoluto = -459
```

Floats são números reais:

```go
/*
este eh um comentario em bloco no go.
abaixo usamos uma forma abreviada de declarar, inicializar e inferir o tipo de uma variavel
*/
pi := 3.14

// tambem podemos declarar multiplas variaveis de uma vez
preco, desconto := 9.99, 0.1
```

#### Tamanho dos Tipos
Com Go, é possível definir o tamanho da variável quando a declaramos. Ao invés de utilizar apenas `int`, podemos utilizar `int8`, `int16`, `int32` ou `int64`. O mesmo vale para o `float`, que possui `float32` e `float64`.

Em geral, a utilização desses tipos é necessária quando a memória do sistema em que o código vai rodar é limitada, como em smartwatches, sistemas embarcados em eletrodomésticos, etc.

A maioria dos computadores e notebooks modernos já trabalha com arquiteturas de 64 bits. Quando declaramos um `int` estamos inferindo o tipo `int64`.

### Strings
São sequências com um ou mais caracteres (letras, números, caracteres especiais) entre acentro grave (`) ou aspas duplas (").

Go suporta UTF-8 (até porque Ken Thompson e Rob Pike também são os criadores desse formato), então ele aceita strings com acentos gráficos naturalmente.

```go
textoEmUmaLinha := "Esta é uma mensagem"

textoComAspas := `Diga "Olá, mundo!" com Go`

textoComAspasEBarra := "Diga \"Olá, mundo!\" com Go"

textoComQuebraDeLinha := "Está é uma mensagem\n"

textoComMultiplasLinhas := `Fica decretado que agora vale a verdade. 
agora vale a vida, 
e de mãos dadas, 
marcharemos todos pela vida verdadeira.`
```

### Boolean
É um valor lógico que pode ser `true` ou `false` - tudo em caixa baixa.

```go
var invernoEhFrio bool = true
```

### Array
É uma sequência ordenada de elementos e de tamanho definido.

Em Go, uma vez que o tamanho de um array é definido, ele não pode mais ser alterado, pois a memória necessária já foi alocada. Isso torna o array um pouco difícil de trabalhar, mas melhora a performance do código.

```go
// declarando um vetor com capacidade para 10 inteiros
// se imprimirmos esta variavel, veremos um vetor com 10 zeros
// [0 0 0 0 0 0 0 0 0 0]
var num [10]int

// tambem podemos definir os itens do array na hora de cria-lo 
cidades := [3]string{"Manaus", "São Paulo", "Recife"}
```

### Slice
É uma sequência ordenada de elementos, com a diferença que seu tamanho é flexível.

Slices podem aumentar de tamanho dinamicamente - quando adicionamos um novo item ao `slice`, caso a capacidade já tenha sido atingida, ele aloca mais memória à variável. Por causa disso, é comum utilizar mais `slices` do que `arrays` ao programar em Go.

A sintaxe do `slice` é semelhante a do `array`, com exceção que não definimos seu tamanho.

```go
vogais := []string{"a", "e", "i", "o", "u"}
```

### Map
É um estrutura de pares chave-valor, ou simplesmente um dicionário.

Maps seguem a sintaxe abaixo, onde os tipos são definidos no momento da declaração.

```go
var m map[string]int
```
Em um exemplo com valores reais, podemos ter:

```go
valores := map[string]int{"foo": 1, "bar": 2}
```

## Referências
[Go by Example](https://gobyexample.com/)

[How To Code in Go](https://assets.digitalocean.com/books/how-to-code-in-go.pdf)

[Tour of Go](https://tour.golang.org/welcome/1)