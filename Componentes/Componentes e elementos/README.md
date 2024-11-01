# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes")

## Componentes e elementos

### *Sumário*

> Diversos
- [Componentes no modo `Default Exports`](#componentes-no-modo-default-exports "Componentes no modo Default Exports")
- [Componentes no modo `Named Exports`](#componentes-no-modo-named-exports "Componentes no modo Named Exports")
- [`Formulário` responsívo com React-Bootstrap](#formul%C3%A1rio-respons%C3%ADvo-com-react-bootstrap "Formulário responsívo com React-Bootstrap")
  - [`Máscara` nos campos](#m%C3%A1scara-nos-campos "Máscara nos campos")
  - [Enviando um `formulário`](#enviando-um-formul%C3%A1rio "Enviando um formulário")
  - [`Campos editáveis` no formulário dentro de um componente](#campos-edit%C3%A1veis-no-formul%C3%A1rio-dentro-de-um-componente "Campos editáveis no formulário dentro de um componente")
  - [`Validar` e `enviar` os `campos` do formulário](#validar-e-enviar-os-campos-do-formul%C3%A1rio "Validar e enviar os campos do formulário")
  - [`Validar` campo de `email` com JavaScript no ReactJS](#validar-campo-de-email-com-javascript-no-reactjs "Validar campo de email com JavaScript no ReactJS")
  - [`Resetar` campos do `formulário`](#resetar-campos-do-formul%C3%A1rio "Resetar campos do formulário")
  - [Instalar e utilizar o `CKEditor 5` no ReactJS](#instalar-e-utilizar-o-ckeditor-5-no-reactjs "Instalar e utilizar o CKEditor 5 no ReactJS")
  - [`Envio` dos `dados` para a `API` do PRISMA](#envio-dos-dados-para-a-api-do-prisma "Envio dos dados para a API do PRISMA")
  - [Formulário de `Seleção Hierárquica` com React](#formul%C3%A1rio-de-sele%C3%A7%C3%A3o-hier%C3%A1rquica-com-react "Formulário de Seleção Hierárquica com React")
- [`Abas` horizontais com React-Bootstrap](#abas-horizontais-com-react-bootstrap "Abas horizontais com React-Bootstrap")
- [`Lista simples` com React-Bootstrap](#lista-simples-com-react-bootstrap "Lista simples com React-Bootstrap")
- [Implantação do `DataTables`](#implanta%C3%A7%C3%A3o-do-datatables "Implantação do DataTables")
  - [Garantir que script `DataTables` seja executado corretamente no componente](#garantir-que-script-datatables-seja-executado-corretamente-no-componente "Garantir que script DataTables seja executado corretamente no componente")
  - [DataTables com o `ORM Prisma` (resolvendo renderização)](#datatables-com-o-orm-prisma-resolvendo-renderiza%C3%A7%C3%A3o "DataTables com o ORM Prisma (resolvendo renderização)")
- [`Responsive grids` com React-Bootstrap](#responsive-grids-com-react-bootstrap "Responsive grids com React-Bootstrap")
- [`Buttons` com React-Bootstrap](#buttons-com-react-bootstrap "Buttons com React-Bootstrap")
- [Utilizando o `CSS Modules` do React](#utilizando-o-css-modules-do-react "Utilizando o CSS Modules do React")
- [Interfaces com `guias` com React-Bootstrap](#interfaces-com-guias-com-react-bootstrap "Interfaces com guias com React-Bootstrap")
- [Itens `acionáveis` com React-Bootstrap](#itens-acion%C3%A1veis-com-react-bootstrap "Itens acionáveis com React-Bootstrap")
- [`Posicionamento` com React-Bootstrap](#posicionamento-com-react-bootstrap "Posicionamento com React-Bootstrap")
- [Mais opções com `Paginação` com React-Bootstrap](#mais-op%C3%A7%C3%B5es-com-pagina%C3%A7%C3%A3o-com-react-bootstrap "Mais opções com Paginação com React Bootstrap")
- [`Espaços reservados` com React-Bootstrap](#espa%C3%A7os-reservados-com-react-bootstrap "Espaços reservados com React Bootstrap")
- [`Barra com animação` com React-Bootstrap](#barra-com-animação-com-react-bootstrap "Barra com animação com React-Bootstrap")
- [Incrementando `React-FontAwesome`](#incrementando-react-fontawesome "Incrementando React-FontAwesome")
- [`Impedir` a exibição do `menu de contexto` (click inverso) dentro do componente](#impedir-a-exibi%C3%A7%C3%A3o-do-menu-de-contexto-click-inverso-dentro-do-componente "Impedir a exibição do menu de contexto (click inverso) dentro do componente")

> Fenestra
- [Gerenciamento de Janelas Flutuantes com Fenestra: Passando Propriedades para Controle de Fechamento Dinâmico (Resolvido)](#gerenciamento-de-janelas-flutuantes-com-fenestra-passando-propriedades-para-controle-de-fechamento-din%C3%A2mico-resolvido "Gerenciamento de Janelas Flutuantes com Fenestra: Passando Propriedades para Controle de Fechamento Dinâmico (Resolvido)")
  > Passando a propriedade Fenestra para o compoente que ele carregará!
- [Passagem de Propriedades com props e Desestruturação em Componentes React](#passagem-de-propriedades-com-props-e-desestrutura%C3%A7%C3%A3o-em-componentes-react "Passagem de Propriedades com props e Desestruturação em Componentes React")
  > Passando a propriedade `fenestra` para o componente `DemoListings1` da mesma forma que você faria com qualquer outra propriedade, mesmo que ele esteja usando `props`.
- [Controle Condicional de Fechamento de Janela no Formulário](#controle-condicional-de-fechamento-de-janela-no-formul%C3%A1rio "Controle Condicional de Fechamento de Janela no Formulário")
  > Implementação a funcionalidade onde a janela só será fechada se o botão "Fechar ao concluir" estiver marcado.

---

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

```jsx
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

```jsx
function App() {
  return (
    <h1>Hello World!</h1>
  )
}

export default App
```

Arquivo `Test.jsx` com o componente em modo Default Exports.

```jsx
function Test() {
    return (
      <h1>Content test...</h1>
    )
}

export default Test
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

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

```jsx
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

```jsx
import { Post } from './Post'

export function App() {
  return (
    <div>
      <Post />
    </div>
  )
}
```

Arquivo `Post.jsx` com o componente em modo Named Exports.

```jsx
export function Post() {
    return <p>Post</p>
}
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

## Formulário responsívo com React-Bootstrap

[![Formulário de exemplo](https://github.com/systemboys/React_Codes/raw/main/Componentes/Componentes%20e%20elementos/images/Formulario_responsivo_com_React-Bootstrap.png "Formulário de exemplo")](https://github.com/systemboys/React_Codes/raw/main/Componentes/Componentes%20e%20elementos/images/Formulario_responsivo_com_React-Bootstrap.png "Formulário de exemplo")

Se o `React-Bootstrap` não estiver instalado no `npm`, execute o seguinte comando no terminal:

```bash
npm install react-bootstrap bootstrap
```

Importar os seguintes componentes:

```jsx
// Componentes do formulário.
import Container from 'react-bootstrap/Container';
import Button from 'react-bootstrap/Button';
import Col from 'react-bootstrap/Col';
import Form from 'react-bootstrap/Form';
import Row from 'react-bootstrap/Row';
```

Ou:

```jsx
// Componentes do formulário.
import {
    Container,
    Button,
    Col,
    Form,
    Row
} from 'react-bootstrap';
```

> Como todos os elementos acima vêm do `react-bootstrap`, podem ser colodos dentro de chaves `{...}` separados por virgula (,) fazendo uma desestruturação.

Elementos do formulário modelo:

```jsx
<Container>
    <Form>
        <Row className="mb-2">
            <Col sm={6}>
                <Form.Group className="mb-3" as={Col} controlId="formGridEmail">
                    <Form.Label>Email principal</Form.Label>
                    <Form.Control
                      type="email"
                      size="sm"
                      placeholder="Email do sistema..."
                    />
                </Form.Group>
            </Col>
            <Col sm={6}>
                <Form.Group className="mb-3" as={Col} controlId="formGridTitle">
                    <Form.Label>Título do sistema</Form.Label>
                    <Form.Control
                      type="text"
                      size="sm"
                      placeholder="Um título..."
                    />
                </Form.Group>
            </Col>
            <Col sm={12}>
                <Form.Group className="mb-3" as={Col} controlId="formGridState">
                    <Form.Label>Estado</Form.Label>
                    <Form.Select
                      size="sm"
                    >
                        <option value="">&raquo; Selecione &laquo;</option>
                        <option value="SP">São Paulo</option>
                        <option value="RJ">Rio de Janeiro</option>
                        <option value="MG">Minas Gerais</option>
                    </Form.Select>
                </Form.Group>
            </Col>
            <Col sm={12}>
                <Form.Group className="mb-3" controlId="formGridAboutSystem">
                    <Form.Label>Sobre o sistema</Form.Label>
                    <Form.Control
                      as="textarea"
                      size="sm"
                      rows={8}
                      placeholder="Escreva algo sobre o sistema..."
                    />
                </Form.Group>
            </Col>
        </Row>
        <Button variant="primary" type="submit">
            Enviar
        </Button>
    </Form>
</Container>
```

Caso você esteja utilizando CSS Modules e deseja que o botão `imput` seja fixado abaixo do formulário e rolar apenas o conteúdo do formulário com a barra de rolagem, segue o CSS:

```css
@media screen and (min-width: 990px) {
    .formBody {
        overflow: auto;
        height: 362.5px;
        border-bottom: 1px solid rgba(255,255,255,.2);
    }
}
```

> Obs.: Lembrando que o `@media` está definindo que as regras do estilo CSS serão aplicadas apenas quando o screen for no mínimo `990px` ou superior!

Adicione a classe no elemento HTML:

```jsx
...
import styles from './styles.module.css';

export function YourComponent() {
    return (
        <Container>
            <Form>
                <Row className={`${styles.formBody} mb-2`}>
                    <Col sm={6}>
                        ...
```

> Note que foi adicionado em `className="mb-2"` a classe do CSS Modules ficando assim: `${styles.formBody} mb-2`.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

## Máscara nos campos

Para aplicar uma máscara no input do campo CPF, podemos utilizar uma biblioteca de formatação de strings, como o react-input-mask.

Para utilizá-lo, primeiro precisamos instalá-lo:

```bash
npm install react-input-mask
```

Em seguida, podemos importá-lo em nosso componente e utilizá-lo no input da seguinte forma:

```jsx
import React, { useState } from 'react';
import InputMask from 'react-input-mask';

function MyForm() {
  const [cpf, setCpf] = useState('');

  function handleCpfChange(event) {
    setCpf(event.target.value);
  }

  return (
    <form>
      <label htmlFor="cpf">CPF:</label>
      <InputMask
        mask="999.999.999-99"
        id="cpf"
        value={cpf}
        onChange={handleCpfChange}
      />
    </form>
  );
}
```

No exemplo acima, importamos o InputMask e utilizamos dentro do input de CPF. Definimos a propriedade mask com a máscara desejada e utilizamos as props value e onChange para lidar com o estado do componente.

Dessa forma, o input será formatado de acordo com a máscara definida, e o valor digitado pelo usuário será atualizado no estado do componente.

Se você já tem o campo e não quer mexer na sua estrutura, você pode envolver o seu <Form.Control ... /> com o componente InputMask, passando a máscara desejada como uma string de formatação. O código ficaria assim:

```jsx
<Form.Group className="mb-3" as={Col} controlId="formGridCPF">
  <Form.Label>CPF</Form.Label>
  <InputMask
    mask="999.999.999-99"
    maskChar="_"
    value={individual_registration}
    onChange={(e) => setIndividual_registration(e.target.value)}
    ref={individual_registrationInputRef}
  >
    {() => (
      <Form.Control
        type="text"
        size="sm"
        placeholder="___.___.___-__"
      />
    )}
  </InputMask>
</Form.Group>
```

Você pode usar o react-input-mask para adicionar uma máscara ao campo de data. Por exemplo, se você quiser que o campo de data seja formatado como dd/mm/yyyy, você pode usar a seguinte sintaxe:

```jsx
<InputMask
  mask="99/99/9999"
  placeholder="dd/mm/yyyy"
  value={date}
  onChange={(e) => setDate(e.target.value)}
/>
```

Nesse caso, o campo de entrada aceitará somente números e preencherá automaticamente com barras. Lembre-se de que você ainda precisará validar a entrada do usuário para garantir que seja uma data válida.

Basta substituir o valor da propriedade mask para o valor da máscara de data desejada e atualizar a propriedade placeholder para exibir a máscara de data correspondente. Aqui está um exemplo:

```jsx
<Form.Group className="mb-3" as={Col} controlId="formGridDataRegistro">
  <Form.Label>Data/Regist.</Form.Label>
  <InputMask
    mask="99/99/9999"
    maskChar="_"
    value={registered_date}
    onChange={(e) => setRegistered_date(e.target.value)}
    ref={registered_dateInputRef}
  >
    {() => (
      <Form.Control
        type="text"
        size="sm"
        placeholder="__/__/____"
      />
    )}
  </InputMask>
</Form.Group>
```

Da mesma forma, é utilizado para o campo de horas:

```jsx
<Form.Group className="mb-3" as={Col} controlId="formGridHoraRegistro">
  <Form.Label>Hora/Regist.</Form.Label>
  <InputMask
    mask="99:99:99"
    maskChar="_"
    value={registered_time}
    onChange={(e) => setRegistered_time(e.target.value)}
    ref={registered_timeInputRef}
  >
    {() => (
      <Form.Control
        type="text"
        size="sm"
        placeholder="__:__:__"
      />
    )}
  </InputMask>
</Form.Group>
```

Lembre-se de importar o componente InputMask e definir os estados e as referências de acordo com o campo de hora.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

## Enviando um formulário

Importar o `useState` do React para armazenarmos os valores:

```jsx
import React, { useState } from 'react';
```

Dentro do seu componente, antes do retorno, devem ser declarados os valores, deixando-os vazios e, deverá ter também uma `Arrow Function` para interceptar o evento do Submit do formulário:

> Quando não há `action=""` ou quando há mas não é definido nenhum valor, ao enviar o submit, o usuário será direcionado para a mesma tela do formulário (comportamento típico do form). A ação do envio deverá ser mapeada e interceptada.

```jsx
// Declaração dos valores dos campos.
const [email, setEmail] = useState("");
const [username, setUsername] = useState("");
const [password, setPassword] = useState("");

// Interceptar o evento de submit.
async function handleSubmitLogin(e) {
    e.preventDefault();

    // Exibir no console os valores obitidos nos campos.
    console.log("submit", { email, username, password });
}
```

> Na função, o (e) em `async function handleSubmitLogin(e) {...` pode ser colocado (e), (ev) ou (event)!

A função deverá ser colocada no `<form>...</form>` no evento `onSubmit={}`:

```jsx
<form onSubmit={handleSubmitLogin}>
```

Agora os geters e os seters deverão ser ligados nos campos:

```jsx
<input
    type="email"
    name="email"
    id="email"
    placeholder="Email principal"
    value={email}
    onChange={(e) => setEmail(e.target.value)}
/>
<input
    type="text"
    name="username"
    id="username"
    placeholder="Usuário"
    value={username}
    onChange={(e) => setUsername(e.target.value)}
/>
<input
    type="password"
    name="password"
    id="password"
    placeholder="Senha"
    value={password}
    onChange={(e) => setPassword(e.target.value)}
/>
```

> O valor de leitura e a função que define o valor são colocados no `value={}` e no `onChange={}`.

> Os valores desses campos estão na propriedade `.value` em `setPassword(e.target.value)`.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

## Campos editáveis no formulário dentro de um componente

Como definir um valor em um campo onde ele se torna editável dentro de um componente?

> Para definir um valor padrão para um campo `type="text"` em React, você pode definir o valor inicial do estado que irá controlar o valor do campo. Você pode usar o hook `useState` para definir o estado inicial do valor do campo, assim como a função para atualizá-lo quando necessário.

> Aqui está um exemplo de como definir um valor padrão para um campo de texto usando o componente `Form.Control` do React Bootstrap:

```jsx
import { useState } from 'react';
import { Form, Col } from 'react-bootstrap';

function MyForm() {

  // Declaração dos valores dos campos.
  const [systemTitle, setSystemTitle] = useState('Meu título padrão');

  return (
    <Form>
      <Form.Group className="mb-3" as={Col} controlId="formGridTitle">
        <Form.Label>Título do sistema</Form.Label>
        <Form.Control
          type="text"
          size="sm"
          value={systemTitle}
          onChange={(event) => setSystemTitle(event.target.value)}
          placeholder="Um título..."
        />
      </Form.Group>
    </Form>
  );
}
```

> Neste exemplo, o valor padrão do campo de texto é definido como `'Meu título padrão'` através do estado inicial `systemTitle`. Em seguida, o valor é controlado pelo estado usando a propriedade value do componente `Form.Control`.

> A função `onChange` é usada para atualizar o valor do estado `systemTitle` sempre que o usuário digita algo no campo. Dessa forma, o valor do campo será atualizado conforme o usuário digita e pode ser usado em outras partes do seu código.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

## Validar e enviar os campos do formulário

Para verificar se os campos estão vazios, você pode usar uma declaração condicional `if` para verificar se as variáveis de estado correspondentes estão vazias ou não antes de enviar o formulário. Você pode fazer algo assim:

Inportar o `useRef` do React.

```jsx
import React, { useState, useRef } from "react";
```

> Aqui está um exemplo de como você pode definir o foco nos campos de entrada criando referências para setar o focus.

```jsx
// Declaração dos valores dos campos.
const [client_type, setClient_type] = useState("");
const [full_name, setFull_name] = useState("");
const [general_record, setGeneral_record] = useState("");
const [individual_registration, setIndividual_registration] = useState("");

// Referências para os campos de entrada para setar o focus.
const client_typeInputRef = useRef(null);
const full_nameInputRef = useRef(null);
const general_recordInputRef = useRef(null);
const individualRegistrationInputRef = useRef(null);

// Interceptar o evento de submit.
async function handleSubmitCustomerRegistration(e) {
  e.preventDefault();

  // Verificar se o campo "Tipo de pessoa" está vazio.
  if (client_type.trim() === '') {
    client_typeInputRef.current.focus();
    alert('Informe o campo "Tipo de pessoa"!');
    return;
  }
  // Verificar se o campo "Nome completo" está vazio.
  if (full_name.trim() === '') {
    full_nameInputRef.current.focus();
    alert('Informe o campo "Nome completo"!');
    return;
  }
  // Verificar se o campo "RG" está vazio.
  if (general_record.trim() === '') {
    general_recordInputRef.current.focus();
    alert('Informe o campo "RG"!');
    return;
  }
  // Verificar se o campo "CPF" está vazio.
  if (individual_registration.trim() === '') {
    individual_registrationInputRef.current.focus();
    alert('Informe o campo "CPF"!');
    return;
  }

  // Envia os dados do formulário se todos os campos obrigatórios estiverem preenchidos.
  console.log("submit: ", {client_type, full_name, general_record, individual_registration});
}
```

Nos campos devem ser atribuídas suas referências `ref={full_nameInputRef}`:

```jsx
...
<input
  type="text"
  value={full_name}
  onChange={(e) => setFull_name(e.target.value)}
  ref={full_nameInputRef}
/>
...
```

Nesse exemplo, você pode ver que o código verifica se o campo "Nome completo" está vazio usando o método `trim()` para remover os espaços em branco em ambos os lados da string e depois comparando com uma string vazia. Se o campo estiver vazio, exibirá um alerta e a função retornará, impedindo que o formulário seja enviado. Em seguida, é feita uma verificação semelhante para outros campos obrigatórios, dependendo do tipo de cliente selecionado. Se todos os campos obrigatórios estiverem preenchidos, o formulário será enviado e os valores dos campos serão exibidos no console.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

## Validar campo de email com JavaScript no ReactJS

Para validar um campo de e-mail em ReactJS usando JavaScript, você pode usar expressões regulares (regex) para verificar se o formato do e-mail é válido. Você pode adicionar uma função de validação ao seu componente que verifica se o valor do campo de e-mail corresponde a um padrão de e-mail válido. Aqui está um exemplo de como fazer isso:

```jsx
import React, { useState } from 'react';

function YourComponent() {
  const [email, setEmail] = useState('');
  const [isValidEmail, setIsValidEmail] = useState(false);

  function validateEmail(value) {
    const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
    return emailRegex.test(value);
  }

  function handleChange(event) {
    const value = event.target.value;
    setEmail(value);
    setIsValidEmail(validateEmail(value));
  }

  return (
    <div>
      <label htmlFor="email">E-mail:</label>
      <input
        type="email"
        id="email"
        name="email"
        value={email}
        onChange={handleChange}
        className={isValidEmail ? 'valid' : 'invalid'}
      />
      {isValidEmail ? null : <div className="error">E-mail inválido</div>}
    </div>
  );
}

export default EmailInput;
```

Neste exemplo, a função `validateEmail` usa uma expressão regular para validar o formato do e-mail. A função `handleChange` é chamada sempre que o valor do campo de e-mail muda. Ela atualiza o estado do componente com o valor atual do campo de e-mail e o resultado da validação. O estado `isValidEmail` é usado para aplicar uma classe CSS que indica se o valor do campo de e-mail é válido ou não. Um elemento `<div>` de erro é renderizado se o e-mail não for válido.

> Quero que me dê um alerta `alert()` padrão de PopUp simples caso o email não seja válido.

Claro, você pode adicionar uma condição para verificar se o email é válido e exibir um alerta caso não seja. Aqui está um exemplo:

```jsx
function validarEmail(email) {
  // Expressão regular para validar email
  const re = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
  return re.test(email);
}

function handleSubmit(e) {
  e.preventDefault();

  const email = e.target.email.value;

  // Verifica se o email é válido
  if (!validarEmail(email)) {
    alert('Por favor, insira um email válido!');
    return;
  }

  // Resto do código para enviar o formulário
}
```

Nesse exemplo, a função `validarEmail` usa uma expressão regular para verificar se o email é válido. Se o email não for válido, o código exibe um alerta. Caso contrário, o resto do código para enviar o formulário pode ser executado. Note que a função `handleSubmit` deve ser atribuída ao evento `onSubmit` do formulário para ser chamada quando o formulário for enviado.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

## Resetar campos do formulário

Para resetar todos os campos do formulário, você pode utilizar o método `reset()` do objeto `HTMLFormElement`. Esse método faz com que todos os campos dentro do formulário sejam resetados para os valores iniciais.

Assim, basta adicionar um evento de click no botão "Reset" e chamar o método `reset()` no objeto `form`, que representa o elemento `form` do seu formulário.

>>> Resumo: Passo-a-passo

`1`. Fora do componente, importe o `useRef`:

```jsx
import { useRef } from "react";
```

`2`. Abaixo das declaraçõs dos valores dos campos, declare a constante `formRef`:

  ```jsx
  // Referenciar o formulário.
  const formRef = useRef();
  ```
`3`. Adicione a função `handleReset()`:

  ```jsx
  // Função Reset, para resetar os campos do formulário.
  function handleReset() {
    formRef.current.reset();
    setName("");
    setEmail("");
  }
  ```

  > Obs.: Coloque os nomes dos campos como no exemplo:

`4`. No formulário coloque a referência `ref={formRef}`:

```jsx
<form ref={formRef}>
  ...
</form>
```

`5`. Coloque a função que foi criada `handleReset()` em um `onClick={}` no `<button>...</button>`:

  ```jsx
  <button type="button" onClick={handleReset}>
    Reset
  </button>
  ```

Nesse exemplo, utilizamos a propriedade `ref` do elemento `form` para obter uma referência ao formulário. Em seguida, passamos essa referência para a propriedade `ref` do elemento `form` e utilizamos o método `reset()` nessa referência no evento de click do botão "Reset". Note que, para resetar os estados dos campos controlados pelo React (`name` e `email`), também precisamos setar esses valores para as strings vazias.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

## Instalar e utilizar o "CKEditor 5" no ReactJS

`1`. Instale o CKEditor 5 via npm:

```bash
npm install --save @ckeditor/ckeditor5-react @ckeditor/ckeditor5-build-classic
```

> Se houver erros de conflito, tente o comando acima com o uso forçado `--force`!

`2`. Importe o componente CKEditor:

```jsx
// CKEditor
import { CKEditor } from '@ckeditor/ckeditor5-react';
import ClassicEditor from '@ckeditor/ckeditor5-build-classic';
```

Se você já tem o campo de texto, como por exemplo:

```jsx
<Form.Group className="mb-3" controlId="formGridAboutSystem">
  <Form.Label>Sobore o sistema</Form.Label>
  <Form.Control as="textarea" size="sm" rows={8} defaultValue={listCompanySystem[0]?.about_system} placeholder="Escreva algo sobre o sistema..." />
</Form.Group>
```

`3`. Substitua o campo `Form.Control` que você deseja usar o CKEditor pelo componente `CKEditor`. Para isso, você pode remover a propriedade `as="textarea"` e adicionar a propriedade editor={ClassicEditor}. Além disso, você pode definir a propriedade `data` com o valor do texto do campo:

```jsx
<Form.Group className="mb-3" controlId="formGridAboutSystem">
  <Form.Label>Sobore o sistema</Form.Label>
  <CKEditor
    editor={ClassicEditor}
    data={listCompanySystem[0]?.about_system}
    onChange={(event, editor) => {
    const data = editor.getData();
      // você pode atualizar o estado com o novo valor aqui
    }}
  />
</Form.Group>
```

No método `onChange` do `CKEditor`, você pode atualizar o estado com o novo valor inserido no editor. Por padrão, o CKEditor retorna o conteúdo formatado em HTML, mas você pode usar o método `editor.getData()` para obter o conteúdo em um formato diferente.

> Com esses passos, você deve conseguir utilizar o CKEditor 5 no seu componente.

Para usar o componente CKEditor `personalizado` e passe as opções personalizadas. Na opção `config`, você pode personalizar a barra de ferramentas, removendo ou adicionando botões de acordo com as suas necessidades. Você também pode definir a altura da área de texto no CSS ou na opção `config` usando a propriedade `content.minHeight`. Por exemplo:

```jsx
<CKEditor
  editor={ClassicEditor}
  data={listCompanySystem[0]?.about_system}
  config={{
    toolbar: [
      'heading',
      '|',
      'bold',
      'italic',
      'link',
      'bulletedList',
      'numberedList',
      '|',
      'indent',
      'outdent',
      '|',
      'undo',
      'redo'
    ],
    content: {
      minHeight: '300px'
    },
    language: 'pt-br'
  }}
  // ...
/>
```

O valor da altura pode ser ajustado de acordo com suas necessidades.

Você pode encontrar uma lista completa das opções disponíveis para a barra de ferramentas do CKEditor 5 no seguinte link da documentação oficial: https://ckeditor.com/docs/ckeditor5/latest/features/ui-language-toolbar.html#toolbar-configuration.

Aqui está uma lista completa das opções disponíveis na barra de ferramentas:

| Botão | Descrição |
| :------------: | :------------ |
| undo | Desfazer a última ação. |
| redo | Refazer a última ação desfeita. |
| &#124; | Pipe character para dividir áreas dos botões. |
| bold | Negrito. |
| italic | Itálico. |
| underline | Sublinhado. |
| strikethrough | Tachado. |
| subscript | Sobrescrito. |
| superscript | Sobrescrito. |
| highlight | Destaque. |
| fontColor | Cor do texto. |
| fontBackgroundColor | Cor do fundo do texto. |
| fontFamily | Família de fontes. |
| fontSize | Tamanho da fonte. |
| heading | Cabeçalho (H1, H2, H3, H4, H5, H6). |
| alignment | Alinhamento (esquerda, centralizado, direita, justificado). |
| indent | Aumentar o recuo. |
| outdent | Diminuir o recuo. |
| link | Link. |
| imageInsert | Inserir imagem. |
| blockQuote | Citação em bloco. |
| list | Lista (bulleted, numbered). |
| codeBlock | Bloco de código. |
| code | Código inline. |
| subscript | Sobrescrito. |
| superscript | Sobrescrito. |
| horizontalLine | Linha horizontal. |
| table | Tabela. |
| specialCharacters | Caracteres especiais. |
| mathFormula | Fórmulas matemáticas. |
| mediaEmbed | Mídia incorporada. |

Observe que algumas dessas opções podem não estar disponíveis, dependendo de quais plugins do CKEditor 5 você incluiu em seu projeto.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

## Envio dos dados para a API do PRISMA

O código tem a função de interceptar o evento de envio de um formulário, validar os dados inseridos, e enviar esses dados para o servidor por meio de uma chamada de API assíncrona usando o método HTTP POST da biblioteca `Api`.

O método `await` é utilizado para aguardar a resposta do servidor antes de continuar a execução do código. Caso ocorra algum erro durante a chamada de API, o bloco `catch` é executado, que emite um alerta com a mensagem "Error!".

A linha `e.preventDefault()` é usada para evitar que o formulário seja enviado de forma padrão, ou seja, sem ser através da chamada de API assíncrona. Com isso, a página não é atualizada automaticamente e o usuário permanece na mesma página após o envio do formulário.

```jsx
// Interceptar o evento de submit.
async function handleSubmitDrivers(e) {
  e.preventDefault();

  // Validações ...

  // Dados do formulário.
  const data = { campo1, campo2, campo3 };

  // Chamada de API assíncrona - Envio dos dados para a API.
  try {
    await Api.post('yourRoute', data);
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
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

## Formulário de Seleção Hierárquica com React

Esse código em React cria um exemplo de formulário para registro de produtos, com dois campos de seleção, um para a categoria e outro para a subcategoria.

```jsx
import React, { useState } from "react";

const categories = [
  { id: 1, name: "Categoria 1" },
  { id: 2, name: "Categoria 2" },
  { id: 3, name: "Categoria 3" },
];

const subcategories = [
  { id: 1, name: "Subcategoria 1", categoryId: 1 },
  { id: 2, name: "Subcategoria 2", categoryId: 1 },
  { id: 3, name: "Subcategoria 3", categoryId: 1 },
  { id: 4, name: "Subcategoria 4", categoryId: 2 },
  { id: 5, name: "Subcategoria 5", categoryId: 2 },
  { id: 6, name: "Subcategoria 6", categoryId: 2 },
  { id: 7, name: "Subcategoria 7", categoryId: 3 },
  { id: 8, name: "Subcategoria 8", categoryId: 3 },
  { id: 9, name: "Subcategoria 9", categoryId: 3 },
];

export function MyComponent() {
  const [category, setCategory] = useState(null);
  const [subcategory, setSubcategory] = useState(null);

  const handleCategoryChange = (e) => {
    setCategory(e.target.value);
    setSubcategory(null);
  };

  const handleSubcategoryChange = (e) => {
    setSubcategory(e.target.value);
  };

  const filteredSubcategories = subcategories.filter(
    (s) => s.categoryId === parseInt(category)
  );

  return (
    <div>
      <h1>Formulário</h1>
      <form>
        <label htmlFor="category">Categoria:</label>
        <select
          id="category"
          name="category"
          value={category}
          onChange={handleCategoryChange}
        >
          <option value="">Selecione uma categoria</option>
          {categories.map((c) => (
            <option key={c.id} value={c.id}>
              {c.name}
            </option>
          ))}
        </select>
        <label htmlFor="subcategory">Subcategoria:</label>
        <select
          id="subcategory"
          name="subcategory"
          value={subcategory}
          onChange={handleSubcategoryChange}
        >
          <option value="">Selecione uma subcategoria</option>
          {filteredSubcategories.map((s) => (
            <option key={s.id} value={s.id}>
              {s.name}
            </option>
          ))}
        </select>
      </form>
    </div>
  );
}
```

Aqui está uma explicação passo a passo do que o código faz:

1. **Importações e definições iniciais:**

   - Importa as funções `useState` e o componente `React` do pacote "react".
   - Define duas constantes: `categories` e `subcategories`, que representam dados de exemplo para categorias e subcategorias.

2. **Componente `MyComponent`:**

   - É uma função que define um componente React.
   - Usa os hooks `useState` para manter o estado dos campos de categoria e subcategoria no formulário.

3. **Handlers de Mudança (`handleCategoryChange` e `handleSubcategoryChange`):**

   - `handleCategoryChange` é chamado quando a categoria é alterada no `select`. Ele atualiza o estado da categoria selecionada e redefine o estado da subcategoria para `null`.
   - `handleSubcategoryChange` é chamado quando a subcategoria é alterada no `select`. Ele atualiza o estado da subcategoria selecionada.

4. **Filtragem de Subcategorias:**

   - `filteredSubcategories` é uma variável que armazena as subcategorias filtradas com base na categoria selecionada. Ele usa o `Array.filter()` para pegar apenas as subcategorias que correspondem à categoria selecionada.

5. **Renderização do formulário:**

   - Renderiza um formulário com dois campos de seleção (`select`):

     - O primeiro campo é para escolher a categoria, onde as opções são geradas a partir do array de categorias.
     - O segundo campo é para escolher a subcategoria, onde as opções são geradas dinamicamente com base na categoria selecionada. Se nenhuma categoria estiver selecionada, as opções são todas as subcategorias. Se uma categoria for selecionada, somente as subcategorias relacionadas a essa categoria serão exibidas.

Esse código cria um formulário interativo que permite aos usuários selecionar uma categoria e, com base nessa seleção, escolher uma subcategoria associada para o registro de um produto.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

## Abas horizontais com React-Bootstrap

[![Abas do React-Bootstrap](https://github.com/systemboys/React_Codes/raw/main/Componentes/Componentes%20e%20elementos/images/Abas_horizontais_com_React-Bootstrap.png "Abas do React-Bootstrap")](https://github.com/systemboys/React_Codes/raw/main/Componentes/Componentes%20e%20elementos/images/Abas_horizontais_com_React-Bootstrap.png "Abas do React-Bootstrap")

Se o `React-Bootstrap` não estiver instalado no `npm`, execute o seguinte comando no terminal:

```bash
npm install react-bootstrap bootstrap
```

Importações dos componentes:

```jsx
import Tab from 'react-bootstrap/Tab';
import Tabs from 'react-bootstrap/Tabs';
```

Elementos do HTML:

```jsx
<Container>
    <Tabs
        defaultActiveKey="TabOne"
        id="uncontrolled-tab-example"
        className="mb-3"
    >
        <Tab eventKey="TabOne" title="Aba 1">
            <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Vitae alias sed, similique illum sequi adipisci fugit deleniti minus quaerat animi ipsa natus libero assumenda iste veritatis repellat earum excepturi sit!</p>
        </Tab>
        <Tab eventKey="TabTwo" title="Aba 2">
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Totam dolores facilis nisi id enim quidem at natus, officia possimus accusantium! Cupiditate iure optio veniam incidunt, magnam ex consequatur aut doloribus!</p>
        </Tab>
    </Tabs>
</Container>
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

## Lista simples com React-Bootstrap

[![Lista simples com React-Bootstrap](https://github.com/systemboys/React_Codes/raw/main/Componentes/Componentes%20e%20elementos/images/listas_simples_react-bootstrap.png "Lista simples com React-Bootstrap")](https://github.com/systemboys/React_Codes/raw/main/Componentes/Componentes%20e%20elementos/images/listas_simples_react-bootstrap.png "Lista simples com React-Bootstrap")

Importar do React-Bootstrap os componentes:

```jsx
import { Container, Table } from 'react-bootstrap';
```

Os elementos HTML no retorno:

```jsx
<Container>
    <Table striped bordered hover size="sm">
        <thead>
            <tr>
                <th>#</th>
                <th>First Name</th>
                <th>Last Name</th>
                <th>Username</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>1</td>
                <td>Mark</td>
                <td>Otto</td>
                <td>@mdo</td>
            </tr>
            <tr>
                <td>2</td>
                <td>Jacob</td>
                <td>Thornton</td>
                <td>@fat</td>
            </tr>
            <tr>
                <td>3</td>
                <td>Larry the Bird</td>
                <td>Roboto</td>
                <td>@twitter</td>
            </tr>
        </tbody>
    </Table>
</Container>
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

## Implantação do DataTables

Para hospedá-lo em seu projeto, baixe neste [link](https://datatables.net/download "Download") e colocar dentro do diretório `./src/` o DataTables `./src/DataTables/`, importar no seu arquivo do componente e selecionar a sua tabela:

Caso preferir utilizar o CDN chamando diretamente no repositório do `DataTables`, coloque no seu arquivo `index.html` dentro do `<head></head>`:

```html
<!-- Start DataTable -->
<link rel="stylesheet" href="https://cdn.datatables.net/1.13.4/css/jquery.dataTables.css" />
<script src="https://cdn.datatables.net/1.13.4/js/jquery.dataTables.js"></script>
<!-- End DataTable -->
```

> ( ! ) O CDN chamado direto do repositório do DataTables, é no caso de não querer hospedá-lo no seu projeto!

Caso contrário, no caso de hospedá-lo no seu projeto, importe o mesmo no seu 

```jsx
// Start DataTable.
import DataTable from 'datatables.net-dt';
import '../../DataTables/jquery-3.6.0.min.js';
import '../../DataTables/datatables.min.js';
import '../../DataTables/datatables.min.css';
const table = new DataTable('#myTable', {
    responsive: true
});
// End DataTables.

export function YourComponent(props) {
    // Resto do seu código do componente...
    return (
        {/* Start of list */}
        <table id="myTable" className="display">
            {/* O resto do código */}
        </table>
        {/* End of list */}
    );
}
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

## Garantir que script DataTables seja executado corretamente no componente

Para garantir que o script do DataTables seja executado corretamente no seu componente, você pode utilizar o ciclo de vida `useEffect` para inicializar o DataTables assim que o componente for renderizado. Dessa forma, o DataTables será inicializado toda vez que o componente for montado ou atualizado.

Aqui está um exemplo de como você pode fazer isso:

```jsx
import { useEffect } from 'react';

// Start DataTables.
import DataTable from 'datatables.net-dt';
import '../../../../DataTables/datatables_theme_2.css'; // Sua folha de estilo
// End DataTables.

export function DemoListings1() {

  // Start DataTables.
  useEffect(() => {
    const table = new DataTable('#myTable', {
      responsive: true
    });
    return () => {
      table.destroy(); // Destruir a tabela quando o componente for desmontado.
    };
  }, []);
  // End DataTables.

  // Restante do código do componente...

  return (
    // Renderização da tabela...
  );
}
```

Ao utilizar o `useEffect` com um array de dependências vazio (`[]`), você garante que o código dentro dele será executado apenas uma vez, após a montagem inicial do componente. Isso garantirá que o DataTables seja inicializado corretamente.

Além disso, observe que no exemplo acima, também é fornecida uma função de retorno dentro do `useEffect` para destruir o DataTables quando o componente for desmontado. Isso pode ser útil se você quiser liberar recursos ou evitar vazamentos de memória.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

## DataTables com o ORM Prisma (resolvendo renderização)

Uma possível causa para a falta de funcionalidade do DataTables ao usar dados provenientes de uma chamada assíncrona é que o DataTables pode estar sendo inicializado antes dos dados estarem disponíveis. Isso pode resultar em problemas de renderização e funcionalidade.

Para resolver esse problema, você pode adiar a inicialização do DataTables até que os dados estejam prontos. Você pode fazer isso movendo a inicialização do DataTables para um ponto em que você tem certeza de que os dados estão presentes e prontos para uso.

Aqui está uma sugestão de como você pode tentar abordar essa questão:

1. Remova qualquer inicialização do DataTables existente no seu código.

2. No seu componente, adicione um estado adicional para controlar se os dados da API já foram carregados. Por exemplo:

```jsx
const [listCustomersData, setListCustomersData] = useState([]);
const [dataLoaded, setDataLoaded] = useState(false);
```

3. Na sua chamada da API do Prisma, após definir os dados formatados, chame `setDataLoaded(true)` para indicar que os dados foram carregados com sucesso.

```jsx
Api.get(`/customers/1`).then((res) => {
  const formattedData = res.data.map((item) => {
    // Mapeamento dos dados
  });
  setListCustomersData(formattedData);
  setDataLoaded(true); // Indicar que os dados foram carregados
});
```

4. Adicione um useEffect que monitora as alterações no estado `dataLoaded`. Quando `dataLoaded` for definido como `true`, isso indicará que os dados da API foram carregados com sucesso. Nesse momento, você pode inicializar o DataTables. Certifique-se de fazer isso apenas uma vez, portanto, adicione `[listCustomersData]` como dependência do useEffect para garantir que ele só seja executado quando os dados da API forem atualizados.

```jsx
useEffect(() => {
  if (dataLoaded) {
    const table = new DataTable('#myTable', {
      responsive: true
    });
    return () => {
      table.destroy(); // Destruir a tabela quando o componente for desmontado.
    };
  }
}, [dataLoaded, listCustomersData]);
```

Certifique-se de substituir `#myTable` pelo seletor correto do seu elemento da tabela no DOM.

Com essa abordagem, o DataTables só será inicializado após os dados terem sido carregados e o estado `dataLoaded` for definido como `true`. Isso garante que o DataTables tenha acesso aos dados corretos e possa funcionar adequadamente.

Espero que isso resolva o problema. Se você ainda tiver dificuldades, por favor, forneça mais detalhes ou mostre o código atualizado para que eu possa ajudá-lo melhor.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

## Responsive grids com React-Bootstrap

[![Sistema de Grids exemplo](https://github.com/systemboys/React_Codes/raw/main/Componentes/Componentes%20e%20elementos/images/Responsive_grids_com_React-Bootstrap.png "Sistema de Grids exemplo")](https://github.com/systemboys/React_Codes/raw/main/Componentes/Componentes%20e%20elementos/images/Responsive_grids_com_React-Bootstrap.png "Sistema de Grids exemplo")

Se o `React-Bootstrap` não estiver instalado no `npm`, execute o seguinte comando no terminal:

```bash
npm install react-bootstrap bootstrap
```

O Col permite especificar larguras de coluna em 6 tamanhos de ponto de interrupção (xs, sm, md, lg, xl e xxl). Para cada ponto de interrupção, você pode especificar a quantidade de colunas a serem expandidas ou definir a propriedade como para larguras de layout automáticas.

Importações dos componentes:

```jsx
import {
    Container,
    Row,
    Col
} from 'react-bootstrap';
```

Elementos do HTML:

```jsx
<Container>
    <Row>
        <Col sm={8}>sm=8</Col>
        <Col sm={4}>sm=4</Col>
    </Row>
    <Row>
        <Col sm>sm=true</Col>
        <Col sm>sm=true</Col>
        <Col sm>sm=true</Col>
    </Row>
</Container>
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

## Buttons com React-Bootstrap

[![Botões do React-Bootstrap](https://github.com/systemboys/React_Codes/raw/main/Componentes/Componentes%20e%20elementos/images/Buttons_com_React-Bootstrap.png "Botões do React-Bootstrap")](https://github.com/systemboys/React_Codes/raw/main/Componentes/Componentes%20e%20elementos/images/Buttons_com_React-Bootstrap.png "Botões do React-Bootstrap")

Se o `React-Bootstrap` não estiver instalado no `npm`, execute o seguinte comando no terminal:

```bash
npm install react-bootstrap bootstrap
```

Importação dos botões do Bootstrap:

```jsx
import Button from 'react-bootstrap/Button';
```

Elementos HTML:

```jsx
<>
    <Button variant="primary">Primary</Button>{' '}
    <Button variant="secondary">Secondary</Button>{' '}
    <Button variant="success">Success</Button>{' '}
    <Button variant="warning">Warning</Button>{' '}
    <Button variant="danger">Danger</Button>{' '}
    <Button variant="info">Info</Button>{' '}
    <Button variant="light">Light</Button>{' '}
    <Button variant="dark">Dark</Button>
    <Button variant="link">Link</Button>
</>
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

## Utilizando o CSS Modules do React

O arquivo de estilo deverá ter o seguinte nome:

```bash
styles.module.css
```

Importação da folha de estilo:

```jsx
import styles from './styles.module.css';
```

Incrementação da classe no elemento HTML:

```jsx
<div className={styles.youClassName}></div>
```

Na impessão de elementos, as classes aparecerão da seguinte forma:

```html
<div class="_youClassName_n97f3_18"></div>
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

## Interfaces com guias com React-Bootstrap

[![Interfaces com guias com React-Bootstrap](https://github.com/systemboys/React_Codes/raw/main/Componentes/Componentes%20e%20elementos/images/Interfaces_com_guias_com_React-Bootstrap.png "Interfaces com guias com React-Bootstrap")](https://github.com/systemboys/React_Codes/raw/main/Componentes/Componentes%20e%20elementos/images/Interfaces_com_guias_com_React-Bootstrap.png "Interfaces com guias com React-Bootstrap")

Você também pode usar os componentes Tab para criar interfaces com tabulações compatíveis com ARIA com o componente `<ListGroup>`. Troque o componente `<Nav>` pelo grupo de listas e pronto.

Importar os componentes:

```jsx
import Col from 'react-bootstrap/Col';
import ListGroup from 'react-bootstrap/ListGroup';
import Row from 'react-bootstrap/Row';
import Tab from 'react-bootstrap/Tab';
```
Elementos HTML:

```jsx
export function TabsExample() {
  return (
    <Tab.Container id="list-group-tabs-example" defaultActiveKey="#link1">
      <Row>
        <Col sm={4}>
          <ListGroup>
            <ListGroup.Item action href="#link1">
              Link 1
            </ListGroup.Item>
            <ListGroup.Item action href="#link2">
              Link 2
            </ListGroup.Item>
          </ListGroup>
        </Col>
        <Col sm={8}>
          <Tab.Content>
            <Tab.Pane eventKey="#link1">
              <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Placeat harum quae unde corporis eius velit omnis temporibus iste possimus? Dolore saepe hic tenetur consequuntur praesentium, pariatur quo dolores magni unde.</p>
            </Tab.Pane>
            <Tab.Pane eventKey="#link2">
              <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Eaque magnam dolores repellendus eum animi ipsam repudiandae molestias quas explicabo placeat. Suscipit molestiae similique magnam quos, illo architecto? Quo, delectus inventore.</p>
            </Tab.Pane>
          </Tab.Content>
        </Col>
      </Row>
    </Tab.Container>
  );
}
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

## Itens acionáveis com React-Bootstrap

[![Itens acionáveis](https://github.com/systemboys/React_Codes/raw/main/Componentes/Componentes%20e%20elementos/images/Itens_acionaveis.png "Itens acionáveis")](https://github.com/systemboys/React_Codes/raw/main/Componentes/Componentes%20e%20elementos/images/Itens_acionaveis.png "Itens acionáveis")

Alterne a propriedade de ação para criar itens de grupo de lista acionáveis, com estilos desativados, de foco e ativos. As ações do item de lista renderizarão um `<button>` ou `<a>` (dependendo da presença de um href) por padrão, mas podem ser substituídas definindo o as prop como de costume.

As ações de itens de lista são diferentes de itens simples para garantir que recursos de clique ou toque não sejam aplicados a itens não interativos.

Importar o componente:

```jsx
import ListGroup from 'react-bootstrap/ListGroup';
```
Elementos HTML:

```jsx
export function LinkedExample() {
  const alertClicked = () => {
    alert('You clicked the third ListGroupItem');
  };

  return (
    <ListGroup defaultActiveKey="#link1">
      <ListGroup.Item action href="#link1">
        Link 1
      </ListGroup.Item>
      <ListGroup.Item action href="#link2" disabled>
        Link 2
      </ListGroup.Item>
      <ListGroup.Item action onClick={alertClicked}>
        This one is a button
      </ListGroup.Item>
    </ListGroup>
  );
}
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

## Posicionamento com React-Bootstrap

[![Posicionamento](https://github.com/systemboys/React_Codes/raw/main/Componentes/Componentes%20e%20elementos/images/Posicionamento.png "Posicionamento")](https://github.com/systemboys/React_Codes/raw/main/Componentes/Componentes%20e%20elementos/images/Posicionamento.png "Posicionamento")

Offcanvas oferece suporte a alguns posicionamentos diferentes:

- começar coloca fora da tela à esquerda da viewport
- lugares finais fora da tela à direita da viewport
- principais lugares fora da tela na parte superior da viewport
- bottom coloca offcanvas na parte inferior da viewport

Importar os componentes:

```jsx
import React, { useState } from 'react';
import Button from 'react-bootstrap/Button';
import Offcanvas from 'react-bootstrap/Offcanvas';
```

Elementos HTML:

```jsx
function OffCanvasExample({ name, ...props }) {
  const [show, setShow] = useState(false);

  const handleClose = () => setShow(false);
  const handleShow = () => setShow(true);

  return (
    <>
      <Button variant="primary" onClick={handleShow} className="me-2">
        {name}
      </Button>
      <Offcanvas show={show} onHide={handleClose} {...props}>
        <Offcanvas.Header closeButton>
          <Offcanvas.Title>Offcanvas</Offcanvas.Title>
        </Offcanvas.Header>
        <Offcanvas.Body>
          Some text as placeholder. In real life you can have the elements you
          have chosen. Like, text, images, lists, etc.
        </Offcanvas.Body>
      </Offcanvas>
    </>
  );
}

function Example() {
  return (
    <>
      {['start', 'end', 'top', 'bottom'].map((placement, idx) => (
        <OffCanvasExample key={idx} placement={placement} name={placement} />
      ))}
    </>
  );
}

render(<Example />);
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

## Mais opções com Paginação com React Bootstrap

[![Mais opções com Paginação](https://github.com/systemboys/React_Codes/raw/main/Componentes/Componentes%20e%20elementos/images/Mais_opcoes_com_Paginacao.png "Mais opções com Paginação")](https://github.com/systemboys/React_Codes/raw/main/Componentes/Componentes%20e%20elementos/images/Mais_opcoes_com_Paginacao.png "Mais opções com Paginação")

Para criar uma IU de paginação mais complexa, existem alguns subcomponentes convenientes para adicionar os botões "Primeiro", "Anterior", "Próximo" e "Último", bem como um item "Reticências" para indicar resultados anteriores ou contínuos.

Importar o componente:

```jsx
import Pagination from 'react-bootstrap/Pagination';
```

Elementos HTML:

```jsx
export function AdvancedExample() {
  return (
    <Pagination>
      <Pagination.First />
      <Pagination.Prev />
      <Pagination.Item>{1}</Pagination.Item>
      <Pagination.Ellipsis />

      <Pagination.Item>{10}</Pagination.Item>
      <Pagination.Item>{11}</Pagination.Item>
      <Pagination.Item active>{12}</Pagination.Item>
      <Pagination.Item>{13}</Pagination.Item>
      <Pagination.Item disabled>{14}</Pagination.Item>

      <Pagination.Ellipsis />
      <Pagination.Item>{20}</Pagination.Item>
      <Pagination.Next />
      <Pagination.Last />
    </Pagination>
  );
}
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

## Espaços reservados com React Bootstrap

[![Espaços reservados](https://github.com/systemboys/React_Codes/raw/main/Componentes/Componentes%20e%20elementos/images/Espacos_reservados.png "Espaços reservados")](https://github.com/systemboys/React_Codes/raw/main/Componentes/Componentes%20e%20elementos/images/Espacos_reservados.png "Espaços reservados")

Use espaços reservados de carregamento para seus componentes ou páginas para indicar que algo ainda pode estar carregando.

> Os espaços reservados podem ser usados para aprimorar a experiência do seu aplicativo. Eles são construídos apenas com HTML e CSS, o que significa que você não precisa de nenhum JavaScript para criá-los. Você precisará, no entanto, de algum JavaScript personalizado para alternar sua visibilidade. Sua aparência, cor e tamanho podem ser facilmente personalizados com nossas classes utilitárias.

### Exemplo

No exemplo abaixo, pegamos um componente de cartão típico e o recriamos com espaços reservados aplicados para criar um “cartão de carregamento”. Tamanho e proporções são os mesmos entre os dois.

Importar os componentes:

```jsx
import Button from 'react-bootstrap/Button';
import Card from 'react-bootstrap/Card';
import Placeholder from 'react-bootstrap/Placeholder';
```

Elementos HTML:

```jsx
export function CardExample() {
  return (
    <div className="d-flex justify-content-around">
      <Card style={{ width: '18rem' }}>
        <Card.Img variant="top" src="holder.js/100px180" />
        <Card.Body>
          <Card.Title>Card Title</Card.Title>
          <Card.Text>
            Some quick example text to build on the card title and make up the
            bulk of the card's content.
          </Card.Text>
          <Button variant="primary">Go somewhere</Button>
        </Card.Body>
      </Card>

      <Card style={{ width: '18rem' }}>
        <Card.Img variant="top" src="holder.js/100px180" />
        <Card.Body>
          <Placeholder as={Card.Title} animation="glow">
            <Placeholder xs={6} />
          </Placeholder>
          <Placeholder as={Card.Text} animation="glow">
            <Placeholder xs={7} /> <Placeholder xs={4} /> <Placeholder xs={4} />{' '}
            <Placeholder xs={6} /> <Placeholder xs={8} />
          </Placeholder>
          <Placeholder.Button variant="primary" xs={6} />
        </Card.Body>
      </Card>
    </div>
  );
}
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

## Barra com animação com React-Bootstrap

[![Barra com animação com React-Bootstrap](https://github.com/systemboys/React_Codes/raw/main/Componentes/Componentes%20e%20elementos/images/Barra_com_animacao_com_React-Bootstrap.png "Barra com animação com React-Bootstrap")](https://github.com/systemboys/React_Codes/raw/main/Componentes/Componentes%20e%20elementos/images/Barra_com_animacao_com_React-Bootstrap.png "Barra com animação com React-Bootstrap")

Anime espaços reservados definindo a animação de suporte para brilhar ou ondular para transmitir melhor a percepção de algo sendo carregado ativamente.

Importar o componente:

```jsx
import Placeholder from 'react-bootstrap/Placeholder';
```

Elementos HTML:

```jsx
export function AnimationExample() {
  return (
    <>
      <Placeholder as="p" animation="glow">
        <Placeholder xs={12} />
      </Placeholder>
      <Placeholder as="p" animation="wave">
        <Placeholder xs={12} />
      </Placeholder>
    </>
  );
}
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

## Incrementando React-FontAwesome

[![React-FontAwesome](https://github.com/systemboys/React_Codes/raw/main/Componentes/Componentes%20e%20elementos/images/React-FontAwesome.png "React-FontAwesome")](https://github.com/systemboys/React_Codes/raw/main/Componentes/Componentes%20e%20elementos/images/React-FontAwesome.png "React-FontAwesome")

Implementação de ícones do `React-FontAwesome` em seu projeto.

Importar os componentes:

```jsx
// Ícones React-Fontawesome.
import { FontAwesomeIcon } from '@fortawesome/react-fontawesome';
import { faPrint } from '@fortawesome/free-solid-svg-icons';
```

> Para cada ícone, você deve consultar o site oficial do [Font Awesome](https://fontawesome.com/ "Font Awesome") e verificar qual a classe você deseja colocando os dados no parâmentro `icon={faPrint}` do elemento HTML. Obs.: No site oficial, em React, ele mostrará da seguinte forma: `<FontAwesomeIcon icon="fa-solid fa-print" />`, observe que a classe é `fa-print`, importe no formato `camelCase` como está no exemplo acima `{ faPrint }` e ponha no componente como está abaixo `icon={faPrint}`.

Elemento HTML:

```jsx
<FontAwesomeIcon icon={faPrint} size="1x" />
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

## Impedir a exibição do menu de contexto (click inverso) dentro do componente

Para impedir a exibição do menu de contexto dentro de um componente em React, você pode adicionar um listener para o evento `contextmenu` na montagem do componente e, em seguida, chamar o método `preventDefault()` do evento para evitar a exibição do menu de contexto.

Você pode fazer isso da seguinte forma:

```jsx
import React, { useEffect } from 'react';

function MyComponent() {

  // Bloquear menu de contexto (click inverso).
  useEffect(() => {
    const handleContextMenu = (event) => {
      event.preventDefault();
    };
    document.addEventListener('contextmenu', handleContextMenu);
    return () => {
      document.removeEventListener('contextmenu', handleContextMenu);
    };
  }, []);

  return (
    <div>
      {/* conteúdo do seu componente */}
    </div>
  );
}
```

Nesse exemplo, estamos usando o hook `useEffect` para adicionar um listener para o evento `contextmenu` no elemento `document` quando o componente é montado. No retorno da função passada para o `useEffect`, estamos removendo o listener para garantir que ele não continue a ser executado quando o componente é desmontado.

Com essa abordagem, qualquer menu de contexto que tente ser exibido dentro do seu componente será impedido de aparecer.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

## Gerenciamento de Janelas Flutuantes com Fenestra: Passando Propriedades para Controle de Fechamento Dinâmico (Resolvido)

> ( ! ) Situação problema (Resolvido)!

A razão pela qual sua função `handlePopUpNo()` pode não estar funcionando é que você está tentando acessar `props.fenestra` diretamente dentro do componente `DeleteUser`, mas não está passando `props` no componente. Se você está tentando acessar algo que está fora do escopo do seu componente, precisará garantir que a instância do Fenestra seja acessada corretamente.

Aqui estão alguns pontos que podem ajudar a resolver o problema:

1. **Verifique a passagem de `fenestra` como `prop`:** Certifique-se de que, quando você instancia o componente `<DeleteUser />`, está passando o `fenestra` como prop.
   
2. **Desestruturação do `props`:** No componente `DeleteUser`, você está desestruturando `{ id }`, mas precisa desestruturar `fenestra` também, caso ele seja passado como prop.

Aqui está a modificação sugerida:

```jsx
export function DeleteUser({ fenestra }) {

    // Definir o estado para o valor "y".
    const [confirmationValue] = useState("y");

    // Referenciar o formulário.
    const formRef = useRef();

    // Função para fechar janela flutuante.
    function handlePopUpNo() {
        // Fechar a janela flutuante.
        if (fenestra) {
            fenestra.close();  // Fechar a janela do Fenestra
        }
    }

    return (
        <Container>
            <Form ref={formRef} onSubmit={handleSubmitForm}>
                <Row className="mb-3">
                    <Col sm={12}>
                        <p>Deseja mesmo excluir este registro?</p>
                    </Col>
                </Row>
                <Button variant="danger" type="submit">
                    <FontAwesomeIcon icon={faCheck} />{' '}Sim
                </Button>
                <Button type="button" onClick={handlePopUpNo} variant="secondary" className="ms-2">
                    <FontAwesomeIcon icon={faTimes} />{' '}Não
                </Button>
            </Form>
        </Container>
    );
}
```

### O que foi alterado:

1. **Recebendo `fenestra` como prop:** Eu adicionei `fenestra` na desestruturação do componente, para que você possa acessar diretamente o `fenestra` passado na instância do componente.
   
2. **Acesso ao `fenestra`:** Dentro de `handlePopUpNo()`, agora você acessa `fenestra.close()` corretamente.

### Instanciando o componente:

Certifique-se de que, ao abrir a janela, você está passando o `fenestra` como prop ao instanciar o `<DeleteUser />`:

```jsx
<FontAwesomeIcon 
    className={styles.faTrashCan} 
    icon={faTrashCan} 
    size="1x" 
    title='Excluir usuário' 
    onClick={() => props.fenestra.open({
        title: "Resumida", 
        resizeable: false, 
        left: (window.innerWidth - 350) / 2, 
        top: (window.innerHeight - 150) / 2, 
        width: 350, 
        height: 150, 
        content: ({ fenestra }) => <DeleteUser id={item.id} fenestra={fenestra} /> // Passe fenestra como prop aqui
    })} 
/>
```

Com isso, o `fenestra` será passado como prop para o componente `DeleteUser`, e o botão "Não" deverá fechar a janela corretamente.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

## Passagem de Propriedades com props e Desestruturação em Componentes React

Você pode passar a propriedade `fenestra` para o componente `DemoListings1` da mesma forma que você faria com qualquer outra propriedade, mesmo que ele esteja usando `props`. Aqui está como você pode fazer isso:

1. **Passar a propriedade `fenestra` ao chamar o componente**: Se você estiver usando o componente `DemoListings1` em algum lugar do seu código, você pode simplesmente passar `fenestra` como uma propriedade:

   ```jsx
   <DemoListings1 fenestra={fenestra} />
   ```

2. **Receber a propriedade `fenestra` dentro do componente usando `props`**: Como o seu componente está usando `props`, você pode acessar a propriedade `fenestra` de `props` diretamente dentro do componente.

   Aqui está como ficaria o código completo com a propriedade `fenestra` sendo passada e acessada:

   ```jsx
   export function DemoListings1(props) {
     const { fenestra } = props; // desestruturando a propriedade fenestra de props

     // ou você pode acessar diretamente como props.fenestra
     console.log(fenestra); // Isso exibirá o valor de fenestra

     return (
       <div>
         {/* Outros elementos do seu componente */}
         <p>O valor de fenestra é: {fenestra}</p>
       </div>
     );
   }
   ```

   Basicamente, você só precisa garantir que está passando `fenestra` ao instanciar o componente e, em seguida, desestruturar ou acessar essa propriedade de `props` dentro do componente.

Se você quiser manter a estrutura padrão de `props` e ainda assim desestruturar o `fenestra`, o exemplo acima é o mais simples.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

## Controle Condicional de Fechamento de Janela no Formulário

Para implementar a funcionalidade onde a janela só será fechada se o botão "Fechar ao concluir" estiver marcado, você pode modificar a lógica de fechamento do `fenestra` com base no valor do `Form.Check` que você já tem no componente. Aqui estão as alterações necessárias:

### 1. **Criar um estado para o switch**  
Você precisa armazenar o valor do switch "Fechar ao concluir" em um estado. Adicione o seguinte estado ao componente:

```jsx
const [closeOnSubmit, setCloseOnSubmit] = useState(true);
```

### 2. **Vincular o estado ao switch**  
Altere o `Form.Check` para que ele atualize esse novo estado quando for clicado. Atualize o código do `Form.Check` da seguinte maneira:

```jsx
<Form.Check 
    type="switch"
    id="custom-switch"
    label="Fechar ao concluir"
    checked={closeOnSubmit}
    onChange={(e) => setCloseOnSubmit(e.target.checked)}
/>
```

### 3. **Modificar a lógica de fechamento da janela**  
Agora, altere o trecho onde o `fenestra.close()` é chamado, para que ele verifique o estado do `closeOnSubmit` antes de fechar a janela:

```jsx
// --- Executar após registro de dados ---
if (closeOnSubmit && fenestra) {
    fenestra.close();  // Fechar a janela do Fenestra
}
// --- /Executar após registro de dados ---
```

### Código Final das Alterações

Aqui estão as partes relevantes com as alterações aplicadas:

1. **Estado para o switch:**

```jsx
const [closeOnSubmit, setCloseOnSubmit] = useState(true);
```

2. **Modificação do `Form.Check`:**

```jsx
<Form.Check 
    type="switch"
    id="custom-switch"
    label="Fechar ao concluir"
    checked={closeOnSubmit}
    onChange={(e) => setCloseOnSubmit(e.target.checked)}
/>
```

3. **Verificação antes de fechar a janela:**

```jsx
if (closeOnSubmit && fenestra) {
    fenestra.close();  // Fechar a janela do Fenestra
}
```

Com essas alterações, a janela só fechará se o switch "Fechar ao concluir" estiver ativado.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---
