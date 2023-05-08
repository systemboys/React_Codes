# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / ReactJS: Anotações diversas de trechos úteis

[![Imagem 1](https://site.com/img/exemplo.png "Imagem 1")](http://link.com "Imagem 1")

- [Importando constantes de outros arquivos](#importando-constantes-de-outros-arquivos "Importando constantes de outros arquivos")

---

## Importando constantes de outros arquivos

Para exportar constantes de outros arquivos para seu componente, você precisa exportar a constante dentro do arquivo. Exemplo: Temos uma constante com o nome `baseUrl` no arquivo `primarySettings.js`, dessa forma:

```javascript
export const baseUrl = "https://www.meusite.com.br";
```

E então, no seu componente, você deve importar a constante `baseUrl` da seguinte forma:

```javascript
import { baseUrl } from '../../primarySettings.js';
```

E, finalmente, você pode utilizar a constante `baseUrl` em seu componente como no exemplo abaixo:

```javascript
<img src={`${baseUrl}/img/posts/${item.thumb}`} />
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#assunto "Subir para o topo")

---