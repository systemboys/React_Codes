# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Manipulações em ReactJS

[![Manipulações com ReactJS](https://github.com/systemboys/React_Codes/raw/main/Manipula%C3%A7%C3%B5es%20com%20ReactJS/images/Manipulacoes_com_ReactJS.png "Manipulações com ReactJS")](https://github.com/systemboys/React_Codes/raw/main/Manipula%C3%A7%C3%B5es%20com%20ReactJS/images/Manipulacoes_com_ReactJS.png "Manipulações com ReactJS")

- [Manipulação de URL em ReactJS](#manipula%C3%A7%C3%A3o-de-url-em-reactjs "Manipulação de URL em ReactJS")
- [Obtendo a query string em ReactJS usando react-router-dom](#obtendo-a-query-string-em-reactjs-usando-react-router-dom "Obtendo a query string em ReactJS usando react-router-dom")
- [Trabalhando com Tags](#trabalhando-com-tags "Trabalhando com Tags")

---

## Manipulação de URL em ReactJS

> Tenho a seguinte URL: http://localhost:3000/post/#post-1. Como faço para obter apenas os dados após o hashtag (#dados...) usando ReactJS?

Em uma aplicação React, você pode obter os dados após o hashtag utilizando o objeto `window.location.hash`. Por exemplo, para obter os dados após o hashtag na URL que você mencionou, você pode fazer o seguinte:

```javascript
const hash = window.location.hash.substr(1); // Remove o "#" do início da string.
console.log(hash); // Retorna "post-1".
```

O código acima obtém a string após o hashtag (no exemplo, "governador-do-maranhao-recebe-comitiva-de-colinas") e remove o "#" do início da string usando o método `substr(1)`. Em seguida, essa string pode ser usada como necessário em sua aplicação.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--manipula%C3%A7%C3%B5es-em-reactjs "Subir para o topo")

---

## Obtendo a query string em ReactJS usando react-router-dom

Em ReactJS, você pode obter a query string de uma URL usando a biblioteca `react-router-dom`. Essa biblioteca oferece recursos de roteamento para aplicativos React.

Para obter a query string em ReactJS usando o `react-router-dom`, você pode usar o componente `useLocation` fornecido pela biblioteca. O `useLocation` retorna um objeto de localização que contém informações sobre a URL atual, incluindo a query string.

Aqui está um exemplo de como você pode obter a query string em ReactJS:

```javascript
import { useLocation } from 'react-router-dom';

function MyComponent() {
  const location = useLocation();
  const queryParams = new URLSearchParams(location.search);
  
  // Exemplo: Obter o valor do parâmetro 'post'
  const postId = queryParams.get('post');
  
  // Resto do código...
}
```

Nesse exemplo, usamos o `useLocation` para obter o objeto de localização atual. Em seguida, criamos uma instância de `URLSearchParams` passando `location.search`, que é a string da query string da URL atual. Agora, podemos usar o método `get` do objeto `URLSearchParams` para obter o valor do parâmetro desejado, como 'post' no exemplo acima.

Lembre-se de que o `useLocation` só funcionará se o seu aplicativo estiver usando o `BrowserRouter` ou outro roteador fornecido pelo `react-router-dom`.

Certifique-se de ter instalado o `react-router-dom` usando o gerenciador de pacotes de sua preferência antes de usar o código acima.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--manipula%C3%A7%C3%B5es-em-reactjs "Subir para o topo")

---

## Trabalhando com Tags

Para transformar a string "tag1, tag2, tag3, tag4, tag5" em um array de strings ["tag1", "tag2", "tag3", "tag4", "tag5"], podemos usar o método `split()` para dividir a string em um array, utilizando a vírgula e o espaço como separadores, e em seguida usar o método `map()` para adicionar as aspas duplas em cada elemento do array resultante. Ficaria assim:

```javascript
// Transformar a string "tag1, tag2, tag3" em um array de strings ["tag1", "tag2", "tag3"]
const tagsPost = `${listPosts[0]?.tags}`;
const tagsArray = tagsPost.split(", ");
const tagsFormatted = tagsArray.map(tag => `${tag}`);
console.log(tagsFormatted);
```

O resultado será o array `["tag1", "tag2", "tag3", "tag4", "tag5"]`.

Exibindo no método `map()`:

Para renderizar os dados do array `tags` na lista HTML usando o método `map()` em ReactJS, você pode fazer o seguinte:

```javascript
<ul>
  {tagsFormatted.map((tag) => (
    <li key={tag}><Link to="/">{tag}</Link></li>
  ))}
</ul>
```

Explicação: 
- O método `map()` é usado para iterar sobre os elementos do array `tags` e criar um novo array de elementos JSX a partir dele. 
- Em cada iteração, é criado um novo elemento `<li>` contendo um link `<Link>` para a rota "/", com o texto da tag sendo o conteúdo do link.
- O atributo `key` é definido para cada elemento `<li>` para ajudar no desempenho e identificar cada elemento de maneira exclusiva. Neste caso, estamos usando a própria string da tag como a chave, mas você pode usar qualquer valor exclusivo e estável para identificar os elementos.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--manipula%C3%A7%C3%B5es-em-reactjs "Subir para o topo")

---