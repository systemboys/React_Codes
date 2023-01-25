# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Iniciando projeto

- [1 - Crie o seu projeto com o Vite](https://github.com/systemboys/React_Codes/tree/main/Iniciando%20projeto#1---crie-o-seu-projeto-com-o-vite "1 - Crie o seu projeto com o Vite")
- [2 - Entre no diretório do seu projeto project_name](https://github.com/systemboys/React_Codes/tree/main/Iniciando%20projeto#2---entre-no-diret%C3%B3rio-do-seu-projeto-project_name "2 - Entre no diretório do seu projeto project_name")
- [3 - Execute o projeto com o seguinte comando](https://github.com/systemboys/React_Codes/tree/main/Iniciando%20projeto#3---execute-o-projeto-com-o-seguinte-comando "3 - Execute o projeto com o seguinte comando")

------------

## Iniciando projeto com Vite

### 1 - Crie o seu projeto com o Vite:

Com o npm lts instalado, crie seu projeto como Vite.

```
npm create vite@latest project_name
```

> Obs.: Selecione React e depois JavaScript ou TypyScript, dependendo do que deseja em seu projeto!

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](https://github.com/systemboys/React_Codes/tree/main/Iniciando%20projeto#react-codes--iniciando-projeto "Subir para o topo")

### 2 - Entre no diretório do seu projeto project_name:

Instale as dependências npm.

```
npm i
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](https://github.com/systemboys/React_Codes/tree/main/Iniciando%20projeto#react-codes--iniciando-projeto "Subir para o topo")

### 3 - Execute o projeto com o seguinte comando:

```
npm run dev
```

> Após executar o projeto, logo lhe apresentará o endereço localhost com a parta selecionada como no exemplo abaixo:

```
  VITE v3.2.3  ready in 772 ms

  ➜  Local:   http://localhost:5173/
  ➜  Network: use --host to expose
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](https://github.com/systemboys/React_Codes/tree/main/Iniciando%20projeto#react-codes--iniciando-projeto "Subir para o topo")

------------

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

[![Imagem de exemplo](https://site.com/img/exemplo.png "Imagem de exemplo")](http://link.com "Imagem de exemplo")

Atalhos:
   Pressione `r` para reiniciar o servidor
   Pressione `u` para mostrar o URL do servidor
   Pressione `o` para abrir no navegador
   Pressione `q` para sair

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](https://github.com/systemboys/React_Codes/tree/main/Iniciando%20projeto#react-codes--iniciando-projeto "Subir para o topo")

------------
