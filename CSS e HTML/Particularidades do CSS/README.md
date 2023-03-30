# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Particularidades do CSS

- [Como criar um link com uma âncora](#como-criar-um-link-com-uma-%C3%A2ncora "Como criar um link com uma âncora")

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

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--particularidades-do-css "Subir para o topo")

---