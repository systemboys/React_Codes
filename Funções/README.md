# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Funções

- [Função simples](#fun%C3%A7%C3%A3o-simples "Função simples")
- [Passar uma propriedade de um elemento para uma arrow function](#passar-uma-propriedade-de-um-elemento-para-uma-arrow-function "Passar uma propriedade de um elemento para uma arrow function")
- [Popup com uma determinada URL passada via parâmetro](#popup-com-uma-determinada-url-passada-via-par%C3%A2metro "Popup com uma determinada URL passada via parâmetro")
- [PopUp passando além de uma URL, dimensões e centralizada](#popup-passando-al%C3%A9m-de-uma-url-dimens%C3%B5es-e-centralizada "PopUp passando além de uma URL, dimensões e centralizada")

---

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

---

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

> O `onClick={}` envia o evento, e no segundo parâmetro de `handleClick(event, "123")` será definido o valor a ser enviado. O resultado deste exemplo é exibido no `console`.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--fun%C3%A7%C3%B5es "Subir para o topo")

---

## Popup com uma determinada URL passada via parâmetro

Para abrir uma popup com uma determinada URL em um projeto em ReactJS, você pode usar o seguinte código:

```javascript
function openPopup(url) {
  window.open(url, 'popup', 'width=600,height=600');
}

// Exemplo de uso
openPopup('https://www.google.com');
```

Neste exemplo, a função `openPopup` recebe uma URL como parâmetro e utiliza o método `window.open` para abrir uma nova janela com a URL especificada. O segundo parâmetro da função `window.open` define o nome da janela (no caso, "popup"), e o terceiro parâmetro especifica as dimensões da janela. Você pode ajustar o tamanho de acordo com suas necessidades.

## PopUp passando além de uma URL, dimensões e centralizada

Você pode usar o método `window.open()` do JavaScript para abrir uma nova janela popup com uma determinada URL e dimensões. Para centralizar a janela na tela, você pode usar as dimensões da tela e as dimensões da janela para calcular a posição do canto superior esquerdo da janela. Aqui está um exemplo de código que faz isso:

```javascript
function openPopup(url, width, height) {
  // calcula a posição do canto superior esquerdo da janela para centralizá-la
  const left = (screen.width - width) / 2;
  const top = (screen.height - height) / 2;

  // abre a janela popup com a URL e dimensões especificadas
  window.open(url, "", `width=${width}, height=${height}, left=${left}, top=${top}`);
}
```

Para usar essa função em seu projeto React, basta chamá-la em algum evento de um elemento da interface do usuário, por exemplo:

```javascript
<button onClick={() => openPopup("https://www.google.com", 800, 600)}>Abrir popup</button>
```

Este exemplo criará um botão que, quando clicado, abrirá uma janela popup com a URL "https://www.google.com" e as dimensões 800x600, centralizadas na tela.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--fun%C3%A7%C3%B5es "Subir para o topo")

---