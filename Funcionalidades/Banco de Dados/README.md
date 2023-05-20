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
    - [Listar os itens no seu componente (`importação da API`)](#listar-os-itens-no-seu-componente "Listar os itens no seu componente (importação da API)")
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

> Algumas dicas úteis.

- [Formatação de Dados da API em um Array no Formato Específico (`JSON`)](#formata%C3%A7%C3%A3o-de-dados-da-api-em-um-array-no-formato-espec%C3%ADfico-json "Formatação de Dados da API em um Array no Formato Específico (JSON)")
- [Obtendo registros com limite e paginação na rota](#obtendo-registros-com-limite-e-pagina%C3%A7%C3%A3o-na-rota "Obtendo registros com limite e paginação na rota")

---

## Conectar Banco de Dados MySQL com ORM PRISMA

### Criar um novo projeto e iniciar o servidor:

> Crie um novo projeto com o Vite fora do diretório do seu projeto o qual deseja conectá-lo ao banco de dados. Você irá criar uma API para conectar seu projeto!

```bash
npm create vite@latest api_project_name
```

> Selecione a framework `React`, depois a variante `TypeScript`.

Agora rode os comandos seguintes para testar:

```bash
cd api_project_name
npm install
npm run dev
```

> Você estará entrando no seu novo projeto e instalando as dependências do node e o comando `npm run dev` rodar o servidor.

Após testar, parar o servidor, apagar os arquivos `./index.html` e `./tsconfig.json`, o diretório `./public/` e todos os arquivos dentro do diretório `./src/`.

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

```javascript
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

```javascript
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

```javascript
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

```javascript
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

```javascript
import { PrismaClient } from "@prisma/client";

export const prisma = new PrismaClient ({
    log: ['query'],
});
```

### Criar o arquivo `./src/server.ts` e configure o seguinte código:

```javascript
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

```javascript
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

```javascript
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

```javascript
"script": {
    "dev": "tsx watch src/server.ts"
}
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

```javascript
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

```javascript
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

```javascript
import { useState, useEffect } from 'react';
import { Api } from '../../server/api';
```

Criar um `useState` e `setListUpdates` dentro do export do seu componente e configurar a rota no `Api.get()`:

```javascript
// Executar a requisição GET para a rota '/latest_updates' da API.
const [listUpdates, setListUpdates] = useState([]);
useEffect(() => {
    Api.get('/latest_updates').then((res) => {
        setListUpdates(res.data)
    })
}, []);
```

> Obs.: A constante `listUpdates` deve ser mapeada pelo `map()`, porque os dados da tabela estão nessa constante.

E por último, o `map()` para obter sua lista:

```javascript
<ul>
    {listUpdates.map(Updates => (
        <li>Atualização: {Updates.commit} | Data: {Updates.date} às {Updates.hour} | Autor: {Updates.author} | Descrição: {Updates.description}</li>
    ))}
</ul>
```

>>> Dica! [renderizar, elemento html, html, dangerouslySetInnerHTML, injetar html, conteúdo html, dom]

Para renderizar elementos HTML dentro do JSX, você pode usar a função `dangerouslySetInnerHTML` do React. Essa função permite injetar HTML diretamente no DOM, mas você deve usá-la com cuidado, pois ela pode expor seu aplicativo a ataques de injeção de script (cross-site scripting - XSS).

No seu código, você pode usar a função `dangerouslySetInnerHTML` da seguinte maneira:

```javascript
<Col sm={8} dangerouslySetInnerHTML={{ __html: listInQuestion[0]?.column }}></Col>
```

Observe que a propriedade `dangerouslySetInnerHTML` recebe um objeto com uma única propriedade `__html` que contém o HTML que você deseja injetar no DOM. O React irá avisá-lo caso esta propriedade esteja presente, para que você se certifique de que deseja fazer isso.

Com essa mudança, o conteúdo HTML deve ser renderizado corretamente no seu componente. Mas lembre-se de usar esta função com cuidado e evitar expor seu aplicativo a ataques de XSS.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--banco-de-dados "Subir para o topo")

---

## Listar 1 registro a partir do ID

### Listar 1 registro a partir do ID, Exemplo 1

No exemplo, iremos mudar o plano de fundo de um objeto onde é identificado pela classe `fenestra-desktop-icons`.

No arquivo `./src/routes.ts` da sua Api, crie sua rota:

```javascript
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

Importe os `hooks` necessários e sua `Api` no arquivo de seu componente:

```javascript
import { useState, useEffect } from 'react';
import { Api } from './server/api';
```

Dentro do seu componente, antes do retorno `return()`, execute a sua rota:

```javascript
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

```javascript
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

```javascript
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

```javascript
onClick={(event) => handleClick(event, GradientBackgrounds.id)}
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--banco-de-dados "Subir para o topo")

---

## Atualizar um registro a partir do ID

Para atualizar um registro a partir de um ID específico, segue a seguite rota para seu arquivo `./src/routes.ts`:

```javascript
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

```javascript
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

```javascript
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

```javascript
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

```javascript
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

```javascript
import React, { Component, useEffect, useState } from 'react';
```

2. Importe sua API:

```javascript
import { Api } from '../../server/api';
```

3. Atualize o estado inicial no construtor `constructor()` da classe e adicione uma função de `componentDidMount` para fazer a chamada à API e atualizar o estado do componente.

```javascript
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

```javascript
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
      image: item.thumb,
      title: item.title,
      category: item.category,
      date: item.date,
    }));
    setListBackground(formattedData);
  });
}, []);
```

Aqui, usamos o método `map()` para percorrer cada item retornado pela consulta e criar um novo objeto no formato desejado. Em seguida, definimos o estado `listBackground` com o array `formattedData`, que contém os dados formatados.

Certifique-se de que as propriedades `thumb`, `title`, `category` e `date` correspondam aos nomes corretos dos campos na resposta da API.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--banco-de-dados "Subir para o topo")

---

## Obtendo registros com limite e paginação na rota

Para obter registros de 6 a 10 na rota '/jm_posts', você pode usar o método `skip` para pular os primeiros 6 registros e, em seguida, definir o limite usando o método `take`. O código ficaria assim:

```javascript
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