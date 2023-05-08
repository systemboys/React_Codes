# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Manipulações em ReactJS

[![Manipulações com ReactJS](https://github.com/systemboys/React_Codes/raw/main/Manipula%C3%A7%C3%B5es%20com%20ReactJS/images/Manipulacoes_com_ReactJS.png "Manipulações com ReactJS")](https://github.com/systemboys/React_Codes/raw/main/Manipula%C3%A7%C3%B5es%20com%20ReactJS/images/Manipulacoes_com_ReactJS.png "Manipulações com ReactJS")

- [Manipulação de URL em ReactJS](#manipula%C3%A7%C3%A3o-de-url-em-reactjs "Manipulação de URL em ReactJS")

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