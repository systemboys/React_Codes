# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Banco de Dados

- [Conexão com Banco de Dados MySQL](https://github.com/systemboys/React_Codes/tree/main/Banco%20de%20Dados#conex%C3%A3o-com-banco-de-dados-mysql "Conexão com Banco de Dados MySQL")
- [Inserir dados na tabela](https://github.com/systemboys/React_Codes/tree/main/Banco%20de%20Dados#inserir-dados-na-tabela "Inserir dados na tabela")
- [Atualizar dados da tabela](https://github.com/systemboys/React_Codes/tree/main/Banco%20de%20Dados#atualizar-dados-da-tabela "Atualizar dados da tabela")
- [Consultar os dados da tabela](https://github.com/systemboys/React_Codes/tree/main/Banco%20de%20Dados#consultar-os-dados-da-tabela "Consultar os dados da tabela")
- [Deletar dados da tabela](https://github.com/systemboys/React_Codes/tree/main/Banco%20de%20Dados#deletar-dados-da-tabela "Deletar dados da tabela")
- [Componentes no modo `Default Exports`](https://github.com/systemboys/React_Codes/... "Componentes no modo Default Exports")
- [Componentes no modo `Named Exports`](https://github.com/systemboys/React_Codes/... "Componentes no modo Named Exports")

------------

## Componentes no modo Default Exports

Arquivo `index.html`.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <link real="icon" type="image/svg+xml" href="/vite.svg">
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Vite + React</title>
  </head>
  <body>
    <div id="root"></div>
    <script type="module" src="/src/main.jsx"></script>
  </body>
</html>
```

Arquivo `main.jsx`.

```javascript
import React from 'react'
import ReactDOM from 'react-dom/client'
import App from './App'
import Test from './Test'

ReactDOM.createRoot(document.getElementById('root')).render(
  <React.StrictMode>
    <App />
    <Test />
  </React.StrictMode>
)
```

Arquivo `App.jsx`.

```javascript
export function App() {
  return (
    <h1>Hello World!</h1>
  )
}

export default App
```

Arquivo `Test.jsx`.

```javascript
function Test() {
    return (
      <h1>Content test...</h1>
    )
}

export default Test
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](https://github.com/systemboys/React_Codes/tree/main/Componentes%20e%20elementos#react-codes--componentes-e-elementos "Subir para o topo")

------------

## Componentes no modo Named Exports

Arquivo `index.html`.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <link real="icon" type="image/svg+xml" href="/vite.svg">
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Vite + React</title>
  </head>
  <body>
    <div id="root"></div>
    <script type="module" src="/src/main.jsx"></script>
  </body>
</html>
```

Arquivo `main.jsx`.

```javascript
import React from 'react'
import ReactDOM from 'react-dom/client'
import { App } from './App'

ReactDOM.createRoot(document.getElementById('root')).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
)
```

Arquivo `App.jsx`.

```javascript
import { Post } from './Post'

export function App() {
  return (
    <div>
      <Post />
      <Post />
      <Post />
      <Post />
      <Post />
      <Post />
    </div>
  )
}
```

Arquivo `Post.jsx`.

```javascript
export function Post() {
    return <p>Post</p>
}
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](https://github.com/systemboys/React_Codes/tree/main/Componentes%20e%20elementos#react-codes--componentes-e-elementos "Subir para o topo")

------------

## Conexão com Banco de Dados MySQL

Conteúdo...

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
