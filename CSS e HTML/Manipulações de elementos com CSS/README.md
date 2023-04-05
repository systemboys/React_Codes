# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Manipulações de elementos com CSS

- [`Transbordar` texto dentro de um elemento](#transbordar-texto-dentro-de-um-elemento "Transbordar texto dentro de um elemento")
- [Mudar a `imagem do plano de fundo` de um elemento](#mudar-a-imagem-do-plano-de-fundo-de-um-elemento "Mudar a imagem do plano de fundo de um elemento")

---

## Transbordar texto dentro de um elemento

[![Transbordar texto dentro de um elemento](https://github.com/systemboys/React_Codes/raw/main/CSS%20e%20HTML/Manipula%C3%A7%C3%B5es%20de%20elementos%20com%20CSS/images/Transbordar_texto_dentro_de_um_elemento.png "Transbordar texto dentro de um elemento")](https://github.com/systemboys/React_Codes/raw/main/CSS%20e%20HTML/Manipula%C3%A7%C3%B5es%20de%20elementos%20com%20CSS/images/Transbordar_texto_dentro_de_um_elemento.png "Transbordar texto dentro de um elemento")

Quando você precisa colocar um texto dentro de um elemento e o mesmo sai pela borda lateral direita.

Com essa regra no CSS, você pode por três pontinhos (Texto...) que serão distribuídos de acordo com a largura do elemento.

Sua class CSS

```css
.yourDiv {
  width: 120px;
  text-overflow: ellipsis;
  white-space: nowrap;
  overflow: hidden;
}
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--manipula%C3%A7%C3%B5es-de-elementos-com-css "Subir para o topo")

---

## Mudar a imagem do plano de fundo de um elemento

Este exemplo altera a imagem do plano de fundo de um objeto. A constante `element` recebe o nome de uma classe e, a condição abaixo após verificar a existência de um valor, e faz a lateração:

```javascript
const element = document.querySelector('.youClassName');
if (element) {
    element.style.backgroundImage = `url(${url})`;
}
```

> Neste exemplo, estamos selecionando o elemento que possui a classe `.youClassName` usando `document.querySelector` e definindo a imagem de plano de fundo usando `element.style.backgroundImage`. Certifique-se de substituir o seletor de classe pelo nome da sua classe específica.

Para mudar a cor de fundo de um elemento usando o mesmo script, você pode modificar o código substituindo `backgroundImage` pela cor desejada.

Aqui está o código atualizado para mudar a cor de fundo de um elemento com a classe `.youClassName`:

```javascript
const element = document.querySelector('.youClassName');
if (element) {
    element.style.backgroundColor = 'blue'; // Substitua "blue" pela cor desejada
}
```

Note que aqui estamos usando `element.style.backgroundColor` em vez de `element.style.backgroundImage` para definir a cor de fundo do elemento. Substitua `'blue'` pela cor desejada em formato de string. Você também pode definir a cor a partir de uma variável.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--manipula%C3%A7%C3%B5es-de-elementos-com-css "Subir para o topo")

---

