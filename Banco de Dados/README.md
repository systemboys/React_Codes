# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Banco de Dados

- [Conectar Banco de Dados `MySQL` com ORM `PRISMA`](https://github.com/systemboys/React_Codes/tree/main/Banco%20de%20Dados#conectar-banco-de-dados-mysql-com-orm-prisma "Conectar Banco de Dados MySQL com ORM PRISMA")
    - [Criar um `novo projeto` e iniciar o servidor](https://github.com/systemboys/React_Codes/tree/main/Banco%20de%20Dados#criar-um-novo-projeto-e-iniciar-o-servidor "Criar um novo projeto e iniciar o servidor")
    - [Instalar o PRISMA](https://github.com/systemboys/React_Codes/tree/main/Banco%20de%20Dados#instalar-o-prisma "Instalar o PRISMA")
    - [Configurar o arquivo `./.env`](https://github.com/systemboys/React_Codes/tree/main/Banco%20de%20Dados#configurar-o-arquivo-env "Configurar o arquivo .env")
    - [Configurar no arquivo `./prisma/schema.prisma` o trecho de codigo](https://github.com/systemboys/React_Codes/tree/main/Banco%20de%20Dados#configurar-no-arquivo-prismaschemaprisma-o-trecho-de-codigo "Configurar no arquivo ./prisma/schema.prisma o trecho de codigo")
    - [Escrevendo o model no arquivo `./prisma/schema.prisma`](https://github.com/systemboys/React_Codes/tree/main/Banco%20de%20Dados#escrevendo-o-model-no-arquivo-prismaschemaprisma "Escrevendo o model no arquivo `prisma/schema.prisma`")
    - [Criar o arquivo `./src/prisma.ts` e configure o seguinte código](https://github.com/systemboys/React_Codes/tree/main/Banco%20de%20Dados#criar-o-arquivo-srcprismats-e-configure-o-seguinte-c%C3%B3digo "Criar o arquivo `src/prisma.ts` e configure o seguinte código")
    - [Criar o arquivo `./src/server.ts` e configure o seguinte código](https://github.com/systemboys/React_Codes/tree/main/Banco%20de%20Dados#criar-o-arquivo-srcserverts-e-configure-o-seguinte-c%C3%B3digo "Criar o arquivo `src/server.ts` e configure o seguinte código")
    - [Criar e configurar o arquivo `./src/routes.ts`](https://github.com/systemboys/React_Codes/tree/main/Banco%20de%20Dados#criar-e-configurar-o-arquivo-srcroutests "Criar e configurar o arquivo src/routes.ts")
    - [Utilização do `Insomnia` para leitura, gravação, atualização e delete](https://github.com/systemboys/React_Codes/tree/main/Banco%20de%20Dados#utiliza%C3%A7%C3%A3o-do-insomnia-para-leitura-grava%C3%A7%C3%A3o-atualiza%C3%A7%C3%A3o-e-delete "Utilização do Insomnia para leitura, gravação, atualização e delete")
    - [`Recriar instâncias` nos módulos](https://github.com/systemboys/React_Codes/tree/main/Banco%20de%20Dados#recriar-inst%C3%A2ncias-nos-m%C3%B3dulos "Recriar instâncias nos módulos")
- [`Listar itens` da `tabela` no seu componente](https://github.com/systemboys/React_Codes/tree/main/Banco%20de%20Dados#listar-itens-da-tabela-no-seu-componente "Listar itens da tabela no seu componente")
    - [Instalações necessárias](https://github.com/systemboys/React_Codes/tree/main/Banco%20de%20Dados#instala%C3%A7%C3%B5es-necess%C3%A1rias "Instalações necessárias")
    - [Listar os itens no seu componente](https://github.com/systemboys/React_Codes/tree/main/Banco%20de%20Dados#listar-os-itens-no-seu-componente "Listar os itens no seu componente")

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
})
```

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
[(&uarr;) Subir](https://github.com/systemboys/React_Codes/tree/main/Banco%20de%20Dados#react-codes--banco-de-dados "Subir para o topo")

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
[(&uarr;) Subir](https://github.com/systemboys/React_Codes/tree/main/Banco%20de%20Dados#react-codes--banco-de-dados "Subir para o topo")

------------