# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Funções

- [Função simples](#fun%C3%A7%C3%A3o-simples "Função simples")
- [Passar uma propriedade de um elemento para uma arrow function](#passar-uma-propriedade-de-um-elemento-para-uma-arrow-function "Passar uma propriedade de um elemento para uma arrow function")

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

## Passar uma propriedade de um elemento para uma arrow function

Para executar uma arrow function que recebe a propriedade de um elemento quando um evento onClick é disparado, você pode definir a arrow function como uma função que recebe o evento e o elemento como seus parâmetros, e em seguida passá-la para a propriedade onClick do elemento.

Por exemplo, suponha que você tenha um botão com um id definido e deseja executar uma arrow function que recebe o id do botão quando ele é clicado. Você pode fazer o seguinte:

```javascript
// Evento do onClick={}
const handleClick = (event, id) => {
    console.log(`O evento do onClick no botão com o valor ${id} definido no segundo parâmentro arrow function handleClick() foi clicado.`);
};
```

Neste exemplo, a arrow function handleClick é definida para receber o evento e o id do elemento como seus parâmetros. O seu componente renderiza um botão com o id definido e passa a arrow function handleClick para a propriedade onClick do botão, juntamente com o id do botão.

Quando o botão é clicado, a arrow function é executada com o evento e o id do botão como seus parâmetros, permitindo que você acesse a propriedade do elemento dentro da função.

```javascript
return <button onClick={(event) => handleClick(event, "123")}>Clique aqui</button>;
```

> O `onClick={}` envia o evento, e no segundo parâmetro de `handleClick(event, "123")` será definido o valor a ser enviado. O resultado do exemplo

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#assunto "Subir para o topo")

------------