# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes")

## Iniciando projeto

### *Sumário*

> Com o Vite

- [1 - Crie o seu projeto com o Vite](#1---crie-o-seu-projeto-com-o-vite "1 - Crie o seu projeto com o Vite")
- [2 - Entre no diretório do seu projeto project_name](#2---entre-no-diret%C3%B3rio-do-seu-projeto-project_name "2 - Entre no diretório do seu projeto project_name")
- [3 - Execute o projeto com o seguinte comando](#3---execute-o-projeto-com-o-seguinte-comando "3 - Execute o projeto com o seguinte comando")
- [4 - Configuração da porta no Vite](#4---configura%C3%A7%C3%A3o-da-porta-no-vite "4 - Configuração da porta no Vite")
- [5 - Rodar projeto em desenvolvimento na rede local](#5---rodar-projeto-em-desenvolvimento-na-rede-local "5 - Rodar projeto em desenvolvimento na rede local")
- [6 - Descrição do comando `npm run build` e sua função no processo de desenvolvimento de aplicações](#descri%C3%A7%C3%A3o-do-comando-npm-run-build-e-sua-fun%C3%A7%C3%A3o-no-processo-de-desenvolvimento-de-aplica%C3%A7%C3%B5es "Descrição do comando 'npm run build' e sua função no processo de desenvolvimento de aplicações")

> Padrão com o Node

- [Configuração de Projeto Node.js com Express, TypeScript e Prisma](#configura%C3%A7%C3%A3o-de-projeto-nodejs-com-express-typescript-e-prisma "Configuração de Projeto Node.js com Express, TypeScript e Prisma")
- [Configuração do MySQL via Docker Compose](# "Configuração do MySQL via Docker Compose")

---

## Iniciando projeto com Vite

### 1 - Crie o seu projeto com o Vite:

Com o npm lts instalado, crie seu projeto como Vite.

```bash
npm create vite@latest project_name
```

> Obs.: Selecione React e depois JavaScript ou TypyScript, dependendo do que deseja em seu projeto!

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

### 2 - Entre no diretório do seu projeto project_name:

Entre no diretório do seu novo projeto e instale as dependências npm.

```bash
npm i
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")


### 3 - Execute o projeto com o seguinte comando:

```bash
npm run dev
```

> Após executar o projeto, logo lhe apresentará o endereço localhost com a parta selecionada como no exemplo abaixo:

```bash
  VITE v3.2.3  ready in 772 ms

  ➜  Local:   http://localhost:5173/
  ➜  Network: use --host to expose
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

### 4 - Configuração da porta no Vite:

Adicione a linha `server: {port: 3001}` no export do `vite.config.js` com sua porta definida:

```jsx
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'

// https://vitejs.dev/config/
export default defineConfig({
  plugins: [react()],
  server: {port: 3001}
})
```

Para deixar de ser selecionada automaticamente, a imagem abaixo mostra o exemplo:

[![Resultado da execução do servidor com a nova porta](https://github.com/systemboys/React_Codes/raw/main/Funcionalidades/Iniciando%20projeto/images/Configuracao_da_porta_no_Vite.png "Resultado da execução do servidor com a nova porta")](https://github.com/systemboys/React_Codes/raw/main/Funcionalidades/Iniciando%20projeto/images/Configuracao_da_porta_no_Vite.png "Resultado da execução do servidor com a nova porta")

Atalhos:

- Pressione `r` para reiniciar o servidor
- Pressione `u` para mostrar o URL do servidor
- Pressione `o` para abrir no navegador
- Pressione `q` para sair

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

## 5 - Rodar projeto em desenvolvimento na rede local

[![Computadores em rede](https://github.com/systemboys/React_Codes/raw/main/Funcionalidades/Iniciando%20projeto/images/Computadores_em_rede.png "Computadores em rede")](https://github.com/systemboys/React_Codes/raw/main/Funcionalidades/Iniciando%20projeto/images/Computadores_em_rede.png "Computadores em rede")

Modificar o código do seu arquivo `package.json`, na configuração do script "dev", dentro do `"scripts": {...}`, adicionando a flag `--host 0.0.0.0` ficando da seguinte forma:

```jsx
...
"scripts": {
  "dev": "vite --host 0.0.0.0",
  ...
```

[![Configuração do Vite no package](https://github.com/systemboys/React_Codes/raw/main/Funcionalidades/Iniciando%20projeto/images/Configuracao_do_Vite_no_package.png "Configuração do Vite no package")](https://github.com/systemboys/React_Codes/raw/main/Funcionalidades/Iniciando%20projeto/images/Configuracao_do_Vite_no_package.png "Configuração do Vite no package")

>Note que no script "dev", adicionamos a flag "--host 0.0.0.0" para que o servidor possa ser acessado de outras máquinas na rede. Lembre-se também de executar o comando `npm install` na pasta do projeto para atualizar as dependências e então executar o comando "npm run dev" para rodar o servidor.

No arquivo `api.js` da sua API, modifique a sua URL trocando `localhost` para o IP da máquina que está rodando o servidor:

```jsx
...
export const Api = axios.create({
    baseURL: 'http://10.0.0.102:3333',
    ...
```

[![Arquivo api.js de sua API](https://github.com/systemboys/React_Codes/raw/main/Funcionalidades/Iniciando%20projeto/images/Arquivo_api_de_sua_API.png "Arquivo api.js de sua API")](https://github.com/systemboys/React_Codes/raw/main/Funcionalidades/Iniciando%20projeto/images/Arquivo_api_de_sua_API.png "Arquivo api.js de sua API")

Se seu servidor estiver rodando em Linux, libere as portas do seu `Front-end` e da sua `API` com o seuignte comando no terminal:

```bash
sudo iptables -A INPUT -p tcp --dport 5173 -j ACCEPT
```

> Liberada a porta 5173.

```bash
sudo iptables -A INPUT -p tcp --dport 3333 -j ACCEPT
```

> Liberada a porta 3333.

```bash
sudo iptables -S
```

> O último comando verifica o status do `iptables` mostrando as protas aceitas.

Dado o comando `sudo iptables` será exposto o status da seguinte forma:

```bash
root@debian:~# sudo iptables -S
-P INPUT ACCEPT
-P FORWARD ACCEPT
-P OUTPUT ACCEPT
-A INPUT -p tcp -m tcp --dport 5173 -j ACCEPT
-A INPUT -p tcp -m tcp --dport 3333 -j ACCEPT
```

[![Dado os comandos no terminal](https://github.com/systemboys/React_Codes/raw/main/Funcionalidades/Iniciando%20projeto/images/Comandos_liberar_portas.png "Dado os comandos no terminal")](https://github.com/systemboys/React_Codes/raw/main/Funcionalidades/Iniciando%20projeto/images/Comandos_liberar_portas.png "Dado os comandos no terminal")

Nas máquinas que estão na mesma rede, abrir seu navegador e digitar a URL do seu projeto:

[![URL no navegador da máquina local](https://github.com/systemboys/React_Codes/raw/main/Funcionalidades/Iniciando%20projeto/images/Projeto_em_rede_local.png "URL no navegador da máquina local")](https://github.com/systemboys/React_Codes/raw/main/Funcionalidades/Iniciando%20projeto/images/Projeto_em_rede_local.png "URL no navegador da máquina local")

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

## Descrição do comando 'npm run build' e sua função no processo de desenvolvimento de aplicações

O comando `npm run build` é usado para criar uma versão de produção da sua aplicação. Ele é usado comumente em projetos que usam o ReactJS, mas também pode ser usado em outros projetos Node.js.

Quando você executa o comando `npm run build`, ele realiza uma série de tarefas, como compilar o código, otimizar os arquivos, criar arquivos de manifesto e arquivos de configuração, além de gerar uma pasta `build` na raiz do seu projeto. Essa pasta contém uma versão otimizada do seu aplicativo que pode ser implantada em um servidor web.

Para usar o comando, basta navegar até o diretório do seu projeto usando o terminal e executar o comando `npm run build`. Depois que o processo for concluído, a pasta `build` será criada com o aplicativo otimizado.

```bash
npm run build
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

## Configuração de Projeto Node.js com Express, TypeScript e Prisma

Inicializar um novo projeto Node.js com o arquivo package.json preenchido automaticamente com valores padrão, sem a necessidade de interação do usuário.

```bash
npm init -y
```

Instalar o pacote 'express' no seu projeto. O Express é um framework popular para construir aplicativos da web com Node.js.

```bash
npm i express
```

Atualizando o próprio npm para a versão 10.2.5 de forma global (-g) caso esteja desatualizado.

```bash
npm install -g npm@10.2.5
```

Instalar o TypeScript (um superset de JavaScript que adiciona tipagem estática ao código), o ts-node (que permite executar arquivos TypeScript diretamente) e os tipos de definição para o Node.js, todos como dependências de desenvolvimento (--save-dev).

```bash
npm install typescript ts-node @types/node --save-dev
```

Inicializar o TypeScript no seu projeto, criando um arquivo de configuração 'tsconfig.json' que permite personalizar as opções do compilador.

```bash
npx tsc --init
```

Instalar o Prisma, uma ferramenta ORM (Object-Relational Mapping) para bancos de dados, como uma dependência de desenvolvimento.

```bash
npm install prisma --save-dev
```

Instalar o cliente Prisma no seu projeto. O '@prisma/client' é usado para interagir com o banco de dados por meio do Prisma.

```bash
npm install @prisma/client
```

Inicializar o Prisma no seu projeto, criando a estrutura de diretórios e arquivos necessários para gerenciar os modelos de banco de dados usando o Prisma.

```bash
npx prisma init
```

Estes comandos são usados em um fluxo típico de configuração de um projeto Node.js que utiliza Express, TypeScript e Prisma para lidar com a lógica da aplicação e interações com o banco de dados.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

## Configuração do MySQL via Docker Compose

Instruções no código YAML para configurar um serviço de banco de dados MySQL usando o Docker Compose:

1. **Crie um arquivo YAML:** Crie um arquivo com a extensão `.yml` ou `.yaml` (por exemplo, `docker-compose.yml`).

2. **Defina a versão do Docker Compose:** Especifique a versão do Docker Compose no início do arquivo YAML.

   ```yaml
   version: '3.3'
   ```

3. **Configure o serviço do banco de dados:**

   ```yaml
   services:
     database:
       image: mysql:5.7
       container_name: mysql
       restart: always
       environment:
         MYSQL_ROOT_USER: 'root'
         MYSQL_DATABASE: 'mark01'
         MYSQL_USER: 'user'
         MYSQL_PASSWORD: 'root'
         MYSQL_ROOT_PASSWORD: 'root'
       ports:
         - '3306:3306'
       expose:
         - '3306'
       volumes:
         - './.mysql-data/db:/var/lib/mysql'
   ```

4. **Salve o arquivo:** Guarde o arquivo com as configurações que você acabou de definir.

5. **Execute o Docker Compose:** No terminal ou prompt de comando, navegue até o diretório onde o arquivo YAML está localizado e execute o seguinte comando para iniciar o serviço do banco de dados MySQL:

   ```bash
   docker-compose up -d
   ```

   Isso iniciará o contêiner do MySQL de acordo com as configurações especificadas no arquivo YAML.

Essas instruções fornecem a estrutura básica para configurar um serviço de banco de dados MySQL utilizando o Docker Compose, permitindo que você inicialize e gerencie o contêiner facilmente.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---
