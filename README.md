<h1 align="center">
    <img alt="Image Trybe" src="https://i.ibb.co/d4W2x4g/trybe.png" width="400px" />
</h1>

<h3 align="center">
  Exercício 8-2: JS_ES6 - Higher Order Functions--map, filter - Concluído o/ o/ o/ :star:
</h3>

<blockquote align="center">“Quanto mais você estuda, mais aprende e se aproxima de realizar seu sonhos!”</blockquote>

<h1></h1>

<p align="center">

  <a href="https://www.linkedin.com/in/eduardosouzaprogrammer/">
    <img alt="Made by Eduardo Souza" src="https://img.shields.io/badge/made%20by-Edu%20Souza-%23F8952D">
  </a>&nbsp;

 <a href="https://edusouza-programmer.github.io/">
<img alt="Github page Edu Souza " src="https://img.shields.io/badge/Github%20page-Edu_Souza-orange">
</a>&nbsp;

  <a href="LICENSE" >
    <img alt="License" src="https://img.shields.io/badge/license-MIT-%23F8952D">
  </a>

</p>

<p align="center">
  <a href="#rocket-Sobre-o-Exercício">Sobre o Exercício</a>&nbsp;&nbsp;|&nbsp;&nbsp;
  <a href="#postbox-Entrega">Entrega</a>&nbsp;&nbsp;|&nbsp;&nbsp;
  <a href="#unlock-Licença">Licença</a>
</p>

# :rocket: Sobre o Exercício

Nos exercícios a seguir, você trabalhará com uma estrutura de dados representando uma lista de livros, contendo informações como nome do livro, gênero, pessoa autora do livro e data de lançamento.
Sua solução só será considerada correta se todos os asserts do arquivo forem executados sem erros. No Visual Studio Code, você pode executar o código do exemplo clicando com o botão direito e escolhando a opção Run Code.

# :postbox: Entrega

### :clipboard: Sumário

- <p><a href="#1"> :pushpin: 1.</a> Crie um array com strings no formato NOME_DO_LIVRO - GÊNERO_DO_LIVRO - NOME_DA_PESSOA_AUTORA;</p>

- <p><a href="#2"> :pushpin: 2.</a> Construa um array de objetos a partir do array de livros. Cada objeto deve conter uma propriedade author, com o nome da pessoa autora do livro, e uma propriedade age com a idade dessa pessoa quando o livro foi lançado. O array deve ser ordenado por idade, ou seja, da pessoa mais jovem para a mais velha considerando suas idades quando o livro foi lançado;</p>

- <p><a href="#3"> :pushpin: 3.</a> Crie um array com todos os objetos que possuem gênero ficção científica ou fantasia;</p>

- <p><a href="#4"> :pushpin: 4.</a> Crie um array ordenado pelos livros com mais de 60 anos de publicação e ordene-o pelo livro mais velho;</p>

- <p><a href="#5"> :pushpin: 5.</a> Desafio: O modelo boxer - Adicione bordas, Margem e Espaçamento;</p>

- <p><a href="#6"> :pushpin: 6.</a> Desafio: O modelo boxer - Adicione bordas, Margem e Espaçamento;</p>

- <p><a href="#7"> :pushpin: 7.</a> Desafio: O modelo boxer - Adicione bordas, Margem e Espaçamento;</p>

## :books: Exercícios

### 1°

Crie um array com strings no formato NOME_DO_LIVRO - GÊNERO_DO_LIVRO - NOME_DA_PESSOA_AUTORA.

#### Resposta:

<details>
 <summary> :pencil2: Código Javascript</summary>

```js
const assert = require("assert");

const books = [
	{
		id: 1,
		name: "As Crônicas de Gelo e Fogo",
		genre: "Fantasia",
		author: {
			name: "George R. R. Martin",
			birthYear: 1948,
		},
		releaseYear: 1991,
	},
	{
		id: 2,
		name: "O Senhor dos Anéis",
		genre: "Fantasia",
		author: {
			name: "J. R. R. Tolkien",
			birthYear: 1892,
		},
		releaseYear: 1954,
	},
	{
		id: 3,
		name: "Fundação",
		genre: "Ficção Científica",
		author: {
			name: "Isaac Asimov",
			birthYear: 1920,
		},
		releaseYear: 1951,
	},
	{
		id: 4,
		name: "Duna",
		genre: "Ficção Científica",
		author: {
			name: "Frank Herbert",
			birthYear: 1920,
		},
		releaseYear: 1965,
	},
	{
		id: 5,
		name: "A Coisa",
		genre: "Terror",
		author: {
			name: "Stephen King",
			birthYear: 1947,
		},
		releaseYear: 1986,
	},
	{
		id: 6,
		name: "O Chamado de Cthulhu",
		genre: "Terror",
		author: {
			name: "H. P. Lovecraft",
			birthYear: 1890,
		},
		releaseYear: 1928,
	},
];

const expected_result = [
	"As Crônicas de Gelo e Fogo - Fantasia - George R. R. Martin",
	"O Senhor dos Anéis - Fantasia - J. R. R. Tolkien",
	"Fundação - Ficção Científica - Isaac Asimov",
	"Duna - Ficção Científica - Frank Herbert",
	"A Coisa - Terror - Stephen King",
	"O Chamado de Cthulhu - Terror - H. P. Lovecraft",
];

function formatedBookNames() {
	return books.map(
		(book) => `${book.name} - ${book.genre} - ${book.author.name}`
	);
}
// show
assert.deepStrictEqual(formatedBookNames(), expected_result);
```

</details>

<p align="right">
    <a href="#clipboard-Sumário">
    <img alt="Back Sumário" src="https://img.shields.io/badge/Back-Sum%C3%A1rio-orange">
  </a>
</p>

#

### 2°

Construa um array de objetos a partir do array de livros. Cada objeto deve conter uma propriedade author, com o nome da pessoa autora do livro, e uma propriedade age com a idade dessa pessoa quando o livro foi lançado. O array deve ser ordenado por idade, ou seja, da pessoa mais jovem para a mais velha considerando suas idades quando o livro foi lançado.

#### Resposta:

<details>
 <summary> :pencil2: Código Javascript</summary>

```js
const assert = require("assert");

const books = [
	{
		id: 1,
		name: "As Crônicas de Gelo e Fogo",
		genre: "Fantasia",
		author: {
			name: "George R. R. Martin",
			birthYear: 1948,
		},
		releaseYear: 1991,
	},
	{
		id: 2,
		name: "O Senhor dos Anéis",
		genre: "Fantasia",
		author: {
			name: "J. R. R. Tolkien",
			birthYear: 1892,
		},
		releaseYear: 1954,
	},
	{
		id: 3,
		name: "Fundação",
		genre: "Ficção Científica",
		author: {
			name: "Isaac Asimov",
			birthYear: 1920,
		},
		releaseYear: 1951,
	},
	{
		id: 4,
		name: "Duna",
		genre: "Ficção Científica",
		author: {
			name: "Frank Herbert",
			birthYear: 1920,
		},
		releaseYear: 1965,
	},
	{
		id: 5,
		name: "A Coisa",
		genre: "Terror",
		author: {
			name: "Stephen King",
			birthYear: 1947,
		},
		releaseYear: 1986,
	},
	{
		id: 6,
		name: "O Chamado de Cthulhu",
		genre: "Terror",
		author: {
			name: "H. P. Lovecraft",
			birthYear: 1890,
		},
		releaseYear: 1928,
	},
];

const expected_result = [
	{
		age: 31,
		author: "Isaac Asimov",
	},
	{
		age: 38,
		author: "H. P. Lovecraft",
	},
	{
		age: 39,
		author: "Stephen King",
	},
	{
		age: 43,
		author: "George R. R. Martin",
	},
	{
		age: 45,
		author: "Frank Herbert",
	},
	{
		age: 62,
		author: "J. R. R. Tolkien",
	},
];

function nameAndAge() {
	return books
		.map((book) => ({
			author: book.author.name,
			age: book.releaseYear - book.author.birthYear,
		}))
		.sort(({ age: ageA }, { age: ageB }) => ageA - ageB);
}

assert.deepEqual(nameAndAge(), expected_result);
```

</details>

<p align="right">
    <a href="#clipboard-Sumário">
    <img alt="Back Sumário" src="https://img.shields.io/badge/Back-Sum%C3%A1rio-orange">
  </a>
</p>

#

### 3°

Crie um array com todos os objetos que possuem gênero ficção científica ou fantasia.

#### Resposta:

<details>
 <summary> :pencil2: Código Javascript</summary>

```js
const assert = require("assert");

const books = [
	{
		id: 1,
		name: "As Crônicas de Gelo e Fogo",
		genre: "Fantasia",
		author: {
			name: "George R. R. Martin",
			birthYear: 1948,
		},
		releaseYear: 1991,
	},
	{
		id: 2,
		name: "O Senhor dos Anéis",
		genre: "Fantasia",
		author: {
			name: "J. R. R. Tolkien",
			birthYear: 1892,
		},
		releaseYear: 1954,
	},
	{
		id: 3,
		name: "Fundação",
		genre: "Ficção Científica",
		author: {
			name: "Isaac Asimov",
			birthYear: 1920,
		},
		releaseYear: 1951,
	},
	{
		id: 4,
		name: "Duna",
		genre: "Ficção Científica",
		author: {
			name: "Frank Herbert",
			birthYear: 1920,
		},
		releaseYear: 1965,
	},
	{
		id: 5,
		name: "A Coisa",
		genre: "Terror",
		author: {
			name: "Stephen King",
			birthYear: 1947,
		},
		releaseYear: 1986,
	},
	{
		id: 6,
		name: "O Chamado de Cthulhu",
		genre: "Terror",
		author: {
			name: "H. P. Lovecraft",
			birthYear: 1890,
		},
		releaseYear: 1928,
	},
];

const expected_result = [
	{
		id: 1,
		name: "As Crônicas de Gelo e Fogo",
		genre: "Fantasia",
		author: {
			name: "George R. R. Martin",
			birthYear: 1948,
		},
		releaseYear: 1991,
	},
	{
		id: 2,
		name: "O Senhor dos Anéis",
		genre: "Fantasia",
		author: {
			name: "J. R. R. Tolkien",
			birthYear: 1892,
		},
		releaseYear: 1954,
	},
	{
		id: 3,
		name: "Fundação",
		genre: "Ficção Científica",
		author: {
			name: "Isaac Asimov",
			birthYear: 1920,
		},
		releaseYear: 1951,
	},
	{
		id: 4,
		name: "Duna",
		genre: "Ficção Científica",
		author: {
			name: "Frank Herbert",
			birthYear: 1920,
		},
		releaseYear: 1965,
	},
];

function fantasyOrScienceFiction() {
	return books.filter(
		(book) => book.genre === "Ficção Científica" || book.genre === "Fantasia"
	);
}

assert.deepEqual(fantasyOrScienceFiction(), expected_result);
```

</details>

<p align="right">
    <a href="#clipboard-Sumário">
    <img alt="Back Sumário" src="https://img.shields.io/badge/Back-Sum%C3%A1rio-orange">
  </a>
</p>

#

### 4°

Crie um array ordenado pelos livros com mais de 60 anos de publicação e ordene-o pelo livro mais velho.

#### Resposta:

<details>
 <summary> :pencil2: Código Javascript</summary>

```js
const assert = require("assert");

const books = [
	{
		id: 1,
		name: "As Crônicas de Gelo e Fogo",
		genre: "Fantasia",
		author: {
			name: "George R. R. Martin",
			birthYear: 1948,
		},
		releaseYear: 1991,
	},
	{
		id: 2,
		name: "O Senhor dos Anéis",
		genre: "Fantasia",
		author: {
			name: "J. R. R. Tolkien",
			birthYear: 1892,
		},
		releaseYear: 1954,
	},
	{
		id: 3,
		name: "Fundação",
		genre: "Ficção Científica",
		author: {
			name: "Isaac Asimov",
			birthYear: 1920,
		},
		releaseYear: 1951,
	},
	{
		id: 4,
		name: "Duna",
		genre: "Ficção Científica",
		author: {
			name: "Frank Herbert",
			birthYear: 1920,
		},
		releaseYear: 1965,
	},
	{
		id: 5,
		name: "A Coisa",
		genre: "Terror",
		author: {
			name: "Stephen King",
			birthYear: 1947,
		},
		releaseYear: 1986,
	},
	{
		id: 6,
		name: "O Chamado de Cthulhu",
		genre: "Terror",
		author: {
			name: "H. P. Lovecraft",
			birthYear: 1890,
		},
		releaseYear: 1928,
	},
];

const expected_result = [
	{
		id: 6,
		name: "O Chamado de Cthulhu",
		genre: "Terror",
		author: { name: "H. P. Lovecraft", birthYear: 1890 },
		releaseYear: 1928,
	},
	{
		id: 3,
		name: "Fundação",
		genre: "Ficção Científica",
		author: { name: "Isaac Asimov", birthYear: 1920 },
		releaseYear: 1951,
	},
	{
		id: 2,
		name: "O Senhor dos Anéis",
		genre: "Fantasia",
		author: { name: "J. R. R. Tolkien", birthYear: 1892 },
		releaseYear: 1954,
	},
];

// array com livros mais 60 nos
// ordenar pelo o livro mais velho
function oldBooks() {
	const olderBookAge60 = new Date().getFullYear() - 60;
	return books
		.filter((book) => book.releaseYear < olderBookAge60)
		.sort(({ releaseYear: yearA }, { releaseYear: yearB }) => yearA - yearB);
}

assert.deepEqual(oldBooks(), expected_result);
```

</details>

<p align="right">
    <a href="#clipboard-Sumário">
    <img alt="Back Sumário" src="https://img.shields.io/badge/Back-Sum%C3%A1rio-orange">
  </a>
</p>

#

### 5°

#### Resposta:

<details>
 <summary> :pencil2: Código Javascript</summary>

```js

```

</details>

<p align="right">
    <a href="#clipboard-Sumário">
    <img alt="Back Sumário" src="https://img.shields.io/badge/Back-Sum%C3%A1rio-orange">
  </a>
</p>

#

### 6°

#### Resposta:

<details>
 <summary> :pencil2: Código Javascript</summary>

```js

```

</details>

<p align="right">
    <a href="#clipboard-Sumário">
    <img alt="Back Sumário" src="https://img.shields.io/badge/Back-Sum%C3%A1rio-orange">
  </a>
</p>

#

### 7°

#### Resposta:

<details>
 <summary> :pencil2: Código Javascript</summary>

```js

```

</details>

<p align="right">
    <a href="#clipboard-Sumário">
    <img alt="Back Sumário" src="https://img.shields.io/badge/Back-Sum%C3%A1rio-orange">
  </a>
</p>

## :unlock: Licença

Este projeto está licenciado sob a Licença MIT - consulte [LICENSE](https://opensource.org/licenses/MIT) para maiores detalhes.
