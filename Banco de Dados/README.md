# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Banco de Dados

- [Conectar Banco de Dados `MySQL` com ORM `PRISMA`](https://github.com/systemboys/React_Codes/tree/main/Banco%20de%20Dados#conectar-banco-de-dados-mysql-com-orm-prisma "Conectar Banco de Dados MySQL com ORM PRISMA")

------------

## Conectar Banco de Dados MySQL com ORM PRISMA

Criar um novo projeto e iniciar o servidor:

> Crie um novo projeto fora do diretório do seu projeto o qual quer conectá-lo. Na verdade, você estará criando uma API para conectar seu projeto!

```
npm init -y
```

Instalar o Express:

```
npm i express @types/express
```

Instalar o TypeScript:

```
npm install typescript ts-node @types/node --save-dev
```

Iniciar TypeScript:

```
npx tsc --init
```

Mudar "target": "es2016" para "es2020" no arquivo `./tsconfig.json`:

```javascript
/* Language and Environment */
"target": "es2020", /* Set the JavaScript language version for emitted JavaScript and include compatible library declarations. */
```

Instalar o PRISMA:

```
npm install prisma --save-dev
```

Instalar o Prisma Client no projeto com o seguinte comando:

```
npm install @prisma/cliente
```

Iniciar o PRISMA:

```
npx prisma init
```

Configurar o arquivo `.env`:

```javascript
DATABASE_URL="mysql://youUser:yourPassword@yourHost:3306/yourDataBase"
```

> Onde:
> `youUser` é seu usuário de banco de dados,
> `yourPassword` é a senha,
> `yourHost` é o Host de sua hospedagem,
> `3306` é porta e
> `yourDataBase` é seu banco de dados.

Configurar no arquivo `./prisma/schema.prisma` o trecho de codigo:

> O valor de `provider` deve ser `mysql`, que é o tipo de banco de dados!

```javascript
datasource db {
  provider = "mysql"
  url      = env("DATABASE_URL")
}
```

Obter os modules:

```
npx prisma db pull
```

> O PRISMA irá obter a estrutura de todas as tabelas do seu banco de dados!

Exemplo abaixo:

[![Print de uma execução no Db Pull](https://github.com/systemboys/React_Codes/raw/main/Banco%20de%20Dados/Prisma/npx_prisma_db_pull.png "Print de uma execução no Db Pull")](https://github.com/systemboys/React_Codes/raw/main/Banco%20de%20Dados/Prisma/npx_prisma_db_pull.png "Print de uma execução no Db Pull")

Criar o arquivo `src/prisma.ts` e configure o seguinte código:

```javascript
import { PrismaClient } from "@prisma/client"

export const prisma = new PrismaClient ({
    log: ['query'],
})
```

Criar o arquivo `src/server.ts` e configure o seguinte código:

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

Criar o arquivo `src/routes.ts` e configure o seguinte código:

```javascript
import express from "express";

import { prisma } from './prisma';

export const routes = express.Router();

// ### Consultar 'admins' ###
routes.get('/admins', async (req, res) => {
    const admins = await prisma.admins.findMany()
    res.status(200).json(admins);
})

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

```
npm install tsx
```

No arquivo `package.json` editar o script deixando como no exemplo abaixo:

```javascript
"script": {
    "dev": "tsx watch src/server.ts"
}
```

Execute o servidor NPM:

```
npm run dev
```

[![Server executando](https://github.com/systemboys/React_Codes/raw/main/Banco%20de%20Dados/Prisma/npm_run_dev.png "Server executando")](https://github.com/systemboys/React_Codes/raw/main/Banco%20de%20Dados/Prisma/npm_run_dev.png "Server executando")

Com o `Insomnia`instalado, executar o GET para consultar os registros na tabela `admins` e gerar um `JSON`:

[![Consultar os dados com o Insomnia](https://github.com/systemboys/React_Codes/raw/main/Banco%20de%20Dados/Prisma/Insomnia_get_admins.png "Imagem de exemplo")](https://github.com/systemboys/React_Codes/raw/main/Banco%20de%20Dados/Prisma/Insomnia_get_admins.png "Consultar os dados com o Insomnia")

Com o `Insomnia`instalado, executar o POST para inserir um registro na tabela `admins` e gerar um `JSON`:

[![Registrar dados com o Insomnia](https://github.com/systemboys/React_Codes/raw/main/Banco%20de%20Dados/Prisma/insomnia_post_admins.png "Imagem de exemplo")](https://github.com/systemboys/React_Codes/raw/main/Banco%20de%20Dados/Prisma/insomnia_post_admins.png "Registrar dados com o Insomnia")

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](https://github.com/systemboys/React_Codes/tree/main/Banco%20de%20Dados#react-codes--banco-de-dados "Subir para o topo")

------------

Recriar instâncias nos módulos:

```javascript
npx prisma generate
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](https://github.com/systemboys/React_Codes/tree/main/Banco%20de%20Dados#react-codes--banco-de-dados "Subir para o topo")

------------
