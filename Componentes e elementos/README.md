# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Componentes e elementos

- [Componentes no modo `Default Exports`](#componentes-no-modo-default-exports "Componentes no modo Default Exports")
- [Componentes no modo `Named Exports`](#componentes-no-modo-named-exports "Componentes no modo Named Exports")
- [`Formulário` responsívo com React-Bootstrap](#formul%C3%A1rio-respons%C3%ADvo-com-react-bootstrap "Formulário responsívo com React-Bootstrap")
  - [`Máscara` nos campos](#m%C3%A1scara-nos-campos "Máscara nos campos")
  - [Enviando um `formulário`](#enviando-um-formul%C3%A1rio "Enviando um formulário")
  - [`Campos editáveis` no formulário dentro de um componente](#campos-edit%C3%A1veis-no-formul%C3%A1rio-dentro-de-um-componente "Campos editáveis no formulário dentro de um componente")
  - [`Validar` os `campos vazios` do formulário](#validar-os-campos-vazios-do-formul%C3%A1rio "Validar os campos vazios do formulário")
  - [`Resetar` campos do `formulário`](#resetar-campos-do-formul%C3%A1rio "Resetar campos do formulário")
  - [Instalar e utilizar o `CKEditor 5` no ReactJS](#instalar-e-utilizar-o-ckeditor-5-no-reactjs "Instalar e utilizar o CKEditor 5 no ReactJS")
- [`Abas` horizontais com React-Bootstrap](#abas-horizontais-com-react-bootstrap "Abas horizontais com React-Bootstrap")
- [`Lista simples` com React-Bootstrap](#lista-simples-com-react-bootstrap "Lista simples com React-Bootstrap")
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

Arquivo `Test.jsx` com o componente em modo Default Exports.

```javascript
function Test() {
    return (
      <h1>Content test...</h1>
    )
}

export default Test
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--componentes-e-elementos "Subir para o topo")

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
    </div>
  )
}
```

Arquivo `Post.jsx` com o componente em modo Named Exports.

```javascript
export function Post() {
    return <p>Post</p>
}
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--componentes-e-elementos "Subir para o topo")

---

## Formulário responsívo com React-Bootstrap

[![Formulário de exemplo](https://github.com/systemboys/React_Codes/raw/main/Componentes%20e%20elementos/images/Formulario_responsivo_com_React-Bootstrap.png "Formulário de exemplo")](https://github.com/systemboys/React_Codes/raw/main/Componentes%20e%20elementos/images/Formulario_responsivo_com_React-Bootstrap.png "Formulário de exemplo")

Se o `React-Bootstrap` não estiver instalado no `npm`, execute o seguinte comando no terminal:

```bash
npm install react-bootstrap bootstrap
```

Importar os seguintes componentes:

```javascript
// Componentes do formulário.
import Button from 'react-bootstrap/Button';
import Col from 'react-bootstrap/Col';
import Form from 'react-bootstrap/Form';
import Row from 'react-bootstrap/Row';
```

Ou:

```javascript
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

```javascript
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

```javascript
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
[(&uarr;) Subir](#react-codes--componentes-e-elementos "Subir para o topo")

---

## Máscara nos campos

Para aplicar uma máscara no input do campo CPF, podemos utilizar uma biblioteca de formatação de strings, como o react-input-mask.

Para utilizá-lo, primeiro precisamos instalá-lo:

```bash
npm install react-input-mask
```

Em seguida, podemos importá-lo em nosso componente e utilizá-lo no input da seguinte forma:

```javascript
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

```javascript
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

```javascript
<InputMask
  mask="99/99/9999"
  placeholder="dd/mm/yyyy"
  value={date}
  onChange={(e) => setDate(e.target.value)}
/>
```

Nesse caso, o campo de entrada aceitará somente números e preencherá automaticamente com barras. Lembre-se de que você ainda precisará validar a entrada do usuário para garantir que seja uma data válida.

Basta substituir o valor da propriedade mask para o valor da máscara de data desejada e atualizar a propriedade placeholder para exibir a máscara de data correspondente. Aqui está um exemplo:

```javascript
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

```javascript
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
[(&uarr;) Subir](#react-codes--componentes-e-elementos "Subir para o topo")

---

## Enviando um formulário

Importar o `useState` do React para armazenarmos os valores:

```javascript
import React, { useState } from 'react';
```

Dentro do seu componente, antes do retorno, devem ser declarados os valores, deixando-os vazios e, deverá ter também uma `Arrow Function` para interceptar o evento do Submit do formulário:

> Quando não há `action=""` ou quando há mas não é definido nenhum valor, ao enviar o submit, o usuário será direcionado para a mesma tela do formulário (comportamento típico do form). A ação do envio deverá ser mapeada e interceptada.

```javascript
// Declaração dos valores dos campos.
const [email, setEmail] = useState("");
const [username, setUsername] = useState("");
const [password, setPassword] = useState("");

// Interceptar o evento de submit.
const handleSubmitLogin = (e) => {
    e.preventDefault();

    // Exibir no console os valores obitidos nos campos.
    console.log("submit", { email, username, password });
}
```

> Na função, o (e) em `const handleSubmitLogin = (e) => {...` pode ser colocado (e), (ev) ou (event)!

A função deverá ser colocada no `<form>...</form>` no evento `onSubmit={}`:

```javascript
<form onSubmit={handleSubmitLogin}>
```

Agora os geters e os seters deverão ser ligados nos campos:

```javascript
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
[(&uarr;) Subir](#react-codes--componentes-e-elementos "Subir para o topo")

---

## Campos editáveis no formulário dentro de um componente

Como definir um valor em um campo onde ele se torna editável dentro de um componente?

> Para definir um valor padrão para um campo `type="text"` em React, você pode definir o valor inicial do estado que irá controlar o valor do campo. Você pode usar o hook `useState` para definir o estado inicial do valor do campo, assim como a função para atualizá-lo quando necessário.

> Aqui está um exemplo de como definir um valor padrão para um campo de texto usando o componente `Form.Control` do React Bootstrap:

```javascript
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
[(&uarr;) Subir](#react-codes--componentes-e-elementos "Subir para o topo")

---

## Validar os campos vazios do formulário

Para verificar se os campos estão vazios, você pode usar uma declaração condicional `if` para verificar se as variáveis de estado correspondentes estão vazias ou não antes de enviar o formulário. Você pode fazer algo assim:

Inportar o `useRef` do React.

```javascript
import React, { useState, useRef } from "react";
```

> Aqui está um exemplo de como você pode definir o foco nos campos de entrada criando referências para setar o focus.

```javascript
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
const handleSubmitCustomerRegistration = (e) => {
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

```javascript
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
[(&uarr;) Subir](#react-codes--componentes-e-elementos "Subir para o topo")

---

## Resetar campos do formulário

Para resetar todos os campos do formulário, você pode utilizar o método `reset()` do objeto `HTMLFormElement`. Esse método faz com que todos os campos dentro do formulário sejam resetados para os valores iniciais.

Assim, basta adicionar um evento de click no botão "Reset" e chamar o método `reset()` no objeto `form`, que representa o elemento `form` do seu formulário.

>>> Resumo: Passo-a-passo

`1`. Fora do componente, importe o `useRef`:

```javascript
import { useRef } from "react";
```

`2`. Abaixo das declaraçõs dos valores dos campos, declare a constante `formRef`:

  ```javascript
  // Referenciar o formulário.
  const formRef = useRef();
  ```
`3`. Adicione a função `handleReset()`:

  ```javascript
  // Função Reset, para resetar os campos do formulário.
  function handleReset() {
    formRef.current.reset();
    setName("");
    setEmail("");
  }
  ```

  > Obs.: Coloque os nomes dos campos como no exemplo:

`4`. No formulário coloque a referência `ref={formRef}`:

```javascript
<form ref={formRef}>
  ...
</form>
```

`5`. Coloque a função que foi criada `handleReset()` em um `onClick={}` no `<button>...</button>`:

  ```javascript
  <button type="button" onClick={handleReset}>
    Reset
  </button>
  ```

Nesse exemplo, utilizamos a propriedade `ref` do elemento `form` para obter uma referência ao formulário. Em seguida, passamos essa referência para a propriedade `ref` do elemento `form` e utilizamos o método `reset()` nessa referência no evento de click do botão "Reset". Note que, para resetar os estados dos campos controlados pelo React (`name` e `email`), também precisamos setar esses valores para as strings vazias.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--componentes-e-elementos "Subir para o topo")

---

## Instalar e utilizar o "CKEditor 5" no ReactJS

`1`. Instale o CKEditor 5 via npm:

```bash
npm install --save @ckeditor/ckeditor5-react @ckeditor/ckeditor5-build-classic
```

> Se houver erros de conflito, tente o comando acima com o uso forçado `--force`!

`2`. Importe o componente CKEditor:

```javascript
// CKEditor
import { CKEditor } from '@ckeditor/ckeditor5-react';
import ClassicEditor from '@ckeditor/ckeditor5-build-classic';
```

Se você já tem o campo de texto, como por exemplo:

```javascript
<Form.Group className="mb-3" controlId="formGridAboutSystem">
  <Form.Label>Sobore o sistema</Form.Label>
  <Form.Control as="textarea" size="sm" rows={8} defaultValue={listCompanySystem[0]?.about_system} placeholder="Escreva algo sobre o sistema..." />
</Form.Group>
```

`3`. Substitua o campo `Form.Control` que você deseja usar o CKEditor pelo componente `CKEditor`. Para isso, você pode remover a propriedade `as="textarea"` e adicionar a propriedade editor={ClassicEditor}. Além disso, você pode definir a propriedade `data` com o valor do texto do campo:

```javascript
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

```javascript
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
[(&uarr;) Subir](#react-codes--componentes-e-elementos "Subir para o topo")

---

## Abas horizontais com React-Bootstrap

[![Abas do React-Bootstrap](https://github.com/systemboys/React_Codes/raw/main/Componentes%20e%20elementos/images/Abas_horizontais_com_React-Bootstrap.png "Abas do React-Bootstrap")](https://github.com/systemboys/React_Codes/raw/main/Componentes%20e%20elementos/images/Abas_horizontais_com_React-Bootstrap.png "Abas do React-Bootstrap")

Se o `React-Bootstrap` não estiver instalado no `npm`, execute o seguinte comando no terminal:

```bash
npm install react-bootstrap bootstrap
```

Importações dos componentes:

```javascript
import Tab from 'react-bootstrap/Tab';
import Tabs from 'react-bootstrap/Tabs';
```

Elementos do HTML:

```javascript
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
[(&uarr;) Subir](#react-codes--componentes-e-elementos "Subir para o topo")

---

## Lista simples com React-Bootstrap

[![Lista simples com React-Bootstrap](https://github.com/systemboys/React_Codes/raw/main/Componentes%20e%20elementos/images/listas_simples_react-bootstrap.png "Lista simples com React-Bootstrap")](https://github.com/systemboys/React_Codes/raw/main/Componentes%20e%20elementos/images/listas_simples_react-bootstrap.png "Lista simples com React-Bootstrap")

Importar do React-Bootstrap os componentes:

```javascript
import { Container, Table } from 'react-bootstrap';
```

Os elementos HTML no retorno:

```javascript
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
[(&uarr;) Subir](#react-codes--componentes-e-elementos "Subir para o topo")

---

## Responsive grids com React-Bootstrap

[![Sistema de Grids exemplo](https://github.com/systemboys/React_Codes/raw/main/Componentes%20e%20elementos/images/Responsive_grids_com_React-Bootstrap.png "Sistema de Grids exemplo")](https://github.com/systemboys/React_Codes/raw/main/Componentes%20e%20elementos/images/Responsive_grids_com_React-Bootstrap.png "Sistema de Grids exemplo")

Se o `React-Bootstrap` não estiver instalado no `npm`, execute o seguinte comando no terminal:

```bash
npm install react-bootstrap bootstrap
```

O Col permite especificar larguras de coluna em 6 tamanhos de ponto de interrupção (xs, sm, md, lg, xl e xxl). Para cada ponto de interrupção, você pode especificar a quantidade de colunas a serem expandidas ou definir a propriedade como para larguras de layout automáticas.

Importações dos componentes:

```javascript
import Container from 'react-bootstrap/Container';
import Row from 'react-bootstrap/Row';
import Col from 'react-bootstrap/Col';
```

Elementos do HTML:

```javascript
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
[(&uarr;) Subir](#react-codes--componentes-e-elementos "Subir para o topo")

---

## Buttons com React-Bootstrap

[![Botões do React-Bootstrap](https://github.com/systemboys/React_Codes/raw/main/Componentes%20e%20elementos/images/Buttons_com_React-Bootstrap.png "Botões do React-Bootstrap")](https://github.com/systemboys/React_Codes/raw/main/Componentes%20e%20elementos/images/Buttons_com_React-Bootstrap.png "Botões do React-Bootstrap")

Se o `React-Bootstrap` não estiver instalado no `npm`, execute o seguinte comando no terminal:

```bash
npm install react-bootstrap bootstrap
```

Importação dos botões do Bootstrap:

```javascript
import Button from 'react-bootstrap/Button';
```

Elementos HTML:

```javascript
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
[(&uarr;) Subir](#react-codes--componentes-e-elementos "Subir para o topo")

---

## Utilizando o CSS Modules do React

O arquivo de estilo deverá ter o seguinte nome:

```bash
styles.module.css
```

Importação da folha de estilo:

```javascript
import styles from './styles.module.css';
```

Incrementação da classe no elemento HTML:

```javascript
<div className={styles.youClassName}></div>
```

Na impessão de elementos, as classes aparecerão da seguinte forma:

```html
<div class="_youClassName_n97f3_18"></div>
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--componentes-e-elementos "Subir para o topo")

---

## Interfaces com guias com React-Bootstrap

[![Interfaces com guias com React-Bootstrap](https://github.com/systemboys/React_Codes/raw/main/Componentes%20e%20elementos/images/Interfaces_com_guias_com_React-Bootstrap.png "Interfaces com guias com React-Bootstrap")](https://github.com/systemboys/React_Codes/raw/main/Componentes%20e%20elementos/images/Interfaces_com_guias_com_React-Bootstrap.png "Interfaces com guias com React-Bootstrap")

Você também pode usar os componentes Tab para criar interfaces com tabulações compatíveis com ARIA com o componente `<ListGroup>`. Troque o componente `<Nav>` pelo grupo de listas e pronto.

Importar os componentes:

```javascript
import Col from 'react-bootstrap/Col';
import ListGroup from 'react-bootstrap/ListGroup';
import Row from 'react-bootstrap/Row';
import Tab from 'react-bootstrap/Tab';
```
Elementos HTML:

```javascript
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
[(&uarr;) Subir](#react-codes--componentes-e-elementos "Subir para o topo")

---

## Itens acionáveis com React-Bootstrap

[![Itens acionáveis](https://github.com/systemboys/React_Codes/raw/main/Componentes%20e%20elementos/images/Itens_acionaveis.png "Itens acionáveis")](https://github.com/systemboys/React_Codes/raw/main/Componentes%20e%20elementos/images/Itens_acionaveis.png "Itens acionáveis")

Alterne a propriedade de ação para criar itens de grupo de lista acionáveis, com estilos desativados, de foco e ativos. As ações do item de lista renderizarão um `<button>` ou `<a>` (dependendo da presença de um href) por padrão, mas podem ser substituídas definindo o as prop como de costume.

As ações de itens de lista são diferentes de itens simples para garantir que recursos de clique ou toque não sejam aplicados a itens não interativos.

Importar o componente:

```javascript
import ListGroup from 'react-bootstrap/ListGroup';
```
Elementos HTML:

```javascript
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
[(&uarr;) Subir](#react-codes--componentes-e-elementos "Subir para o topo")

---

## Posicionamento com React-Bootstrap

[![Posicionamento](https://github.com/systemboys/React_Codes/raw/main/Componentes%20e%20elementos/images/Posicionamento.png "Posicionamento")](https://github.com/systemboys/React_Codes/raw/main/Componentes%20e%20elementos/images/Posicionamento.png "Posicionamento")

Offcanvas oferece suporte a alguns posicionamentos diferentes:

- começar coloca fora da tela à esquerda da viewport
- lugares finais fora da tela à direita da viewport
- principais lugares fora da tela na parte superior da viewport
- bottom coloca offcanvas na parte inferior da viewport

Importar os componentes:

```javascript
import React, { useState } from 'react';
import Button from 'react-bootstrap/Button';
import Offcanvas from 'react-bootstrap/Offcanvas';
```

Elementos HTML:

```javascript
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
[(&uarr;) Subir](#react-codes--componentes-e-elementos "Subir para o topo")

---

## Mais opções com Paginação com React Bootstrap

[![Mais opções com Paginação](https://github.com/systemboys/React_Codes/raw/main/Componentes%20e%20elementos/images/Mais_opcoes_com_Paginacao.png "Mais opções com Paginação")](https://github.com/systemboys/React_Codes/raw/main/Componentes%20e%20elementos/images/Mais_opcoes_com_Paginacao.png "Mais opções com Paginação")

Para criar uma IU de paginação mais complexa, existem alguns subcomponentes convenientes para adicionar os botões "Primeiro", "Anterior", "Próximo" e "Último", bem como um item "Reticências" para indicar resultados anteriores ou contínuos.

Importar o componente:

```javascript
import Pagination from 'react-bootstrap/Pagination';
```

Elementos HTML:

```javascript
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
[(&uarr;) Subir](#react-codes--componentes-e-elementos "Subir para o topo")

---

## Espaços reservados com React Bootstrap

[![Espaços reservados](https://github.com/systemboys/React_Codes/raw/main/Componentes%20e%20elementos/images/Espacos_reservados.png "Espaços reservados")](https://github.com/systemboys/React_Codes/raw/main/Componentes%20e%20elementos/images/Espacos_reservados.png "Espaços reservados")

Use espaços reservados de carregamento para seus componentes ou páginas para indicar que algo ainda pode estar carregando.

> Os espaços reservados podem ser usados para aprimorar a experiência do seu aplicativo. Eles são construídos apenas com HTML e CSS, o que significa que você não precisa de nenhum JavaScript para criá-los. Você precisará, no entanto, de algum JavaScript personalizado para alternar sua visibilidade. Sua aparência, cor e tamanho podem ser facilmente personalizados com nossas classes utilitárias.

### Exemplo

No exemplo abaixo, pegamos um componente de cartão típico e o recriamos com espaços reservados aplicados para criar um “cartão de carregamento”. Tamanho e proporções são os mesmos entre os dois.

Importar os componentes:

```javascript
import Button from 'react-bootstrap/Button';
import Card from 'react-bootstrap/Card';
import Placeholder from 'react-bootstrap/Placeholder';
```

Elementos HTML:

```javascript
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
[(&uarr;) Subir](#react-codes--componentes-e-elementos "Subir para o topo")

---

## Barra com animação com React-Bootstrap

[![Barra com animação com React-Bootstrap](https://github.com/systemboys/React_Codes/raw/main/Componentes%20e%20elementos/images/Barra_com_animacao_com_React-Bootstrap.png "Barra com animação com React-Bootstrap")](https://github.com/systemboys/React_Codes/raw/main/Componentes%20e%20elementos/images/Barra_com_animacao_com_React-Bootstrap.png "Barra com animação com React-Bootstrap")

Anime espaços reservados definindo a animação de suporte para brilhar ou ondular para transmitir melhor a percepção de algo sendo carregado ativamente.

Importar o componente:

```javascript
import Placeholder from 'react-bootstrap/Placeholder';
```

Elementos HTML:

```javascript
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
[(&uarr;) Subir](#react-codes--componentes-e-elementos "Subir para o topo")

---

## Incrementando React-FontAwesome

[![React-FontAwesome](https://github.com/systemboys/React_Codes/raw/main/Componentes%20e%20elementos/images/React-FontAwesome.png "React-FontAwesome")](https://github.com/systemboys/React_Codes/raw/main/Componentes%20e%20elementos/images/React-FontAwesome.png "React-FontAwesome")

Implementação de ícones do `React-FontAwesome` em seu projeto.

Importar os componentes:

```javascript
// Ícones React-Fontawesome.
import { FontAwesomeIcon } from '@fortawesome/react-fontawesome';
import { faPrint } from '@fortawesome/free-solid-svg-icons';
```

> Para cada ícone, você deve consultar o site oficial do [Font Awesome](https://fontawesome.com/ "Font Awesome") e verificar qual a classe você deseja colocando os dados no parâmentro `icon={faPrint}` do elemento HTML. Obs.: No site oficial, em React, ele mostrará da seguinte forma: `<FontAwesomeIcon icon="fa-solid fa-print" />`, observe que a classe é `fa-print`, importe no formato `camelCase` como está no exemplo acima `{ faPrint }` e ponha no componente como está abaixo `icon={faPrint}`.

Elemento HTML:

```javascript
<FontAwesomeIcon icon={faPrint} size="1x" />
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--componentes-e-elementos "Subir para o topo")

---
