# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Manipulações de elementos com JavaScript

- [Elemento com várias classes, como selecioná-lo](#elemento-com-v%C3%A1rias-classes-como-selecion%C3%A1-lo "Elemento com várias classes, como selecioná-lo")

---

## Elemento com várias classes, como selecioná-lo

Para remover uma div com várias classes, você pode usar o método `querySelector` do JavaScript para selecionar o elemento com base em suas classes. O código abaixo irá selecionar o primeiro elemento com a classe especificada e removê-lo do DOM:

```javascript
const divToRemove = document.querySelector(".fenestra-taskbar-button.mx-1.btn.active.btn-outline-primary");
divToRemove.parentNode.removeChild(divToRemove);
```

Este código encontra o elemento que possui todas as classes especificadas e o armazena na variável `divToRemove`. Em seguida, ele remove o elemento do DOM usando o método `removeChild` do elemento pai (`parentNode`) do elemento selecionado.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--manipula%C3%A7%C3%B5es-de-elementos-com-javascript "Subir para o topo")

---