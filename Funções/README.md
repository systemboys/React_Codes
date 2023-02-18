# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Funções

- [Função simples](#fun%C3%A7%C3%A3o-simples "Função simples")
- [Passando um valor para a Arrow Function](#passando-um-valor-para-a-arrow-function "Passando um valor para a Arrow Function")

------------

## Função simples

Quando a função é acionada a partir de um click do usuário, é recomendável colocar o prefix `handle` e em seguida o nome de sua função em `CamelCase`, onde é uma denominação em inglês para a prática de escrever as palavras compostas ou frases, onde cada palavra é iniciada com maiúsculas e unidas sem espaços. Exemplo: `handleYourFunction() {...}`.

```javascript
function handleYourFunction() {
    alert('Helo World!');
};
```

Outra forma em uma constante:

```javascript
const handleYourFunction = () => {
    alert('Helo World!');
};
```

Sua função pode ser executada por exemplo, em um elemento HTML escrita da seguinte forma na propriedade `onClick={}`:

```javascript
 onClick={handleYourFunction}
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--fun%C3%A7%C3%B5es "Subir para o topo")

------------

## Passando um valor para a Arrow Function

A Arrow Function que recebe o evento do onClick:

```javascript
// Evento do onClick={}
const handleClick = (event, id) => {
    console.log(`O botão com o id ${id} foi clicado.`);
};
```

> O resultado deste exemplo será executado no `console`: `O botão com o id 123 foi clicado.`!

O valor passado pelo `onClick={}` no elemento HTML:

```javascript
onClick={(event) => handleClick(event, "123")}
```

> O `onClick={}` envia o evento, no segundo parâmetro de `handleClick(event, "123")` será definido o valor a ser enviado.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#assunto "Subir para o topo")

------------