# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Funções

- [Função simples](#fun%C3%A7%C3%A3o-simples "Função simples")
- [Passar uma propriedade de um elemento para uma arrow function](#passar-uma-propriedade-de-um-elemento-para-uma-arrow-function "Passar uma propriedade de um elemento para uma arrow function")
- [PopUp com uma determinada URL passada via parâmetro](#popup-com-uma-determinada-url-passada-via-par%C3%A2metro "Popup com uma determinada URL passada via parâmetro")
- [PopUp passando além de uma URL, dimensões e centralizada](#popup-passando-al%C3%A9m-de-uma-url-dimens%C3%B5es-e-centralizada "PopUp passando além de uma URL, dimensões e centralizada")
- [Contar número de caracteres de uma string](#contar-n%C3%BAmero-de-caracteres-de-uma-string "Contar número de caracteres de uma string")
- [Capitalizando as palavras Capitalizando as palavras (ótimo para nomes de pessoas)](#capitalizando-as-palavras-%C3%B3timo-para-nomes-de-pessoas "Capitalizando as palavras Capitalizando as palavras (ótimo para nomes de pessoas)")
- [Capitalizar a primeira palavra de um parágrafo com exceções em ReactJS](#fun%C3%A7%C3%A3o-para-capitalizar-a-primeira-palavra-de-um-par%C3%A1grafo-com-exce%C3%A7%C3%B5es-em-reactjs "Capitalizar a primeira palavra de um parágrafo com exceções em ReactJS")
- [Transformando meses de 01 a 12 em Janeiro a Dezembro](#transformando-meses-de-01-a-12-em-janeiro-a-dezembro "Transformando meses de 01 a 12 em Janeiro a Dezembro")

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

## PopUp com uma determinada URL passada via parâmetro

Para abrir uma popup com uma determinada URL em um projeto em ReactJS, você pode usar o seguinte código:

```javascript
// PopUp simples.
function openPopup(url) {
  window.open(url, 'popup', 'width=600,height=600');
}

// Exemplo de uso.
openPopup('https://www.google.com');
```

Neste exemplo, a função `openPopup` recebe uma URL como parâmetro e utiliza o método `window.open` para abrir uma nova janela com a URL especificada. O segundo parâmetro da função `window.open` define o nome da janela (no caso, "popup"), e o terceiro parâmetro especifica as dimensões da janela. Você pode ajustar o tamanho de acordo com suas necessidades.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--fun%C3%A7%C3%B5es "Subir para o topo")

---

## PopUp passando além de uma URL, dimensões e centralizada

Você pode usar o método `window.open()` do JavaScript para abrir uma nova janela popup com uma determinada URL e dimensões. Para centralizar a janela na tela, você pode usar as dimensões da tela e as dimensões da janela para calcular a posição do canto superior esquerdo da janela. Aqui está um exemplo de código que faz isso:

```javascript
// PopUp simples centralizada.
function openPopup(url, width, height) {
  // Calcular a posição do canto superior esquerdo da janela para centralizá-la.
  const left = (screen.width - width) / 2;
  const top = (screen.height - height) / 2;

  // Abrir a janela popup com a URL e dimensões especificadas.
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

## Contar número de caracteres de uma string

Esta função recebe a o valor da string, conta os caracteres e retorna o valor referente à quantidade de caracteres.

```javascript
// Contar caracteres
function countCharacters(string) {
    const numberOfCharacters = string.length;
    return numberOfCharacters;
}
// Exemplo: countCharacters("Seu texto aqui.")
```

Para contar o número de caracteres de uma string em ReactJS, você pode simplesmente usar a propriedade `length` da string. Por exemplo, suponha que você tenha uma variável chamada "texto" que contém o texto que você deseja contar os caracteres, você pode obter o número de caracteres usando o seguinte código:

```javascript
const texto = "Exemplo de texto";
const numeroCaracteres = texto.length;
console.log(numeroCaracteres); // 16
```

Neste exemplo, a constante `numeroCaracteres` vai conter o número de caracteres do texto, que no caso é 16.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--fun%C3%A7%C3%B5es "Subir para o topo")

---

## Capitalizando as palavras (ótimo para nomes de pessoas)

Você pode criar uma nova função em seu componente React que capitalize as letras da string. Segue um exemplo:

```javascript
// Capitalizando as palavras.
function capitalize(str) {
  return str.replace(/\b\w/g, function (match) {
    return match.toUpperCase();
  });
}
```

Em seguida, você pode utilizá-la no seu campo de formulário da seguinte forma:

```javascript
<Form.Control
  type="text"
  size="sm"
  placeholder="Nome completo do cliente"
  value={full_name}
  onChange={(e) => setFull_name(capitalize(e.target.value))}
  ref={full_nameInputRef}
/>
```

Dessa forma, a função `capitalize()` será chamada sempre que houver uma mudança no valor do campo de formulário e a string digitada será capitalizada.

> ( ! ) Quero que ignore as seguintes palavras: "de", "do", "da", "dos", "uma", "umas", "um", "uns".

Para ignorar as palavras especificadas, você pode verificar se cada palavra está na lista de palavras ignoradas antes de capitalizá-la. Aqui está uma possível implementação da função:

```javascript
// Capitalizando as palavras.
function capitalizeWords(value) {
  const ignoredWords = ['de', 'do', 'da', 'dos', 'uma', 'umas', 'um', 'uns'];
  const words = value.split(' ');
  const capitalizedWords = words.map((word) => {
    if (ignoredWords.includes(word.toLowerCase())) {
      return word.toLowerCase();
    } else {
      return word.charAt(0).toUpperCase() + word.slice(1).toLowerCase();
    }
  });
  return capitalizedWords.join(' ');
}
```

Você pode usar essa função `capitalizeWords()` no seu componente React assim:

```javascript
<Form.Control
  type="text"
  size="sm"
  placeholder="Nome completo do cliente"
  value={full_name}
  onChange={(e) => setFull_name(capitalizeWords(e.target.value))}
  ref={full_nameInputRef}
/>
```

Para utilizar a função `capitalizeWords` em um elemento HTML, basta chamá-la passando a string desejada como parâmetro e envolver o resultado em um elemento que deseja aplicá-lo, como um `<h1>` por exemplo. Veja um exemplo:

```javascript
<h1>{capitalizeWords('este é um exemplo de título capitalizado')}</h1>
```

Isso irá renderizar o texto "Este é um Exemplo de Título Capitalizado" dentro de um elemento `<h1>`.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--fun%C3%A7%C3%B5es "Subir para o topo")

---

## Capitalizar a primeira palavra de um parágrafo com exceções em ReactJS

É possível usar um array para facilitar a inclusão de palavras em exceções no texto capitalizado. Aqui está o código que utiliza um array de palavras excepcionais:

```javascript
// Capitalizar a primeira palavra de um parágrafo com exceções.
function capitalizeFirstWord(text) {
  const lowercaseText = text.toLowerCase();
  const words = lowercaseText.split(' ');

  const exceptions = ['educação', 'maranhão'];

  const capitalizedWords = words.map((word, index) => {
    if (index === 0) {
      return word.charAt(0).toUpperCase() + word.slice(1);
    } else if (exceptions.includes(word)) {
      return word.toUpperCase();
    } else {
      return word;
    }
  });
  const capitalizedText = capitalizedWords.join(' ');
  return capitalizedText;
}

console.log(capitalizeFirstWord(yourParagraph));
```

As palavras excepcionais estão armazenadas no array `exceptions`. O código verifica se a palavra está contida nesse array usando `exceptions.includes(word)`. Dessa forma, você pode adicionar ou remover palavras no array `exceptions` de acordo com suas necessidades. O resultado continuará sendo apenas a capitalização da primeira palavra e a preservação das palavras excepcionais.

Este código em ReactJS tem como objetivo capitalizar a primeira palavra de um parágrafo, enquanto mantém as palavras em minúsculas, exceto por algumas exceções. Aqui está uma descrição passo a passo do código:

1. É definida a função `capitalizeFirstWord` que recebe um texto como parâmetro.
2. O texto é convertido para minúsculas usando o método `toLowerCase()`.
3. O texto é dividido em palavras usando o método `split(' ')`, que retorna um array de palavras.
4. É definido um array chamado `exceptions` que contém as palavras excepcionais que não serão convertidas para minúsculas.
5. O array de palavras é percorrido usando o método `map()`.
6. Para a primeira palavra (índice 0), a primeira letra é capitalizada usando `word.charAt(0).toUpperCase() + word.slice(1)`, que retorna a primeira letra em maiúscula concatenada com o restante da palavra em minúscula.
7. Para as palavras subsequentes, é verificado se a palavra está presente no array `exceptions` usando `exceptions.includes(word)`.
8. Se a palavra estiver no array de exceções, ela é mantida em maiúscula.
9. Caso contrário, a palavra é mantida em minúscula.
10. As palavras modificadas são armazenadas em um novo array chamado `capitalizedWords`.
11. O array `capitalizedWords` é juntado novamente em um texto usando o método `join(' ')`.
12. O texto final com a primeira palavra capitalizada e as exceções mantidas é retornado pela função `capitalizeFirstWord`.
13. No componente `App`, é definido um parágrafo como exemplo, onde todas as palavras estão em letras maiúsculas.
14. A função `capitalizeFirstWord` é chamada com o parágrafo como argumento, retornando o parágrafo modificado.
15. O parágrafo modificado é renderizado em um elemento `<p>`.

Esse código pode ser usado como referência para capitalizar a primeira palavra de um parágrafo e lidar com exceções de palavras específicas em seu projeto ReactJS.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--fun%C3%A7%C3%B5es "Subir para o topo")

---

## Transformando meses de 01 a 12 em Janeiro a Dezembro

Você pode criar uma função que receba o número do mês como argumento e retorne o nome do mês correspondente. Veja um exemplo:

```javascript
// Transformando meses de 01 a 12 em Janeiro a Dezembro
function getMonthName(month) {
  const monthNames = [
    "Janeiro", "Fevereiro", "Março", "Abril", 
    "Maio", "Junho", "Julho", "Agosto", 
    "Setembro", "Outubro", "Novembro", "Dezembro"
  ];
  return monthNames[month - 1];
}
```

Nesse exemplo, a função `getMonthName` recebe um número de mês (de 1 a 12) como argumento e retorna o nome do mês correspondente. O array `monthNames` contém os nomes dos meses em ordem, e a função usa o número do mês como índice para obter o nome correspondente do array. Note que a função subtrai 1 do número do mês, já que os arrays em JavaScript são indexados a partir de zero.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--fun%C3%A7%C3%B5es "Subir para o topo")

---