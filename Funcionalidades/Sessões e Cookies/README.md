# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Sessões e Cookies

[![Cookies](https://github.com/systemboys/React_Codes/raw/main/Sess%C3%B5es%20e%20Cookies/images/cookies-1.png "Cookies")](https://github.com/systemboys/React_Codes/raw/main/Sess%C3%B5es%20e%20Cookies/images/cookies-1.png "Cookies")

- [Sessões e Cookies com JavaScript](#sess%C3%B5es-e-cookies-com-javascript "Sessões e Cookies com JavaScript")

---

## Sessões e Cookies com JavaScript

Para criar uma sessão, você pode usar o objeto `sessionStorage` do JavaScript. Ele é um objeto global do navegador que armazena dados de sessão na memória enquanto a página permanece aberta. Os dados armazenados nesse objeto são acessíveis apenas pela mesma página ou outras páginas abertas no mesmo domínio.

Para armazenar um dado na sessão, você pode usar o método `setItem` do objeto `sessionStorage`, passando o nome da chave e o valor:

```jsx
// Armazena um valor na sessão.
sessionStorage.setItem('nome', 'João');
```

Para recuperar um valor da sessão, você pode usar o método `getItem` do objeto `sessionStorage`, passando o nome da chave:

```jsx
// Recupera um valor da sessão.
const nome = sessionStorage.getItem('nome');
console.log(nome); // Imprime 'João'.
```

Para criar um cookie, você pode usar a propriedade `document.cookie` do JavaScript. Ela permite definir, atualizar ou excluir cookies no navegador. Cookies são dados armazenados no computador do usuário, que podem ser acessados por qualquer página ou aplicativo no mesmo domínio.

Para definir um cookie, você pode definir a propriedade `document.cookie` com uma string contendo o nome da chave, o valor e algumas opções adicionais, como o tempo de expiração:

```jsx
// Define um cookie com o nome 'nome' e o valor 'João'
document.cookie = 'nome=João';

// Define um cookie com o nome 'idade' e o valor '30', expirando em 1 dia.
const umDiaEmMs = 24 * 60 * 60 * 1000;
const dataExpiracao = new Date(Date.now() + umDiaEmMs).toUTCString();
document.cookie = 'idade=30; expires=' + dataExpiracao;
```

Para recuperar um cookie, você pode acessar a propriedade `document.cookie`, que retorna uma string contendo todos os cookies definidos para o domínio atual. Em seguida, é possível filtrar essa string para encontrar o cookie desejado:

```jsx
// Recupera o valor do cookie 'nome'.
const cookies = document.cookie.split(';');
const nomeCookie = cookies.find(cookie => cookie.trim().startsWith('nome='));
const nome = nomeCookie ? nomeCookie.split('=')[1] : null;
console.log(nome); // Imprime 'João'.
```

> É importante lembrar que cookies e sessões são vulneráveis a ataques de roubo de informações e podem expor dados sensíveis do usuário. Por isso, é recomendável criptografar ou codificar esses dados antes de armazená-los no navegador ou no servidor.

Para apagar uma sessão ou um cookie, você pode utilizar a função `removeItem` do objeto `localStorage`. Por exemplo:

Para remover um cookie:

```jsx
localStorage.removeItem('nomeDoCookie');
```

Para remover uma sessão:

```jsx
localStorage.removeItem('nomeDaSessao');
```

> Observe que, para remover tanto um cookie quanto uma sessão, é preciso passar o mesmo nome que foi utilizado para criar o cookie ou sessão.

Para destruir todos os cookies ou sessões de uma vez, você pode utilizar o método `clear` do objeto `localStorage`.

Por exemplo:

```jsx
localStorage.clear();
```

> Observe que este método irá remover todos os itens armazenados no `localStorage`, incluindo todas as sessões e cookies que foram criados pelo seu aplicativo. Por isso, é importante tomar cuidado ao utilizar esse método para não remover dados importantes ou que outros aplicativos estejam utilizando.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--sess%C3%B5es-e-cookies "Subir para o topo")

---