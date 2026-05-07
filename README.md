# ArrayListJs

## Projeto criado para demonstrar a utilização dos métodos `map()`, `filter()` e `reduce()` na manipulação de arrays.

---

# O que são Arrays?

Arrays são listas contendo vários valores e objetos que utilizamos para armazenar dados dentro de uma única variável.

Um bom exemplo disso:

```
const lista = [1, 3, 6, 8, 10];
```

Essa lista é pequena, no entanto, e se eu tivesse uma lista maior e quisesse multiplicar todos os números dela por um valor que eu determinasse? E se eu quisesse filtrar apenas os números pares dessa lista? Ou qualquer outro tipo de filtragem? E se eu quisesse reduzir todos os elementos da lista para um único valor?

São para esse tipo de situação que utilizamos os métodos:

- `map()`
- `filter()`
- `reduce()`

Veremos como usar cada um deles e em qual contexto cada um se encaixa melhor.

---

# Método map()

O método `map()` percorre todos os elementos do array e, com base naquele array, cria um novo contendo as modificações desejadas.

Ele não modifica o array original.

Um exemplo bem simples é quando queremos multiplicar todos os elementos dentro de uma lista.

## Exemplo:

```
const numeros = [10, 20, 30, 40, 50];

const dobro = numeros.map((numero) => {
  return numero * 2;
});

console.log(dobro);
```

## Resultado:

```
[20, 40, 60, 80, 100]
```

## Explicação

Perceba que existe uma **Arrow Function** na utilização do método e que dentro dela é passado como parâmetro o valor `numero`.

Essa variável será utilizada para percorrer o array criando um novo array com as modificações desejadas.

---

# Método filter()

No `filter()` a ideia de utilização é bem simples. Usamos ele quando queremos filtrar valores de determinado array ou objetos.

Assim como o `map()`, ele também não modifica o array original, apenas devolve um novo array filtrado.

## Exemplo:

```
const lista = [10, 15, 14, 50];

const numerosPares = lista.filter(n => n % 2 === 0);

console.log(numerosPares);
```

## Resultado:

```
[10, 14, 50]
```

## Explicação

Perceba que aqui também utilizamos uma **Arrow Function** e que também temos uma variável `n` passada como parâmetro para percorrer a lista e encontrar os números pares.

---

# Método reduce()

Geralmente esse é o método que mais dá nó na cabeça, acredito que seja por conta dos seus parâmetros.

Utilizamos o método `reduce()` para reduzir uma quantidade de elementos do array em um único valor final.

Esse método possui:
- um acumulador
- uma variável para percorrer o array
- e um valor inicial

O acumulador é responsável por armazenar os valores das interações anteriores.

Já a variável `valor` será responsável por percorrer cada elemento do array.

E por fim temos o valor inicial, que define qual será o valor inicial do acumulador.

## Exemplo:

```
const lista = [10, 20, 30, 40];

const soma = lista.reduce((acumulador, valor) => {
  return acumulador + valor;
}, 0);

console.log(soma);
```

## Resultado:

```
100
```

## Explicação

Assim como nos demais métodos, aqui também existe o uso de **Arrow Function**.

Seguindo temos o parâmetro `acumulador`, aquele que literalmente vai acumulando o resultado de cada interação do método.

Em seguida temos o parâmetro `valor`, responsável por passar por cada elemento do array.

E por fim temos o `0` no final do método, que representa o valor inicial do acumulador.

Nesse exemplo o `reduce()` fez:

```txt
0 + 10 = 10
10 + 20 = 30
30 + 30 = 60
60 + 40 = 100
```

---

# Utilizando esses métodos em objetos

Agora vamos ver exemplos mais próximos da realidade utilizando arrays de objetos.

---

# Utilizando map() com objetos

Imagine uma lista de produtos de uma loja e queremos pegar apenas o nome de cada produto.

## Exemplo:

```
const produtos = [
  { nome: "Notebook", preco: 3000 },
  { nome: "Mouse", preco: 120 },
  { nome: "Teclado", preco: 250 }
];

const nomesProdutos = produtos.map(produto => {
  return produto.nome;
});

console.log(nomesProdutos);
```

## Resultado:

```
["Notebook", "Mouse", "Teclado"]
```

## Explicação

O `map()` percorreu cada objeto da lista e criou um novo array contendo apenas os nomes dos produtos.

---

# Utilizando filter() com objetos

Agora imagine que queremos filtrar apenas os produtos acima de 200 reais.

## Exemplo:

```
const produtosCaros = produtos.filter(produto => {
  return produto.preco > 200;
});

console.log(produtosCaros);
```

## Resultado:

```
[
  { nome: "Notebook", preco: 3000 },
  { nome: "Teclado", preco: 250 }
]
```

## Explicação

O `filter()` percorreu cada objeto da lista verificando quais produtos possuíam preço maior que 200.

Os que atenderam essa condição foram adicionados ao novo array.

---

# Utilizando reduce() com objetos

Agora imagine que queremos somar o valor de todos os produtos da loja.

## Exemplo:

```
const valorTotal = produtos.reduce((acumulador, produto) => {
  return acumulador + produto.preco;
}, 0);

console.log(valorTotal);
```

## Resultado:

```
3370
```

## Explicação

O `reduce()` percorreu todos os objetos da lista somando o preço de cada produto até gerar um único valor final.

---

# Conclusão

Os métodos `map()`, `filter()` e `reduce()` são extremamente importantes no JavaScript moderno.

Dominar esses métodos é essencial para trabalhar com manipulação de arrays e objetos em JavaScript.

Espero que essas expliacações tenham ajudado vocês.
