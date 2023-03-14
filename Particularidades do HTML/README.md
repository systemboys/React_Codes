# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Particularidades do HTML

- [Como criar um link com uma âncora](#link-do-texto-de-comeco "Como criar um link com uma âncora")

---

## Como criar um link com uma âncora

[![Imagem de exemplo](https://site.com/img/exemplo.png "Imagem de exemplo")](http://link.com "Imagem de exemplo")

Para criar um link com uma âncora em HTML, você pode usar a tag `<a>` com o atributo `href` apontando para a seção que você deseja linkar usando o valor do atributo `id` da tag correspondente à seção. Por exemplo:

```html
<a href="#secao-1">Ir para a seção 1</a>

...

<section id="secao-1">
  <h2>Seção 1</h2>
  <p>Conteúdo da seção 1.</p>
</section>
```

Nesse exemplo, o link "Ir para a seção 1" aponta para a seção com o `id` "secao-1". Quando o link é clicado, a página rola até a seção correspondente.

Você pode também usar o atributo `target` para especificar como o link deve ser aberto. Por exemplo, para abrir o link em uma nova janela, você pode usar `target="_blank"`.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#particularidades-do-html "Subir para o topo")

---