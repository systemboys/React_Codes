# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes")

## Particularidades do CSS

### *Sumário*

- [Impedir o uso de seleção de texto dentro do componente](#impedir-o-uso-de-sele%C3%A7%C3%A3o-de-texto-dentro-do-componente "Impedir o uso de seleção de texto dentro do componente")
- [Guia Rápido de Consultas de Mídia em CSS para Design Responsivo](#guia-r%C3%A1pido-de-consultas-de-m%C3%ADdia-em-css-para-design-responsivo "Guia Rápido de Consultas de Mídia em CSS para Design Responsivo")

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

```jsx
function App() {
  return (
    <div style={{ userSelect: 'none' }}>
      {/* conteúdo da sua aplicação */}
    </div>
  );
}
```

Isso impedirá que o usuário selecione qualquer texto dentro do elemento, incluindo em sub-elementos. Se quiser permitir a seleção de texto em sub-elementos, você pode definir o valor de `user-select` como `none` no estilo do elemento principal e como `text` nos sub-elementos que deseja permitir a seleção de texto:

```jsx
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
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

## Guia Rápido de Consultas de Mídia em CSS para Design Responsivo

Este é um conjunto de consultas de mídia (media queries) que se destinam a aplicar estilos CSS específicos a diferentes tamanhos de tela. As consultas de mídia são usadas em desenvolvimento web responsivo para adaptar o layout e o design da página para diferentes dispositivos e tamanhos de tela.

```css
/* Mobile */
@media (max-width: 480px) {}

/* Extra small devices */
@media (min-width: 481px) and (max-width: 767px) {}

/* Small tablets */
@media (min-width: 768px) and (max-width: 991px) {}

/* Large tablets/laptops */
@media (min-width: 992px) and (max-width: 1199px) {}

/* Desktop */
@media (min-width: 1200px) and (max-width: 1919px) {}

/* Extra large screens */
@media (min-width: 1920px) {}
```

1. **Mobile (480px ou menos)**: Estilos para dispositivos móveis com largura de tela de 480 pixels ou menos.
2. **Extra small devices (481px a 767px)**: Estilos para dispositivos pequenos como smartphones em orientação paisagem.
3. **Small tablets (768px a 991px)**: Estilos para tablets pequenos e dispositivos de tamanho similar.
4. **Large tablets/laptops (992px a 1199px)**: Estilos para tablets maiores e laptops.
5. **Desktop (1200px a 1919px)**: Estilos para monitores de desktop comuns.
6. **Extra large screens (1920px ou mais)**: Estilos para monitores de tela grande, como alguns monitores de alta resolução e TVs.

Essas consultas de mídia permitem que você ajuste o layout, o tamanho do texto, as imagens e outros aspectos visuais do seu site para proporcionar uma experiência de usuário otimizada em diferentes dispositivos e tamanhos de tela.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---