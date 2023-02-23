# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Banco de Dados

- [Conectar Banco de Dados `MySQL` com ORM `PRISMA`](#conectar-banco-de-dados-mysql-com-orm-prisma "Conectar Banco de Dados MySQL com ORM PRISMA")
    - [Criar um `novo projeto` e iniciar o servidor](#criar-um-novo-projeto-e-iniciar-o-servidor "Criar um novo projeto e iniciar o servidor")
    - [Instalar o PRISMA](#instalar-o-prisma "Instalar o PRISMA")
    - [Configurar o arquivo `./.env`](#configurar-o-arquivo-env "Configurar o arquivo .env")
    - [Configurar no arquivo `./prisma/schema.prisma` o trecho de codigo](#configurar-no-arquivo-prismaschemaprisma-o-trecho-de-codigo "Configurar no arquivo ./prisma/schema.prisma o trecho de codigo")
    - [Escrevendo o model no arquivo `./prisma/schema.prisma`](#escrevendo-o-model-no-arquivo-prismaschemaprisma "Escrevendo o model no arquivo `prisma/schema.prisma`")
    - [Criar o arquivo `./src/prisma.ts` e configure o seguinte código](#criar-o-arquivo-srcprismats-e-configure-o-seguinte-c%C3%B3digo "Criar o arquivo `src/prisma.ts` e configure o seguinte código")
    - [Criar o arquivo `./src/server.ts` e configure o seguinte código](#criar-o-arquivo-srcserverts-e-configure-o-seguinte-c%C3%B3digo "Criar o arquivo `src/server.ts` e configure o seguinte código")
    - [Criar e configurar o arquivo `./src/routes.ts`](#criar-e-configurar-o-arquivo-srcroutests "Criar e configurar o arquivo src/routes.ts")
    - [Utilização do `Insomnia` para leitura, gravação, atualização e delete](#utiliza%C3%A7%C3%A3o-do-insomnia-para-leitura-grava%C3%A7%C3%A3o-atualiza%C3%A7%C3%A3o-e-delete "Utilização do Insomnia para leitura, gravação, atualização e delete")
    - [`Recriar instâncias` nos módulos](#recriar-inst%C3%A2ncias-nos-m%C3%B3dulos "Recriar instâncias nos módulos")
- [`Listar itens` da `tabela` no seu componente](#listar-itens-da-tabela-no-seu-componente "Listar itens da tabela no seu componente")
    - [Instalações necessárias](#instala%C3%A7%C3%B5es-necess%C3%A1rias "Instalações necessárias")
    - [Listar os itens no seu componente](#listar-os-itens-no-seu-componente "Listar os itens no seu componente")
    - [Listar 1 registro a partir do ID](#listar-1-registro-a-partir-do-id "Listar 1 registro a partir do ID")

------------

## Conectar Banco de Dados MySQL com ORM PRISMA

### Criar um novo projeto e iniciar o servidor:

> Crie um novo projeto fora do diretório do seu projeto o qual quer conectá-lo. Na verdade, você estará criando uma API para conectar seu projeto!

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

Iniciar TypeScript:

```bash
npx tsc --init
```

Mudar "target": "es2016" para "es2020" no arquivo `./tsconfig.json`:

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
npm install @prisma/cliente
```

Iniciar o PRISMA:

```bash
npx prisma init
```

### Configurar o arquivo `./.env`:

```javascript
DATABASE_URL="mysql://youUser:yourPassword@yourHost:3306/yourDataBase"
```

> Onde:
> `youUser` é seu usuário de banco de dados,
> `yourPassword` é a senha,
> `yourHost` é o Host de sua hospedagem,
> `3306` é porta e
> `yourDataBase` é seu banco de dados.

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

[![Print de uma execução no Db Pull](https://github.com/systemboys/React_Codes/raw/main/Banco%20de%20Dados/Prisma/npx_prisma_db_pull.png "Print de uma execução no Db Pull")](https://github.com/systemboys/React_Codes/raw/main/Banco%20de%20Dados/Prisma/npx_prisma_db_pull.png "Print de uma execução no Db Pull")

### Criar o arquivo `./src/prisma.ts` e configure o seguinte código:

```javascript
import { PrismaClient } from "@prisma/client"

export const prisma = new PrismaClient ({
    log: ['query'],
})
```

### Criar o arquivo `./src/server.ts` e configure o seguinte código:

```javascript
import express from 'express';
import { routes } from './routes';

const App = express();

App.use(express.json())
App.use(routes);
App.listen(3333, ()=>{
    console.log('Server is running! 🔥');
});
```

Para habilitar o CORS no seu servidor Express, você pode usar a biblioteca cors. Para permitir qualquer origem, você pode passar `{ origin: '*' }` como opções para a função `cors()`.

Você pode modificar o seu arquivo `server.ts` da seguinte forma:

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
  console.log('Server is running! 🔥');
});

```

A configuração acima permite que todas as solicitações de origens diferentes sejam aceitas. Você também pode especificar uma lista de origens permitidas, caso queira restringir o acesso a um conjunto específico de domínios. Para mais informações sobre como configurar o CORS em sua aplicação, consulte a documentação do pacote `cors` no npm.

> Com essa configuração, todas as requisições vindas de qualquer origem serão permitidas. Lembre-se que em produção, você deve configurar o CORS de forma mais restrita, permitindo somente as origens necessárias.

### Criar e configurar o arquivo `./src/routes.ts`:

```javascript
import express from "express";
import { prisma } from './prisma';

export const routes = express.Router();

// ### Consultar 'admins' ###
routes.get('/admins', async (req, res) => {
    const admins = await prisma.admins.findMany(
        orderBy: {
            id: 'desc'
        }
    );
    res.status(200).json(admins);
});

/* Consultar 'admins/:Number(level)', onde o nível é um determinado valor.
Essa rota deve conter o parâmentro específico. Exemplo: Api.get('/admins/2').then((res) => ... */

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

// ### Inserir 'admins' ###
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

Execute o servidor NPM:

```bash
npm run dev
```

[![Server executando](https://github.com/systemboys/React_Codes/raw/main/Banco%20de%20Dados/Prisma/npm_run_dev.png "Server executando")](https://github.com/systemboys/React_Codes/raw/main/Banco%20de%20Dados/Prisma/npm_run_dev.png "Server executando")

### Utilização do `Insomnia` para leitura, gravação, atualização e delete.

Executar o GET para consultar os registros na tabela `admins` e gerar um `JSON` com o `Insomnia`:

[![Consultar os dados com o Insomnia](https://github.com/systemboys/React_Codes/raw/main/Banco%20de%20Dados/Prisma/Insomnia_get_admins.png "Imagem de exemplo")](https://github.com/systemboys/React_Codes/raw/main/Banco%20de%20Dados/Prisma/Insomnia_get_admins.png "Consultar os dados com o Insomnia")

Executar o POST para inserir um registro na tabela `admins` e gerar um `JSON`:

[![Registrar dados com o Insomnia](https://github.com/systemboys/React_Codes/raw/main/Banco%20de%20Dados/Prisma/insomnia_post_admins.png "Imagem de exemplo")](https://github.com/systemboys/React_Codes/raw/main/Banco%20de%20Dados/Prisma/insomnia_post_admins.png "Registrar dados com o Insomnia")

### Recriar instâncias nos módulos:

```javascript
npx prisma generate
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--banco-de-dados "Subir para o topo")

------------

### Listar itens da tabela no seu componente

### INSTALAÇÕES NECESSÁRIAS

Instalar a dependência `Axios` no NPM do seu projeto o qual deseja listar os itens:

```bash
npm i axios
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
### LISTAR OS ITENS NO SEU COMPONENTE

> Este exemplo lista itens de uma tabela de atualizações de commits do GitHub!

Na lista a qual deve obter os registros, importar os `Hooks` e a `Api`:

```javascript
import { useState, useEffect } from 'react';
import { Api } from '../../server/api';
```

Criar um `useState` e `setListUpdates` dentro do export do seu componente e configurar a rota no `Api.get()`:

```javascript
const [listUpdates, setListUpdates] = useState([]);
useEffect(() => {
    Api.get('/latest_updates').then((res) => {
        setListUpdates(res.data)
    })
}, []);
```

E por último, o `map()` para obter sua lista:

```javascript
<ul>
    {listUpdates.map(Updates => (
        <li>Atualização: {Updates.commit} | Data: {Updates.date} às {Updates.hour} | Autor: {Updates.author} | Descrição: {Updates.description}</li>
    ))}
</ul>
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--banco-de-dados "Subir para o topo")

------------

## Listar 1 registro a partir do ID

No exemplo, iremos mudar o plano de fundo de um objeto onde é identificado pela classe `fenestra-desktop-icons`.

No arquivo `src/routes.ts` da sua Api, crie sua rota:

```javascript
// Consultar 'backgroundsId/:Number(id)'.
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
// Obter o registro a partir do ID na rota.
const [listBackground, setListBackground] = useState([]);

useEffect(() => {
  Api.get('/backgroundsId/67').then((res) => {
    setListBackground(res.data)
  });
}, []);

// Mudar o plano de fundo do objeto com a class determinada.
useEffect(() => {
  document.querySelector(".fenestra-desktop-icons").style.backgroundImage = `url(${listBackground[0]?.file})`;
}, [listBackground]);
```

> No exemplo acima, está sendo mudado o plano de fundo de um objeto. Note que na `url()` está setado o registro `listBackground[0]?.file` buscado na tabela do banco de dados.

Exemplo de uma consulta de um registro de uma outra tabela, onde seu resultado é colocado em outra rota para selecionar outra informação:

```javascript
const [listCompanySystem, setListCompanySystem] = useState([]);
const [listBackground, setListBackground] = useState([]);

useEffect(() => {
Api.get('/companySystemCompanyId/1').then((res) => {
    setListCompanySystem(res.data)
});
}, []);

useEffect(() => {
if (listCompanySystem.length > 0) {
    const SystemCompanyId = listCompanySystem[0]?.background;
    Api.get(`/backgroundsId/${SystemCompanyId}`).then((res) => {
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

------------