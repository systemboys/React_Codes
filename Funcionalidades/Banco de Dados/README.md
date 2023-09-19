# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Banco de Dados

> Configurações e instalações.

- [Conectar Banco de Dados `MySQL` com ORM `PRISMA`](#conectar-banco-de-dados-mysql-com-orm-prisma "Conectar Banco de Dados MySQL com ORM PRISMA")
    - [Criar um `novo projeto` e iniciar o servidor](#criar-um-novo-projeto-e-iniciar-o-servidor "Criar um novo projeto e iniciar o servidor")
    - [Instalar o PRISMA](#instalar-o-prisma "Instalar o PRISMA")
    - [Configurar o arquivo `.env`](#configurar-o-arquivo-env "Configurar o arquivo .env")
    - [Configurar no arquivo `./prisma/schema.prisma` o trecho de codigo](#configurar-no-arquivo-prismaschemaprisma-o-trecho-de-codigo "Configurar no arquivo ./prisma/schema.prisma o trecho de codigo")
    - [Escrevendo o model no arquivo `./prisma/schema.prisma`](#escrevendo-o-model-no-arquivo-prismaschemaprisma "Escrevendo o model no arquivo prisma/schema.prisma")
    - [Criar o arquivo `./src/prisma.ts` e configure o seguinte código](#criar-o-arquivo-srcprismats-e-configure-o-seguinte-c%C3%B3digo "Criar o arquivo src/prisma.ts e configure o seguinte código")
    - [Criar o arquivo `./src/server.ts` e configure o seguinte código](#criar-o-arquivo-srcserverts-e-configure-o-seguinte-c%C3%B3digo "Criar o arquivo src/server.ts e configure o seguinte código")
    - [Criar e configurar o arquivo `./src/routes.ts`](#criar-e-configurar-o-arquivo-srcroutests "Criar e configurar o arquivo src/routes.ts")
    - [Utilização do `Insomnia` para leitura, gravação, atualização e delete](#utiliza%C3%A7%C3%A3o-do-insomnia-para-leitura-grava%C3%A7%C3%A3o-atualiza%C3%A7%C3%A3o-e-delete "Utilização do Insomnia para leitura, gravação, atualização e delete")
    - [`Recriar instâncias` nos módulos](#recriar-inst%C3%A2ncias-nos-m%C3%B3dulos "Recriar instâncias nos módulos")

---

> Consultas em componentes de função.

- [`Listar itens` da `tabela` no seu componente](#listar-itens-da-tabela-no-seu-componente "Listar itens da tabela no seu componente")
    - [Instalações necessárias](#instala%C3%A7%C3%B5es-necess%C3%A1rias "Instalações necessárias")
    - [Listar os itens no seu componente (`importação da API`)](#listar-os-itens-no-seu-componente-importa%C3%A7%C3%A3o-da-api "Listar os itens no seu componente (importação da API)")
      - [Trazer `resultados aleatórios` na lista](#trazer-resultados-aleat%C3%B3rios-na-lista "Trazer resultados aleatórios na lista")
    - [Listar 1 registro a partir do ID](#listar-1-registro-a-partir-do-id "Listar 1 registro a partir do ID")
        - [Exemplo 1, Onde iremos mudar o plano de fundo de um objeto](#listar-1-registro-a-partir-do-id-exemplo-1 "Exemplo 1, Onde iremos mudar o plano de fundo de um objeto")
        - [Exemplo 2, Onde seu resultado é colocado em outra rota](#listar-1-registro-a-partir-do-id-exemplo-2 "Exemplo 2, Onde seu resultado é colocado em outra rota")
        - [Exemplo 3, Onde uma função obtem o registro a partir do ID](#listar-1-registro-a-partir-do-id-exemplo-3 "Exemplo 3, Onde uma função obtem o registro a partir do ID")
- [`Atualizar` um registro `a partir do ID`](#atualizar-um-registro-a-partir-do-id "Atualizar um registro a partir do ID")
- [Gravar novo registro](#gravar-novo-registro "Gravar novo registro")
    - [Exemplo 1, onde é gravado um registro sem condições](#gravar-novo-registro-exemplo-1 "Exemplo 1, onde é gravado um registro sem condições")

---

> Consultas em componentes de classe.

- [Consulta com o PRISMA em um compoente classe](#consulta-com-o-prisma-em-um-compoente-classe "Consulta com o PRISMA em um compoente classe")
- [Listar em componentes classe](#listar-em-componentes-classe "Listar em componentes classe")
- [Configurando uma rota dentro de um componente de classe em React com definição de array](#configurando-uma-rota-dentro-de-um-componente-de-classe-em-react "Configurando uma rota dentro de um componente de classe em React com definição de array")

---

> Algumas dicas e resoluções úteis.

- [Formatação de Dados da API em um Array no Formato Específico (`JSON`)](#formata%C3%A7%C3%A3o-de-dados-da-api-em-um-array-no-formato-espec%C3%ADfico-json "Formatação de Dados da API em um Array no Formato Específico (JSON)")
  > **( i )** Serve para todos os compoentes independetemente de ser classe, função ou constante!
- [Obtendo registros com limite e paginação na rota](#obtendo-registros-com-limite-e-pagina%C3%A7%C3%A3o-na-rota "Obtendo registros com limite e paginação na rota")
  > **( i )** Essa configuração deve ser feita na sua rota!
- [`Correção do Carrossel` e Botão de Passador em Componente React](#corre%C3%A7%C3%A3o-do-carrossel-e-bot%C3%A3o-de-passador-em-componente-react "Correção do Carrossel e Botão de Passador em Componente React")
  > **( i )** Esta correção funcionou no componente ` <Swiper></Swiper>` que apresentava problemas ao exibir os itens!
- [Resolvendo Problemas de Carregamento Tardio de Dados em Componentes React com API](#resolvendo-problemas-de-carregamento-tardio-de-dados-em-componentes-react-com-api "Resolvendo Problemas de Carregamento Tardio de Dados em Componentes React com API")
  > **( i )** Isso reflete a natureza do problema que você está enfrentando e a solução proposta para garantir que os dados estejam prontos antes da renderização do componente React.
- [Como Inicializar uma `DataTable` com Dados de uma `API` no ReactJS](#como-inicializar-uma-datatable-com-dados-de-uma-api-no-reactjs "Como Inicializar uma DataTable com Dados de uma API no ReactJS")
  > **( i )** Neste guia, mostramos como usar o ReactJS para buscar dados de uma API e inicializar uma DataTable somente após os dados terem sido carregados  com sucesso. Isso garante que a DataTable funcione corretamente e evita  problemas de dados vazios ou inexistentes.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--banco-de-dados "Subir para o topo")

---

## Conectar Banco de Dados MySQL com ORM PRISMA

### Criar um novo projeto e iniciar o servidor:

> Crie um novo projeto com o NPM fora do diretório do seu projeto o qual deseja conectá-lo ao banco de dados. Você irá criar uma API para conectar seu projeto!

Crie um diretório para a API e inicie o Git:

```bash
npm init -y
```

Instalar o Express:

```bash
npm i express @types/express
```

Instalar o TypeScript:

```bash
npm install typescript ts-node @types/node --save-dev
```

Iniciar TypeScript, executar o comando `npx tsc --init` para criar um novo arquivo `tsconfig.json` em no projeto TypeScript:

```bash
npx tsc --init
```

Mudar o valor do "target": "es2016" para "es2020" no arquivo `./tsconfig.json`:

```jsx
/* Language and Environment */
"target": "es2020", /* Set the JavaScript language version for emitted JavaScript and include compatible library declarations. */
```

### Instalar o PRISMA:

```bash
npm install prisma --save-dev
```

Instalar o Prisma Client no projeto com o seguinte comando:

```bash
npm install @prisma/client
```

Iniciar o PRISMA:

```bash
npx prisma init
```

### Configurar o arquivo `./.env`:

```jsx
DATABASE_URL="postgresql://yourUser:yourPassword@yourHost:5432/yourDataBase"
```

| Parâmetro | Descrição |
| :------------ | :------------ |
| postgresql | Tipo de banco de dados. |
| yourUser | Usuário de banco de dados. |
| yourPassword | Senha do banco de dados. |
| yourHost | Host de sua hospedagem. |
| 5432 | Porta utilizada para acessar. Obs.: Para acessar o MySQL no host de sua hospedagem, use a porta `3306`. |
| yourDataBase | Banco de dados. |

### Configurar no arquivo `./prisma/schema.prisma` o trecho de codigo:

> O valor de `provider` deve ser `mysql`, que é o tipo de banco de dados!

```jsx
datasource db {
  provider = "mysql"
  url      = env("DATABASE_URL")
}
```

Obter os modules:

```bash
npx prisma db pull
```

> O PRISMA irá obter a estrutura de todas as tabelas do seu banco de dados!

### Escrevendo o model no arquivo `./prisma/schema.prisma`:

```jsx
model admins {
  id           Int    @id @default(autoincrement())
  simple_field String @db.VarChar(255)
  external_id  Int
  date         DateTime @db.Date
  hour         DateTime @db.Time(0)
  text_field   String @db.Text
}
```

> Acima estão os campos mais comuns utilizados no MySQL!

Exemplo abaixo:

[![Print de uma execução no Db Pull](https://github.com/systemboys/React_Codes/raw/main/Funcionalidades/Banco%20de%20Dados/Prisma/npx_prisma_db_pull.png "Print de uma execução no Db Pull")](https://github.com/systemboys/React_Codes/raw/main/Funcionalidades/Banco%20de%20Dados/Prisma/npx_prisma_db_pull.png "Print de uma execução no Db Pull")

### Criar o arquivo `./src/prisma.ts` e configure o seguinte código:

```jsx
import { PrismaClient } from "@prisma/client";

export const prisma = new PrismaClient ({
    log: ['query'],
});
```

### Criar o arquivo `./src/server.ts` e configure o seguinte código dentro do ./src/:

```jsx
import express from 'express';
import { routes } from './routes';

const App = express();
const port = 3333;

App.use(express.json())
App.use(routes);
App.listen(3333, ()=>{
    console.log('Server is running on port "' + port + '"! 🔥');
});
```

Para habilitar o CORS no seu servidor Express, você pode usar a biblioteca cors. Para permitir qualquer origem, você pode passar `{ origin: '*' }` como opções para a função `cors()`.

Instalar o `CORS`:

```bash
npm install cors
```

Instalar o pacote de tipos do `CORS`:

```bash
npm install @types/cors
```

Modificar o seu arquivo `./src/server.ts` da seguinte forma:

```jsx
import express from 'express';
import cors from 'cors';
import { routes } from './routes';

const app = express();
const port = 3333;

app.use(cors({ origin: '*' }));
app.use(express.json());
app.use(routes);

app.listen(port, () => {
  console.log('Server is running on port "' + port + '"! 🔥');
});

```

A configuração acima permite que todas as solicitações de origens diferentes sejam aceitas. Você também pode especificar uma lista de origens permitidas, caso queira restringir o acesso a um conjunto específico de domínios. Para mais informações sobre como configurar o CORS em sua aplicação, consulte a documentação do pacote `cors` no npm.

> Com essa configuração, todas as requisições vindas de qualquer origem serão permitidas. Lembre-se que em produção, você deve configurar o CORS de forma mais restrita, permitindo somente as origens necessárias.

### Criar e configurar o arquivo `./src/routes.ts`:

```jsx
import express from "express";
import { prisma } from './prisma';

export const routes = express.Router();

// Selecionar dados na tabela "admins".
// Rota: '/admins'.
routes.get('/admins', async (req, res) => {
    const admins = await prisma.admins.findMany({
        orderBy: {
            id: 'desc'
        }
    });
    res.status(200).json(admins);
});

/* Consultar 'admins/:Number(level)', onde o nível é um determinado valor.
Essa rota deve conter o parâmentro específico. Exemplo: Api.get('/admins/2').then((res) => ... */

// Selecionar dados na tabela "admins", a partir do ID na coluna "level".
// Rota: '/admins/5'.
routes.get('/admins/:level', async (req, res) => {
    const { level } = req.params;
    const admins = await prisma.admins.findMany({
        where: {
            level: Number(level)
        },
        orderBy: {
            id: 'desc'
        }
    });
    res.status(200).json(admins);
});

// Inserir dados na tabela "admins".
// Rota: '/admins'.
routes.post('/admins', async (req, res) => {
    const {
        primary_email,
        username,
        password,
        full_name,
        level
    } = req.body;
    // Gravar na tabela
    const admins = await prisma.admins.create({
        data:{
            primary_email,
            username,
            password,
            full_name,
            level
        }
    });
    return res.status(201).json({ data:admins });
});
```

Instalar o TSX:

```bash
npm install tsx
```

No arquivo `./package.json` editar o script deixando como no exemplo abaixo:

```jsx
// ...
"script": {
    "dev": "tsx watch src/server.ts",
    "build": "tsup src",
    "start": "node dist/server.js"
}
// ...
```

Executar o `prisma generate`:

```bash
npx prisma generate
```

> Ao executar `npx prisma generate`, o Prisma lê o schema do seu banco de dados e gera o código do Prisma Client que você pode usar em seu aplicativo para acessar o banco de dados. Isso é necessário sempre que você faz alterações em seu schema ou quando você cria um novo projeto e precisa gerar o código inicial.

Execute o servidor NPM:

```bash
npm run dev
```

[![Server executando](https://github.com/systemboys/React_Codes/raw/main/Funcionalidades/Banco%20de%20Dados/Prisma/npm_run_dev.png "Server executando")](https://github.com/systemboys/React_Codes/raw/main/Funcionalidades/Banco%20de%20Dados/Prisma/npm_run_dev.png "Server executando")

### Utilização do `Insomnia` para leitura, gravação, atualização e delete.

Executar o GET para consultar os registros na tabela `admins` e gerar um `JSON` com o `Insomnia`:

[![Consultar os dados com o Insomnia](https://github.com/systemboys/React_Codes/raw/main/Funcionalidades/Banco%20de%20Dados/Prisma/Insomnia_get_admins.png "Imagem de exemplo")](https://github.com/systemboys/React_Codes/raw/main/Funcionalidades/Banco%20de%20Dados/Prisma/Insomnia_get_admins.png "Consultar os dados com o Insomnia")

Executar o POST para inserir um registro na tabela `admins` e gerar um `JSON`:

[![Registrar dados com o Insomnia](https://github.com/systemboys/React_Codes/raw/main/Funcionalidades/Banco%20de%20Dados/Prisma/insomnia_post_admins.png "Imagem de exemplo")](https://github.com/systemboys/React_Codes/raw/main/Funcionalidades/Banco%20de%20Dados/Prisma/insomnia_post_admins.png "Registrar dados com o Insomnia")

### Recriar instâncias nos módulos:

```jsx
npx prisma generate
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--banco-de-dados "Subir para o topo")

---

### Listar itens da tabela no seu componente

### INSTALAÇÕES NECESSÁRIAS

Instalar a dependência `Axios` no NPM do seu projeto o qual deseja listar os itens:

> O pacote 'axios' é uma popular biblioteca de cliente HTTP para fazer requisições em APIs web a partir de aplicações JavaScript.

```bash
npm install axios
```

> Obs.: Se houver erro, forçar a instalação com `--force`!

Instalar o `CORS` na sua API (`prisma`) fora do seu projeto o qual vai listar:

```bash
npm i cors
```

Instalar os `Types` do CORS:

```bash
npm i @types/cors
```

Criar no seu projeto o qual deseja listar os registros da tabela, o arquivo `./src/server/api.js`:

```jsx
import axios from "axios";

export const Api = axios.create({
    baseURL: 'http://localhost:3333',
    headers: {
        'Content-Type': 'application/json'
    }
});
```
### LISTAR OS ITENS NO SEU COMPONENTE (importação da API)

> Este exemplo lista itens de uma tabela de atualizações de commits do GitHub!

Na lista a qual deve obter os registros, importar os `Hooks` e a `Api`:

```jsx
import { useState, useEffect } from 'react';
import { Api } from '../../server/api';
```

> ( ! ) A importação da API e os hooks devem ficar fora do componente.

> Esse código importa os hooks `useState` e `useEffect` do pacote `react` e o objeto `Api` do arquivo `api.js` localizado no diretório `server`.
>
> Esses hooks são componentes fundamentais do React e são usados para gerenciar o estado e lidar com efeitos colaterais em componentes funcionais.
>
> O `useState` é um hook que permite adicionar estado a componentes funcionais. Ele retorna um par de valores: a variável de estado atual e uma função para atualizar esse estado.
>
> O `useEffect` é um hook que permite executar efeitos colaterais em componentes funcionais. Ele recebe uma função de callback como argumento e essa função é executada após a renderização do componente. Também pode ter uma lista de dependências opcional para controlar quando o efeito deve ser executado.
>
> O objeto `Api` é importado do arquivo `api.js` localizado no diretório `server`. Presumivelmente, esse objeto contém métodos para realizar chamadas à API, como `get`, `post`, etc.
>
> No geral, esse código prepara o ambiente para o uso dos hooks `useState` e `useEffect` e importa o objeto `Api` para realizar chamadas à API no componente atual.

Criar um `useState` e `setListUpdates` dentro do export do seu componente e configurar a rota no `Api.get()`:

```jsx
// Executar a requisição GET para a rota '/latest_updates' da API.
const [listUpdates, setListUpdates] = useState([]);
useEffect(() => {
    Api.get('/latest_updates').then((res) => {
        setListUpdates(res.data)
    })
}, []);
```

> Obs.: A constante `listUpdates` deve ser mapeada pelo `map()`, porque os dados da tabela estão nessa constante.

> Nesse código, um hook `useState` é utilizado para criar uma variável de estado chamada `listUpdates` e uma função `setListUpdates` para atualizar esse estado. Inicialmente, o valor do estado é definido como um array vazio `[]`.
>
> Em seguida, um hook `useEffect` é utilizado para executar uma chamada GET para a rota `/latest_updates` da API. Dentro da função de callback do `useEffect`, a função `Api.get('/latest_updates')` é chamada para fazer a requisição GET. Quando a resposta é recebida, a função `setListUpdates` é chamada para atualizar o estado `listUpdates` com os dados da resposta, `res.data`.
>
> O segundo argumento do `useEffect` é um array vazio `[]`, o que significa que o efeito só será executado uma vez, após a renderização inicial do componente.
>
> Em resumo, esse código realiza uma requisição GET para a rota `/latest_updates` da API e atualiza o estado `listUpdates` com os dados recebidos da resposta.

E por último, o `map()` para obter sua lista:

```jsx
<ul>
    {listUpdates.map(Updates => (
        <li>Atualização: {Updates.commit} | Data: {Updates.date} às {Updates.hour} | Autor: {Updates.author} | Descrição: {Updates.description}</li>
    ))}
</ul>
```

> Nesse exemplo de código, está sendo utilizado o método `map` no array `listUpdates` para iterar sobre cada elemento e retornar um elemento `<li>` para cada atualização.
>
>Dentro de cada `<li>`, são exibidas informações específicas de cada atualização, que são acessadas através das propriedades do objeto `Updates`. Essas informações incluem o commit da atualização (`Updates.commit`), a data e hora da atualização (`Updates.date` e `Updates.hour`), o autor da atualização (`Updates.author`), e a descrição da atualização (`Updates.description`).
>
> Todas essas informações são interpoladas no JSX utilizando as chaves `{}` para envolver as expressões JavaScript e exibi-las corretamente no elemento `<li>`. O resultado final é uma lista não ordenada (`<ul>`) onde cada item `<li>` contém as informações da respectiva atualização.

>>> Dica! [renderizar, elemento html, html, dangerouslySetInnerHTML, injetar html, conteúdo html, dom]

Para renderizar elementos HTML dentro do JSX, você pode usar a função `dangerouslySetInnerHTML` do React. Essa função permite injetar HTML diretamente no DOM, mas você deve usá-la com cuidado, pois ela pode expor seu aplicativo a ataques de injeção de script (cross-site scripting - XSS).

No seu código, você pode usar a função `dangerouslySetInnerHTML` da seguinte maneira:

```jsx
<Col sm={8} dangerouslySetInnerHTML={{ __html: listInQuestion[0]?.column }}></Col>
```

Observe que a propriedade `dangerouslySetInnerHTML` recebe um objeto com uma única propriedade `__html` que contém o HTML que você deseja injetar no DOM. O React irá avisá-lo caso esta propriedade esteja presente, para que você se certifique de que deseja fazer isso.

Com essa mudança, o conteúdo HTML deve ser renderizado corretamente no seu componente. Mas lembre-se de usar esta função com cuidado e evitar expor seu aplicativo a ataques de XSS.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--banco-de-dados "Subir para o topo")

---

## Trazer resultados aleatórios na lista

Se você deseja trazer os resultados aleatoriamente, uma opção é realizar a ordenação dos registros após a consulta usando JavaScript no seu arquivo onde está sua rota `./src/routes.ts`. Você pode utilizar a função `sort` para embaralhar a ordem dos resultados. Veja o exemplo abaixo:

> ( ! ) Essa modificação deve ser feita na sua rota!

```jsx
routes.get('/jm_posts_PostCarousel', async (req, res) => {
  const jm_posts = await prisma.jm_posts.findMany();
  const randomizedPosts = jm_posts.sort(() => Math.random() - 0.5).slice(0, 6);
  res.status(200).json(randomizedPosts);
});
```

> ( ! ) Esse exemplo foi testado em uma tabela de Posts de notícias!

Nesse exemplo, primeiro, todos os registros são recuperados usando `findMany`. Em seguida, a função `sort` é utilizada para ordenar os registros aleatoriamente, comparando dois elementos e retornando um número positivo, negativo ou zero. A função `Math.random()` é usada para gerar valores aleatórios entre 0 e 1, e subtraindo 0,5 garante que os resultados sejam embaralhados de forma aleatória. Por fim, é utilizada a função `slice` para limitar a quantidade de registros retornados, neste caso, para 6.

Dessa forma, você deve obter uma lista de resultados aleatórios a partir da consulta ao banco de dados.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--banco-de-dados "Subir para o topo")

---

## Listar 1 registro a partir do ID

### Listar 1 registro a partir do ID, Exemplo 1

No exemplo, iremos mudar o plano de fundo de um objeto onde é identificado pela classe `fenestra-desktop-icons`.

No arquivo `./src/routes.ts` da sua Api, crie sua rota:

```jsx
// Selecionar dados na tabela "backgrounds", a partir do ID do registro.
// Rota: 'backgroundsId/1'.
routes.get('/backgroundsId/:id', async (req, res) => {
    const { id } = req.params;
    const backgrounds = await prisma.backgrounds.findMany({
        where: {
            id: Number(id)
        }
    });
    res.status(200).json(backgrounds);
});
```

Caso tenha mais requisitos, basta incrementá-los na constante e na condição `where`:

```jsx
// Selecionar dados na tabela "customers_address", a partir da coluna "company" e "customer".
// Rota: 'customers/:company/:customer'.
routes.get('/customers/:company/:customer', async (req, res) => {
    const { company, customer } = req.params;
    const customersAddress = await prisma.customers_address.findMany({
        where: {
            company: Number(company),
            customer: Number(customer)
        },
    });
    res.status(200).json(customersAddress);
  });
```

> ( ! ) Lembrando que `Number()` se utilizando quando é número inteiro. O usuo de strings não é necessário!

```jsx
// Quando o parâmetro recebido pela URL for uma string, não há necessidade de Number().
where: {
    company: company,
    customer: Number(customer)
},
// ...
```

> Essa rota tem como objetivo selecionar dados da tabela "customers_address" com base nos valores das colunas "company" e "customer". A rota está definida como `'customers/:company/:customer'`, o que significa que ela espera receber os parâmetros "company" e "customer" na URL.
>
> Através do Prisma, é feita uma consulta à tabela "customers_address" utilizando o método `findMany`. A cláusula `where` é utilizada para filtrar os resultados com base nos valores das colunas "company" e "customer". É verificado se o valor da coluna "company" é igual ao parâmetro "company" fornecido na URL e se o valor da coluna "customer" é igual ao parâmetro "customer" fornecido na URL.
>
> Os dados encontrados são retornados como resposta da API com o status 200 (OK) utilizando o método `json`.
>
> No contexto da sua tabela "backgrounds_address", essa rota retornará os endereços de clientes que correspondem aos valores de "company" e "customer" fornecidos.
>
> Certifique-se de ter o Prisma corretamente configurado e adaptar o código conforme a estrutura do seu projeto.
>
> Se tiver mais dúvidas, fique à vontade para perguntar.

Importe os `hooks` necessários e sua `Api` no arquivo de seu componente:

```jsx
import { useState, useEffect } from 'react';
import { Api } from './server/api';
```

Dentro do seu componente, antes do retorno `return()`, execute a sua rota:

```jsx
// Selecionar dados na tabela "table", a partir do ID.
const [listBackground, setListBackground] = useState([]);
useEffect(() => {
    Api.get(`/backgroundsId/${id}`).then((res) => {
        setListBackground(res.data)
    });
}, []);

// Mudar o plano de fundo do objeto com a class determinada.
useEffect(() => {
    document.querySelector(".fenestra-desktop-icons").style.backgroundImage = `url(${listBackground[0]?.file})`;
}, [listBackground]);
```

> No exemplo acima, está sendo mudado o plano de fundo de um objeto. Note que na `url()` está setado o registro `listBackground[0]?.file` buscado na tabela do banco de dados.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--banco-de-dados "Subir para o topo")

---
### Listar 1 registro a partir do ID, Exemplo 2

Exemplo de uma consulta em uma tabela, onde seu resultado é colocado em outra rota para obter outra informação:

```jsx
const [listCompanySystem, setListCompanySystem] = useState([]);
const [listBackground, setListBackground] = useState([]);

// Selecionar dados na tabela "table_1", a partir do ID.
useEffect(() => {
    Api.get(`/companySystemCompanyId/${id}`).then((res) => {
        setListCompanySystem(res.data)
    });
}, []);

// Selecionar dados na tabela "table_2", a partir do registro da "table_1".
useEffect(() => {
    if (listCompanySystem.length > 0) {
        const BackgroundId = listCompanySystem[0]?.background;
        Api.get(`/backgroundsId/${BackgroundId}`).then((res) => {
            setListBackground(res.data)
        });
    }
}, [listCompanySystem]);

// Mudar o plano de fundo do objeto com a class determinada.
useEffect(() => {
    document.querySelector(".fenestra-desktop-icons").style.backgroundImage = `url(${listBackground[0]?.file})`;
}, [listBackground]);
```

> Neste exemplo, é selecionado um registro de uma tabela, onde esse registro é posto em outra rota para selecionar outro registro, logo em seguida fazendo a mudança do plano de fundo de um objeto.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--banco-de-dados "Subir para o topo")

---

### Listar 1 registro a partir do ID, Exemplo 3

Exemplo de mudança de plano de fundo, onde uma função obtem o registro a partir do ID na rota sendo passado como parâmetro.

```jsx
const [listGradientBackgrounds, setListGradientBackgrounds] = useState([]);
const [listBackground, setListBackground] = useState([]);

// Rota que obtem dados da tabela para obter o ID e levar como parâmetro da função no onClick={}.
useEffect(() => {
    Api.get(`/backgrounds/${id}`).then((res) => {
        setListGradientBackgrounds(res.data);
    });
}, []);

// Evento do onClick={}
const handleClick = (event, id) => {
    const element = document.querySelector('.fenestra-desktop-icons');
    if (element) {
        Api.get(`/backgroundsId/${id}`).then((res) => {
            setListBackground(res.data);
        });
    }
};

// Mudar o plano de fundo.
useEffect(() => {
    if (listBackground[0]?.file) {
        document.querySelector(".fenestra-desktop-icons").style.backgroundImage = `url(${listBackground[0]?.file})`;
    }
}, [listBackground]);
```

> No exemplo acima, estamos mudando o plano de fundo de um elemento, onde a primeira rota está buscando os planos de fundo da categoria "Gradiente" que é indicada pelo ID 2.

Aqui está o `onClick={}` como deve executar a função no elemento que executa a função:

```jsx
onClick={(event) => handleClick(event, GradientBackgrounds.id)}
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--banco-de-dados "Subir para o topo")

---

## Atualizar um registro a partir do ID

Para atualizar um registro a partir de um ID específico, segue a seguite rota para seu arquivo `./src/routes.ts`:

```jsx
// Atualizar dado na tabela "company_system", coluna "background" a partir do ID do registro.
// Rota: '/companySystemUpdateBackgroundId/1/2'.
routes.put('/companySystemUpdateBackgroundId/:companyId/:companyIdBackgroundId', async (req, res) => {
    const { companyId, companyIdBackgroundId } = req.params;
    const updatedCompanySystem = await prisma.company_system.update({
      where: { id: Number(companyId) },
      data: { background: Number(companyIdBackgroundId) },
    });
    res.status(200).json(updatedCompanySystem);
}); 
```

No seu componente antes do retorno, declare o estado da constante:

```jsx
const [setCompanySystemBackground] = useState([]);

// Atualizar dado na tabela "company_system", coluna "background" a partir do ID do registro.
Api.put(`/companySystemUpdateBackgroundId/1/${id}`).then((res) => {
    setCompanySystemBackground(res.data);
});
```

> No exemplo acima, estamos atualizando uma informação na tabela "company_system", na coluna "background" a partir do ID do registro, no caso o ID do registro é "1" e o dado da coluna é "2".

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--banco-de-dados "Subir para o topo")

---

## Gravar novo registro

### Gravar novo registro, Exemplo 1

Neste exemplo, estamos adicionando um registro na tabela "admins":

> Configurações feitas no arquivo `./src/routes.ts` de sua API.

```jsx
// Inserir dados na tabela "admins".
// Rota: '/admins'.
routes.post('/admins', async (req, res) => {
    const {
        primary_email,
        username,
        password,
        full_name,
        level
    } = req.body;
    // Gravar na tabela.
    const admins = await prisma.admins.create({
        data: {
            primary_email,
            username,
            password,
            full_name,
            level
        }
    });
    return res.status(201).json({ data:admins });
});
```

> No exemplo acima, é apenas uma gravação simples, sem regras.

Na função que intercepta a submissão do formulário em seu componente, você deve colocar o código da seguinte forma:

```jsx
// Interceptar o evento de submit.
async function handleSubmitAdmins(e) {
  e.preventDefault();

  // Validações ...

  // Dados do formulário.
  const data = { primary_email, username, password, full_name, level };

  // Chamada de API assíncrona - Envio dos dados para a API.
  try {
    await Api.post('admins', data);
  } catch (error) {
    alert('Ocorreu um erro ao enviar os dados. Tente novamente mais tarde.');
    console.error(error);
  }
}
```

O código apresentado é uma chamada de API assíncrona que tenta enviar dados (data) para um servidor usando o método HTTP POST, por meio da biblioteca Api. O objetivo é inserir um novo registro na coleção de motoristas no servidor.

O try é utilizado para lidar com possíveis erros durante a chamada da API. O código dentro do bloco try é executado normalmente, e, caso ocorra um erro, o controle é transferido para o bloco catch.

Caso haja sucesso na chamada da API, a execução continua normalmente. Caso contrário, é exibido um alerta com a mensagem "Error!".

O await é utilizado para esperar pela conclusão da chamada da API antes de prosseguir com a execução do código. Isso garante que a chamada da API será finalizada antes que qualquer outra ação seja executada no código.

O uso do await é uma forma de lidar com chamadas de API assíncronas no JavaScript, que são operações que podem levar algum tempo para serem concluídas e não bloqueiam a execução do código. Com o uso do await, o código não prossegue até que a operação assíncrona seja finalizada.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--banco-de-dados "Subir para o topo")

---

## Consulta com o PRISMA em um compoente classe

Se o componente for uma classe em vez de uma função, você pode utilizar o método `componentDidMount` para fazer a chamada à API e definir o estado inicial com a lista de atualizações vazia:

```jsx
import React, { Component } from 'react';
import { Api } from '../../server/api';

class MeuComponente extends Component {
  constructor(props) {
    super(props);
    this.state = {
      listUpdates: []
    };
  }

  componentDidMount() {
    Api.get('/latest_updates').then((res) => {
      this.setState({ listUpdates: res.data });
    });
  }

  render() {
    return (
      <ul>
        {this.state.listUpdates.map(Updates => (
          <li>Atualização: {Updates.commit} | Data: {Updates.date} às {Updates.hour} | Autor: {Updates.author} | Descrição: {Updates.description}</li>
        ))}
      </ul>
    );
  }
}

export default MeuComponente;
```

O método `componentDidMount` é chamado automaticamente pelo React quando o componente é montado na tela. Dentro dele, é feita a chamada à API e o estado inicial do componente é definido com a lista de atualizações vazia. Quando a resposta da API é obtida, o estado é atualizado com a lista de atualizações recebida. Na função de renderização do componente, a lista é exibida utilizando o método `map()` como no exemplo anterior.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--banco-de-dados "Subir para o topo")

---

## Listar em componentes classe

Em componentes classe, você pode seguir os seguintes passos:

1. Importe o `useEffect` e o `useState` do React.

```jsx
import React, { Component, useEffect, useState } from 'react';
```

2. Importe sua API:

```jsx
import { Api } from '../../server/api';
```

3. Atualize o estado inicial no construtor `constructor()` da classe e adicione uma função de `componentDidMount` para fazer a chamada à API e atualizar o estado do componente.

```jsx
class YourComponent extends Component {
    constructor() {
      // Atualizar o estado inicial no construtor.
      this.state = {
        listPosts: [],
      };
    }
    
    componentDidMount() {
        // Buscar "jm_posts" da API e atualizar o estado com os dados retornados.
        Api.get('/jm_posts').then((res) => {
          this.setState({ listPosts: res.data });
        });
    }

    render() {
        return (
            <div>
                <Slider>
                    {this.state.listPosts.slice(0, 9).map((item, i) => (
                        <div key={i}>
                            <div>
                                <img src={item.image} />
                            </div>
                            <div>
                                <div>
                                    <Link to="#">{item.category}</Link>
                                    <Link to="#">{item.date}</Link>
                                </div>
                                <h4><Link>{item.title}</Link></h4>
                                <div />
                                <p>{item.summary}</p>
                            </div>
                        </div>
                    ))}
                </Slider>
            </div>
        );
    }
}
```

Com essas alterações, seu componente deve ser capaz de fazer a chamada à API e renderizar os dados recebidos. Lembre-se de importar o `Api` de onde ele está definido e ajustar o caminho para a rota correta.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--banco-de-dados "Subir para o topo")

---

## Configurando uma rota dentro de um componente de classe em React

Aqui está a rota dentro de um componente de classe:

```jsx
import React, { Component } from 'react';
import Api from 'path/to/Api'; // Importe o módulo de API conforme necessário

class MyComponent extends Component {
  constructor(props) {
    super(props);
    this.state = {
      listJMPosts: [],
    };
  }

  componentDidMount() {
    Api.get('/jm_posts').then((res) => {
      const formattedData = res.data.map((item) => ({
        thumb: item.thumb,
        title: item.title,
        category: item.category,
        date: item.date,
      }));
      this.setState({ listJMPosts: formattedData });
    });
  }

  render() {
    const { listJMPosts } = this.state;

    return (
      // Renderize o conteúdo do componente aqui, usando os dados de listJMPosts
      // ...
    );
  }
}

export default MyComponent;
```

Certifique-se de substituir `'path/to/Api'` pelo caminho correto para o módulo de API que você está usando em seu projeto. Além disso, lembre-se de atualizar a lógica de renderização para exibir os dados de `listJMPosts` conforme necessário.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--banco-de-dados "Subir para o topo")

---

## Formatação de Dados da API em um Array no Formato Específico (JSON)

Para formatar os dados retornados pela consulta em um array no formato desejado, você pode fazer o seguinte:

```jsx
// Selecionar dados na tabela "table", a partir do "category".
const [listBackground, setListBackground] = useState([]);
useEffect(() => {
  Api.get(`/backgroundsId/${category}`).then((res) => {
    const formattedData = res.data.map((item) => ({
      image: `/img/backgrounds/${item.thumb}`,
      title: item.title,
      category: item.category,
      date: item.date,
    }));
    setListBackground(formattedData);
  });
}, []);

console.log(listBackground); // Retorno no console.
```

> ( ! ) A chamada à API deve ficar dentro do componente!

Aqui, usamos o método `map()` para percorrer cada item retornado pela consulta e criar um novo objeto no formato desejado. Em seguida, definimos o estado `listBackground` com o array `formattedData`, que contém os dados formatados.

Certifique-se de que as propriedades `thumb`, `title`, `category` e `date` correspondam aos nomes corretos dos campos na resposta da API.

> Esse código faz uma chamada à API para obter dados da tabela "backgroundsId" com base na categoria fornecida. Ele usa os hooks `useState` e `useEffect` para fazer a chamada da API e formatar os dados recebidos.
>
> A chamada à API é feita através do `Api.get()` e usa o caminho `/backgroundsId/${category}` para buscar os dados correspondentes à categoria especificada.
>
> Quando a resposta da API é recebida, o código formata os dados retornados usando o método `map()`. Cada item retornado é transformado em um objeto com as propriedades `image`, `title`, `category` e `date`.
>
> Em seguida, os dados formatados são atribuídos ao estado `listBackground` usando a função `setListBackground`. Isso atualiza o estado com os dados obtidos da API.
>
> O `useEffect` é usado para executar esse código sempre que a categoria for alterada. A dependência vazia `[]` no final indica que o efeito deve ser executado apenas uma vez, após a montagem do componente.
>
> Por fim, o `console.log(listBackground)` é usado para exibir o valor atual de `listBackground` no console. Isso pode ser útil para verificar se os dados foram obtidos corretamente e para depurar eventuais problemas.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--banco-de-dados "Subir para o topo")

---

## Obtendo registros com limite e paginação na rota

Para obter registros de 6 a 10 na rota '/jm_posts', você pode usar o método `skip` para pular os primeiros 6 registros e, em seguida, definir o limite usando o método `take`. O código ficaria assim:

> ( ! ) Essa configuração deve ser feita na sua rota!

```jsx
// Selecionar dados na tabela "jm_posts".
// Rota: '/jm_posts'.
routes.get('/jm_posts', async (req, res) => {
  const jm_posts = await prisma.jm_posts.findMany({
    orderBy: {
      id: 'desc'
    },
    skip: 6, // Número de registros a pular.
    take: 5 // Limite de registros a exibir.
  });
  res.status(200).json(jm_posts);
});
```

Dessa forma, a consulta retornará os registros de 6 a 10, ordenados por ID de forma decrescente.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--banco-de-dados "Subir para o topo")

---

## Correção do Carrossel e Botão de Passador em Componente React

Parece que o problema está relacionado ao momento em que o componente está sendo renderizado e o estado `listPosts` está sendo atualizado com os dados da API. Quando o componente é renderizado inicialmente, o estado `listPosts` está vazio e, portanto, o carrossel exibe apenas um item.

Uma solução para garantir que o carrossel seja renderizado corretamente após os dados serem carregados é adicionar uma verificação antes de renderizar o carrossel. Você pode verificar se o estado `listPosts` tem dados antes de renderizar o carrossel. Algo assim:

```jsx
{listPosts.length > 0 && (
  <Swiper getSwiper={setSwiper} className="trancarousel" {...params}>
    {listPosts.map((item, i) => (
      <div key={i} className="single_post widgets_small post_type5">
        <div className="post_img">
          <div className="img_wrap">
            <Link to="/">
              <img src={item.image} alt="slider5" />
            </Link>
          </div>
        </div>
        <div className="single_post_text">
          <h4>
            <Link to="/post1">{item.title}</Link>
          </h4>
          <p>{item.body}</p>
        </div>
      </div>
    ))}
  </Swiper>
)}
```

Dessa forma, o carrossel será renderizado somente quando o estado `listPosts` tiver dados disponíveis.

Quanto à diferença de comportamento entre `listPosts` e `postSlider`, pode haver uma diferença na estrutura dos dados retornados pela API em comparação com o array `postSlider`. Verifique se os dados retornados pela API têm a mesma estrutura esperada pelo carrossel. Verifique também se o array `listPosts` contém os dados corretos após a chamada da API, verificando o valor em `console.log(listPosts)` logo após `setListPosts(formattedData)`.

Essas verificações ajudarão a identificar possíveis discrepâncias nos dados e a solucionar o problema de exibição do carrossel.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--banco-de-dados "Subir para o topo")

---

## Resolvendo Problemas de Carregamento Tardio de Dados em Componentes React com API

> ( ! ) Problema de carregamento de dados!
>
> "Os dados da API estão sendo retornados corretamente e o slider está configurado corretamente, mas o carregamento dos dados, só aparecem quando o slide começa a deslizar."

O problema de carregamento dos dados pode estar relacionado à ordem em que o componente é renderizado e os dados são buscados da API. Uma possível solução para garantir que os dados estejam disponíveis antes de renderizar o componente é renderizar o componente somente quando os dados da API forem recuperados.

Para fazer isso, você pode adicionar uma verificação antes da renderização do componente para garantir que a lista de notícias `listJMPosts` não esteja vazia. Se a lista estiver vazia, você pode exibir uma mensagem de carregamento ou um indicador de progresso. Veja como você pode fazer isso:

```jsx
class PostGallery extends Component {
    // ... (código existente).

    render() {
        const { className } = this.props;
        const { nav1, nav2, vModal, videoId, listJMPosts } = this.state;

        // Verificar se a lista de notícias está vazia.
        if (listJMPosts.length === 0) {
            return <div>Carregando...</div>; // Exibir mensagem de carregamento.
        }

        // ... (restante do código de renderização).
    }
}
```

> ( ! ) A solução está apenas na condição da estrutura de controle onde é verificado se a lista de notícias está vazia!

Com essa abordagem, o componente só será renderizado quando os dados da API forem recuperados e a lista de notícias não estiver vazia. Isso garante que os dados estejam prontos antes da renderização, evitando problemas de carregamento tardio no slider. Certifique-se de que a estrutura condicional seja colocada no local apropriado dentro do método `render`.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--banco-de-dados "Subir para o topo")

---

## Como Inicializar uma DataTable com Dados de uma API no ReactJS

Neste guia, mostramos como usar o ReactJS para buscar dados de uma API e inicializar uma DataTable somente após os dados terem sido carregados  com sucesso. Isso garante que a DataTable funcione corretamente e evita  problemas de dados vazios ou inexistentes.

```jsx
// Selecionar dados na tabela "produtos".
const [listProducts, setListProducts] = useState([]);
const [dataLoaded, setDataLoaded] = useState(false);
useEffect(() => {
    Api.get(`/productsPrimaryEmail/1`).then((res) => {
        const formattedData = res.data.map((item) => ({
            id: item.id,
            description: item.description,
            bar_code: item.bar_code,
            amount: item.amount,
            final_value: item.final_value,
        }));
        setListProducts(formattedData);
        setDataLoaded(true); // Indicar que os dados foram carregados.
    });
}, []);

useEffect(() => {
    if (dataLoaded) {
        const table = new DataTable('#listProducts', {
            responsive: true
        });
        return () => {
            table.destroy(); // Destruir a tabela quando o componente for desmontado.
        };
    }
}, [dataLoaded, listProducts]);
```

Observe a alteração feita.

```jsx
// Selecionar dados na tabela "produtos".
// ...
const [dataLoaded, setDataLoaded] = useState(false);
// ...

useEffect(() => {
    if (dataLoaded) {
        // ..
    }
}, [dataLoaded, listProducts]);
```

A alteração que você fez no código envolve o uso de um segundo `useEffect` que depende das variáveis `dataLoaded` e `listProducts`. Vou explicar o que essa alteração faz em detalhes:

1. `dataLoaded` é uma variável de estado que você definiu inicialmente como `false`. Ela será usada para controlar se os dados da API já foram carregados ou não.

2. No primeiro `useEffect`, você faz uma requisição à API para buscar os dados da tabela "produtos". Quando os dados são obtidos com sucesso, você formata esses dados e os armazena no estado `listProducts` usando `setListProducts`. Em seguida, você define `dataLoaded` como `true` usando `setDataLoaded(true)` para indicar que os dados foram carregados.

3. No segundo `useEffect`, você monitora as variáveis `dataLoaded` e `listProducts` como dependências. Isso significa que esse `useEffect` será executado sempre que uma dessas variáveis mudar.

4. Quando `dataLoaded` se torna `true`, significa que os dados da API foram carregados com sucesso. Nesse momento, você cria uma instância da DataTable usando o seletor `#listProducts`. A DataTable é uma biblioteca para criar tabelas interativas em páginas da web. Você inicializa a DataTable dentro deste `useEffect`.

5. Além disso, você fornece a opção `responsive: true` ao criar a DataTable, o que sugere que a tabela será responsiva, ou seja, se ajustará automaticamente ao tamanho da tela.

6. No retorno da função do `useEffect`, você destrói a instância da DataTable chamando `table.destroy()`. Isso é importante para liberar recursos e evitar vazamentos de memória quando o componente for desmontado.

Em resumo, essa alteração garante que a DataTable seja inicializada somente após os dados da API terem sido carregados com sucesso (ou seja, quando `dataLoaded` se torna `true`). Isso evita que a DataTable seja inicializada com dados vazios ou inexistentes e garante que ela funcione corretamente com os dados reais da API quando estiver pronta para ser exibida na página.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--banco-de-dados "Subir para o topo")

---