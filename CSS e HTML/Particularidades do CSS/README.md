# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Particularidades do CSS

- [Impedir o uso de seleção de texto dentro do componente](#impedir-o-uso-de-sele%C3%A7%C3%A3o-de-texto-dentro-do-componente "Impedir o uso de seleção de texto dentro do componente")

---

## Impedir o uso de seleção de texto dentro do componente

Para impedir a seleção de texto dentro de um componente em ReactJS, você pode adicionar algumas propriedades de estilo CSS no componente:

```css
/* desabilita a seleção de texto */
-webkit-user-select: none; 
-moz-user-select: none;
-ms-user-select: none;
user-select: none;
```

Em seguida, adicione essas propriedades de estilo no componente em ReactJS:

```jsx
import React from 'react';

function MyComponent() {
  return (
    <div style={{ 
        /* desabilita a seleção de texto */ 
        WebkitUserSelect: 'none',
        MozUserSelect: 'none',
        MsUserSelect: 'none',
        userSelect: 'none',
      }}>
      Seu conteúdo aqui...
    </div>
  );
}

export default MyComponent;
```

Dessa forma, a seleção de texto será impedida dentro do componente.

> Há outra forma de impedir a seleção de texto dentro do componente?

Sim, há outra forma de impedir a seleção de texto dentro de um componente React. Você pode utilizar a propriedade CSS `user-select` para controlar a seleção de texto dentro do elemento. Para impedir completamente a seleção de texto, você pode definir o valor de `user-select` como `none` no estilo do elemento:

```javascript
function App() {
  return (
    <div style={{ userSelect: 'none' }}>
      {/* conteúdo da sua aplicação */}
    </div>
  );
}
```

Isso impedirá que o usuário selecione qualquer texto dentro do elemento, incluindo em sub-elementos. Se quiser permitir a seleção de texto em sub-elementos, você pode definir o valor de `user-select` como `none` no estilo do elemento principal e como `text` nos sub-elementos que deseja permitir a seleção de texto:

```javascript
function App() {
  return (
    <div style={{ userSelect: 'none' }}>
      <div style={{ userSelect: 'text' }}>
        {/* conteúdo da sua aplicação que permite seleção de texto */}
      </div>
      <div>
        {/* conteúdo da sua aplicação que não permite seleção de texto */}
      </div>
    </div>
  );
}
```

Dessa forma, somente o conteúdo dentro do sub-elemento que tem o valor de `user-select` como `text` poderá ser selecionado.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--particularidades-do-css "Subir para o topo")

---