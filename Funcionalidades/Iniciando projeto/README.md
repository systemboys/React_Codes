# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Iniciando projeto

- [1 - Crie o seu projeto com o Vite](#1---crie-o-seu-projeto-com-o-vite "1 - Crie o seu projeto com o Vite")
- [2 - Entre no diretório do seu projeto project_name](#2---entre-no-diret%C3%B3rio-do-seu-projeto-project_name "2 - Entre no diretório do seu projeto project_name")
- [3 - Execute o projeto com o seguinte comando](#3---execute-o-projeto-com-o-seguinte-comando "3 - Execute o projeto com o seguinte comando")
- [4 - Configuração da porta no Vite](#4---configura%C3%A7%C3%A3o-da-porta-no-vite "4 - Configuração da porta no Vite")
- [5 - Rodar projeto em desenvolvimento na rede local](#5---rodar-projeto-em-desenvolvimento-na-rede-local "5 - Rodar projeto em desenvolvimento na rede local")
- [6 - Descrição do comando `npm run build` e sua função no processo de desenvolvimento de aplicações](#descri%C3%A7%C3%A3o-do-comando-npm-run-build-e-sua-fun%C3%A7%C3%A3o-no-processo-de-desenvolvimento-de-aplica%C3%A7%C3%B5es "Descrição do comando 'npm run build' e sua função no processo de desenvolvimento de aplicações")

---

## Iniciando projeto com Vite

### 1 - Crie o seu projeto com o Vite:

Com o npm lts instalado, crie seu projeto como Vite.

```bash
npm create vite@latest project_name
```

> Obs.: Selecione React e depois JavaScript ou TypyScript, dependendo do que deseja em seu projeto!

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--iniciando-projeto "Subir para o topo")

### 2 - Entre no diretório do seu projeto project_name:

Entre no diretório do seu novo projeto e instale as dependências npm.

```bash
npm i
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--iniciando-projeto "Subir para o topo")

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
[(&uarr;) Subir](#react-codes--iniciando-projeto "Subir para o topo")

---

### 4 - Configuração da porta no Vite:

Adicione a linha `server: {port: 3001}` no export do `vite.config.js` com sua porta definida:

```javascript
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
[(&uarr;) Subir](#react-codes--iniciando-projeto "Subir para o topo")

---

## 5 - Rodar projeto em desenvolvimento na rede local

[![Computadores em rede](https://github.com/systemboys/React_Codes/raw/main/Funcionalidades/Iniciando%20projeto/images/Computadores_em_rede.png "Computadores em rede")](https://github.com/systemboys/React_Codes/raw/main/Funcionalidades/Iniciando%20projeto/images/Computadores_em_rede.png "Computadores em rede")

Modificar o código do seu arquivo `package.json`, na configuração do script "dev", dentro do `"scripts": {...}`, adicionando a flag `--host 0.0.0.0` ficando da seguinte forma:

```javascript
...
"scripts": {
  "dev": "vite --host 0.0.0.0",
  ...
```

[![Configuração do Vite no package](https://github.com/systemboys/React_Codes/raw/main/Funcionalidades/Iniciando%20projeto/images/Configuracao_do_Vite_no_package.png "Configuração do Vite no package")](https://github.com/systemboys/React_Codes/raw/main/Funcionalidades/Iniciando%20projeto/images/Configuracao_do_Vite_no_package.png "Configuração do Vite no package")

>Note que no script "dev", adicionamos a flag "--host 0.0.0.0" para que o servidor possa ser acessado de outras máquinas na rede. Lembre-se também de executar o comando `npm install` na pasta do projeto para atualizar as dependências e então executar o comando "npm run dev" para rodar o servidor.

No arquivo `api.js` da sua API, modifique a sua URL trocando `localhost` para o IP da máquina que está rodando o servidor:

```javascript
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
[(&uarr;) Subir](#react-codes--iniciando-projeto "Subir para o topo")

---

## Descrição do comando 'npm run build' e sua função no processo de desenvolvimento de aplicações

O comando `npm run build` é usado para criar uma versão de produção da sua aplicação. Ele é usado comumente em projetos que usam o ReactJS, mas também pode ser usado em outros projetos Node.js.

Quando você executa o comando `npm run build`, ele realiza uma série de tarefas, como compilar o código, otimizar os arquivos, criar arquivos de manifesto e arquivos de configuração, além de gerar uma pasta `build` na raiz do seu projeto. Essa pasta contém uma versão otimizada do seu aplicativo que pode ser implantada em um servidor web.

Para usar o comando, basta navegar até o diretório do seu projeto usando o terminal e executar o comando `npm run build`. Depois que o processo for concluído, a pasta `build` será criada com o aplicativo otimizado.

```bash
npm run build
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--iniciando-projeto "Subir para o topo")

---
