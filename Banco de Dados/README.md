# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Banco de Dados

- [Conectar Banco de Dados `MySQL` com ORM `PRISMA`](https://github.com/systemboys/React_Codes/tree/main/Banco%20de%20Dados#conectar-banco-de-dados-mysql-com-orm-prisma "Conectar Banco de Dados MySQL com ORM PRISMA")
- [Inserir dados na tabela](https://github.com/systemboys/React_Codes/tree/main/Banco%20de%20Dados#inserir-dados-na-tabela "Inserir dados na tabela")
- [Atualizar dados da tabela](https://github.com/systemboys/React_Codes/tree/main/Banco%20de%20Dados#atualizar-dados-da-tabela "Atualizar dados da tabela")
- [Consultar os dados da tabela](https://github.com/systemboys/React_Codes/tree/main/Banco%20de%20Dados#consultar-os-dados-da-tabela "Consultar os dados da tabela")
- [Deletar dados da tabela](https://github.com/systemboys/React_Codes/tree/main/Banco%20de%20Dados#deletar-dados-da-tabela "Deletar dados da tabela")

------------

## Conectar Banco de Dados MySQL com ORM PRISMA

Criar um novo projeto e iniciar o servidor:

> Crie um novo projeto fora do diretório do seu projeto o qual quer conectá-lo. Na verdade, você estará criando uma API para conectar seu projeto!

```
npm init -y
```

Criar o arquivo `server.ts`:

```
./src/server.ts
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

```javscript
DATABASE_URL="mysql://youUser:yourPassword@yourHost:3306/yourDataBase"
```

> Onde:
> `youUser` é seu usuário de banco de dados,
> `yourPassword` é a senha do seu banco,
> `yourHost` é o Host de sua hospedagem,
> `3306` é porta do banco de dados e
> `yourDataBase` é seu banco de dados.

Configurar no arquivo `./prisma/schema.prisma` o trecho de codigo:

```javscript
datasource db {
  provider = "mysql"
  url      = env("DATABASE_URL")
}
```

Obter os modules:

```
npx prisma db pull
```

> O PRISMA irá obter a estrutura de todas as tabelas do banco de dados!

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](https://github.com/systemboys/React_Codes/tree/main/Banco%20de%20Dados#react-codes--banco-de-dados "Subir para o topo")

------------

## Inserir dados na tabela

Conteúdo...

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](https://github.com/systemboys/React_Codes/tree/main/Banco%20de%20Dados#react-codes--banco-de-dados "Subir para o topo")

------------

## Atualizar dados da tabela

Conteúdo...

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](https://github.com/systemboys/React_Codes/tree/main/Banco%20de%20Dados#react-codes--banco-de-dados "Subir para o topo")

------------

## Consultar os dados da tabela

Conteúdo...

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](https://github.com/systemboys/React_Codes/tree/main/Banco%20de%20Dados#react-codes--banco-de-dados "Subir para o topo")

------------

## Deletar dados da tabela

Conteúdo...

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](https://github.com/systemboys/React_Codes/tree/main/Banco%20de%20Dados#react-codes--banco-de-dados "Subir para o topo")

------------
