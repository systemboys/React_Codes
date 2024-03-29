# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes")

## Anotações diversas de trechos úteis

[![React Coding](https://github.com/systemboys/React_Codes/blob/main/ReactJS%20-%20Anota%C3%A7%C3%B5es%20diversas%20de%20trechos%20%C3%BAteis/images/React_coding.png?raw=true "React Coding")](https://github.com/systemboys/React_Codes/blob/main/ReactJS%20-%20Anota%C3%A7%C3%B5es%20diversas%20de%20trechos%20%C3%BAteis/images/React_coding.png?raw=true "React Coding")

### *Sumário*

- [Importando constantes de outros arquivos](#importando-constantes-de-outros-arquivos "Importando constantes de outros arquivos")

---

## Importando constantes de outros arquivos

Para exportar constantes de outros arquivos para seu componente, você precisa exportar a constante dentro do arquivo. Exemplo: Temos uma constante com o nome `baseUrl` no arquivo `primarySettings.js`, dessa forma:

```jsx
export const baseUrl = "https://www.meusite.com.br";
```

E então, no seu componente, você deve importar a constante `baseUrl` da seguinte forma:

```jsx
import { baseUrl } from '../../primarySettings.js';
```

E, finalmente, você pode utilizar a constante `baseUrl` em seu componente como no exemplo abaixo:

```jsx
<img src={`${baseUrl}/img/posts/${item.thumb}`} />
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---