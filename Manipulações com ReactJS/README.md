# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Manipulações em ReactJS

[![Imagem 1](https://site.com/img/exemplo.png "Imagem 1")](http://link.com "Imagem 1")

- [Link 1](https://site.com#anchor-link-1 "Link 1")

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
[(&uarr;) Subir](#assunto "Subir para o topo")

---