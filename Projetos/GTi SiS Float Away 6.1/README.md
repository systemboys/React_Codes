
# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / GTi SiS Float Away 6.1

[![GTi SiS Float Away 6.1](https://github.com/systemboys/React_Codes/raw/main/Projetos/GTi%20SiS%20Float%20Away%206.1/images/Front_GTi-SiS-Float-Away-6.1.png "GTi SiS Float Away 6.1")](https://github.com/systemboys/React_Codes/raw/main/Projetos/GTi%20SiS%20Float%20Away%206.1/images/Front_GTi-SiS-Float-Away-6.1.png "GTi SiS Float Away 6.1")

- [React-Fenestra](#react-fenestra "React-Fenestra")
- [Como `instalar` o `GTi SiS Float Away 6.1`?](#como-instalar-o-gti-sis-float-away-61 "Como instalar o GTi SiS Float Away 6.1?")
  - [`Clonando do GitHub` para seu computador](#clonando-do-github-para-seu-computador "Clonando do GitHub para seu computador")
- [`Tamanho` e `posição` da janela](#tamanho-e-posi%C3%A7%C3%A3o-da-janela "Tamanho e posição da janela")
- [`Centralizar` a janela](#centralizar-a-janela "Centralizar a janela")
- [`Abrir janelas` a partir de outras janelas do Fenestra](#abrir-janelas-a-partir-de-outras-janelas-do-fenestra "Abrir janelas a partir de outras janelas do Fenestra")
  - [`Nova janela` sendo executada dentro de uma `arrow function`](#nova-janela-sendo-executada-dentro-de-uma-arrow-function "Nova janela sendo executada dentro de uma arrow function")
- [`Filtrar` o `nível de usuário` para exibir os `ícones do Desktop`](#filtrar-o-n%C3%ADvel-de-usu%C3%A1rio-para-exibir-os-%C3%ADcones-do-desktop "Filtrar o nível de usuário para exibir os ícones do Desktop")
- [`Terminais` no `processo de programação` do projeto GTi SiS Float Away 6.1](#terminais-no-processo-de-programa%C3%A7%C3%A3o-do-projeto-gti-sis-float-away-61 "Terminais no processo de programação do projeto GTi SiS Float Away 6.1")

---

# GTi SiS Float Away 6.1

Uma API de janelas para react/redux. Template base desenvolvido por [Luiz Alfredo Silva Galiza dos Santos](https://github.com/alfredogaliza) o mesmo utilizado no o projeto `GTi SiS Float Away 6.1`. Modificações e desenvolvimentos de recursos de base do sistema por [Marcos Aurélio R. da Silva](https://github.com/systemboys) e Sandro de Souza Silva com detalhes definidos.

## React-Fenestra

React-Fenestra é uma biblioteca para implementação de um Desktop baseado em janelas. Construído sobre React/Redux, você poderá fornecer seus próprios redutores para integrar a Store do Desktop. A interface do usuário se baseia nos ícones do Font Awesome. A Biblioteca também produz um design responsivo, bastante adaptado para dispositivos móveis.

[Live Demo](https://github.com/alfredogaliza/react-fenestra)

![Captura de tela de 2023-01-12 19-08-16](https://github.com/systemboys/image-bank/raw/main/Projetos%20em%20React/GTi%20SiS%20Float%20Away%206/gti-sis-float-away-6.1.png)

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--gti-sis-float-away-61 "Subir para o topo")

---

# Instruções para instalação

## Como instalar o GTi SiS Float Away 6.1?

### Projeto

1 - Crie o seu projeto com o `Vite`:

Com o `npm lts` instalado, crie seu projeto com o `Vite`.

```bash
npm create vite@latest project_name
```

>Obs.: Selecione uma estrutura, no nosso caso, a framework `React` e depois a variante `JavaScript`!

2 - Entre no diretório do seu projeto `project_name` e siga os seguintes passos:

  - Baixe o arquivo compactado [`Download Zip`](https://github.com/systemboys/gti-sis-float-away-6.1 "Download Zip") do projeto no GitHub;
  - Extraia o projeto, copie os diretórios `./src/` e `./public/`, os arquivos `./index.html` e `./package.json` para dentro do novo projeto Vite.

[![Download do projeto](https://github.com/systemboys/React_Codes/raw/main/Projetos/GTi%20SiS%20Float%20Away%206.1/images/Download_Zip_gti-sis-float-away-6.1.png "Download do projeto")](https://github.com/systemboys/React_Codes/raw/main/Projetos/GTi%20SiS%20Float%20Away%206.1/images/Download_Zip_gti-sis-float-away-6.1.png "Download do projeto")

> Substitua os que foram criados pelo Vite:

3 - Instale as dependências NPM.

```bash
npm install
```

> Se houver erro com indicando conflitos, force a instalação com `npm install --force`.

Após isto, execute o projeto com o seguinte comando:

```bash
npm run dev
```

Após executar o projeto, logo lhe apresentará o endereço localhost com a parta selecionada como no exemplo abaixo:

```bash
  VITE v3.2.3  ready in 772 ms

  ➜  Local:   http://localhost:5173/
  ➜  Network: use --host to expose
```

## Clonando do GitHub para seu computador

No diretório onde deseja colocar seu projeto (ex.: /todos_os_projetos/), com o terminal digite o seguinte comando:

```bash
git clone https://github.com/youruser/youproject.git
```

> O Git exigirá suas credenciais (`usuário` e `senha ou token`)!

Depois disso, faça a instalação das dependências. A instrução está no item `3 - Instale as dependências NPM.`.

---

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--gti-sis-float-away-61 "Subir para o topo")

---

# Configurações das janelas

## Tamanho e posição da janela

Para definir o tamanho e posição da janela, basta você passar os parâmetros top, left, width e height para o argumento da função open, como no exemplo abaixo:

```javascript
// Importações padrão do React
import React from 'react';
import ReactDOM from 'react-dom/client';

// Importação dos componentes do React-Fenestra
import { Desktop, Icon } from 'react-fenestra';

// Aplicação da folha de estilo do Bootstrap e do Fenestra (necessário).
import "bootstrap/dist/css/bootstrap.css";
import "react-fenestra/css/fenestra.css";

// Importação de bibliotecas do FontAwesome (opcional).
import { FontAwesomeIcon } from '@fortawesome/react-fontawesome';
import { faWindowRestore } from '@fortawesome/free-solid-svg-icons';

// Renderização do nó raiz da aplicação
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <React.StrictMode>    
    <Desktop
      icons={[
        ({ fenestra }) =>
          <Icon title="Abrir Janela"
            icon={<FontAwesomeIcon icon={faWindowRestore} size="3x" />}
            onClick={() => fenestra.open({
              title: "Nova Janela",
              top: 20,
              left: 20,
              width: 300,
              height: 300,
              content: ({ fenestra }) =>
                <h1>Olá Mundo!</h1>
            })}
          />
      ]}
    />
  </React.StrictMode>
);
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--gti-sis-float-away-61 "Subir para o topo")

---

## Centralizar a janela

Para centralizar a janela, basta utilizar as propriedades innerWidth e innerHeight da variável global "window". Ela é própria da linguagem Javascript e não se refere à janela do fenestra, e sim à do navegador.

```javascript
// Importações padrão do React
import React from 'react';
import ReactDOM from 'react-dom/client';

// Importação dos componentes do React-Fenestra
import { Desktop, Icon } from 'react-fenestra';

// Aplicação da folha de estilo do Bootstrap e do Fenestra (necessário).
import "bootstrap/dist/css/bootstrap.css";
import "react-fenestra/css/fenestra.css";

// Importação de bibliotecas do FontAwesome (opcional).
import { FontAwesomeIcon } from '@fortawesome/react-fontawesome';
import { faWindowRestore } from '@fortawesome/free-solid-svg-icons';


// (!) A variável global window é própria da linguagem Javascript. Ela não se refere à janela do fenestra.

// Tamanho da janela e do screen.
const windowWidth = 400;
const windowHeight = 300;
const viewportWidth = window.innerWidth;
const viewportHeight = window.innerHeight;

// Renderização do nó raiz da aplicação
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <React.StrictMode>    
    <Desktop
      icons={[
        ({ fenestra }) =>
          <Icon title="Abrir Janela"
            icon={<FontAwesomeIcon icon={faWindowRestore} size="3x" />}
            onClick={() => fenestra.open({
              title: "Nova Janela",
              top: (viewportHeight - windowHeight) / 2,
              left: (viewportWidth - windowWidth) / 2,
              width: windowWidth,
              height: windowHeight,
              content: ({ fenestra }) =>
                <h1>Olá Mundo!</h1>
            })}
          />
      ]}
    />
  </React.StrictMode>
);
```

Lembrando que você também pode ajustar a posição e tamanho da janela dinamicamente, mesmo após ela já ter sido aberta, utilizado a prop "fenestra". Por exemplo, colocando o código abaixo em um botão dentro do conteúdo da janela:

```javascript
// Importações padrão do React
import React from 'react';
import ReactDOM from 'react-dom/client';

// Importação dos componentes do React-Fenestra
import { Desktop, Icon } from 'react-fenestra';

// Aplicação da folha de estilo do Bootstrap e do Fenestra (necessário).
import "bootstrap/dist/css/bootstrap.css";
import "react-fenestra/css/fenestra.css";

// Importação de bibliotecas do FontAwesome (opcional).
import { FontAwesomeIcon } from '@fortawesome/react-fontawesome';
import { faWindowRestore } from '@fortawesome/free-solid-svg-icons';

// Renderização do nó raiz da aplicação
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <React.StrictMode>    
    <Desktop
      icons={[
        ({ fenestra }) =>
          <Icon title="Abrir Janela"
            icon={<FontAwesomeIcon icon={faWindowRestore} size="3x" />}
            onClick={() => fenestra.open({
              title: "Nova Janela",
              width: 400,
              height: 300,
              title: "Nova Janela",
              content: ({ fenestra }) =>
                <button onClick={() => fenestra.setSize(800, 600)}>Aumentar de Tamanho</button>
            })}
          />
      ]}
    />
  </React.StrictMode>
);
```

Para eliminar o botão `Maximizar` veja o exemplo abaixo. Nesse caso, está sendo utilizado a propriedade `resizeable: "false"` dentro de `fenestra.open({})`:

```javascript
<Icon title="Contato"
  icon={<FontAwesomeIcon icon={faEnvelope} size="3x" />}
  onClick={() => fenestra.open({
    title: "Contato",
    resizeable: false,
    left: (window.innerWidth - 800) / 2,
    top: (window.innerHeight - 470) / 2,
    width: 800,
    height: 470,
    content: ({ fenestra }) =>
      <ContactTheDeveloper />
  })}
/>,
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--gti-sis-float-away-61 "Subir para o topo")

---

## Abrir janelas a partir de outras janelas do Fenestra

Para abrir uma janela a partir de outra, basta você utilizar o comando open da API:

```javascript
onClick={() => props.fenestra.open({  title: "Nova Janela", content: ({ fenestra }) => <h1>Olá Mundo!</h1>})}
```

Se quiser utilizar as propriedades da janela criada, basta aproveitar o callback chamado logo após a abertura:

```javascript
onClick={() => props.fenestra.open({  title: "Nova Janela", content: ({ fenestra }) => <h1>Olá Mundo!</h1>}, window => this.setState({filho: window)}
```

Assim você poderá controlar a janela que acabou de criar podendo, inclusive, fechá-la a qualquer momento, de dentro da janela pai:

```javascript
onClick={() => props.fenestra.close(this.state.filho)}
```

Por exemplo, você pode abrir uma janela filho com o formulário e receber o callback quando o formulário for finalizado:

```javascript
onClick={() => props.fenestra.open({  title: "Nova Janela Filho", content: ({ fenestra }) => <form onSubmit={() => meuCallback()}><button type="submit">Me envie!</button></form>})}
```

Exemplo em um botão `<Button onClick={() => ...>...</Button>`:

> Janela centralizada

```javascript
<Button variant="primary" onClick={() => props.fenestra.open({title: "Centralizada", left: (window.innerWidth - 500) / 2, top: (window.innerHeight - 300) / 2, width: 500, height: 300, content: ({ fenestra }) => <p>Nova janela</p>})}>
  Demo
</Button>
```

> Janela posicionada

```javascript
<Button variant="primary" onClick={() => props.fenestra.open({title: "Posicionada", left: 30, top: 30, width: 500, height: 300, content: ({ fenestra }) => <p>Nova janela</p>})}>
  Demo
</Button>
```

> Janela resumida

```javascript
<Button variant="primary" onClick={() => props.fenestra.open({title: "Resumida", resizeable: false, left: (window.innerWidth - 350) / 2, top: (window.innerHeight - 150) / 2, width: 350, height: 150, content: ({ fenestra }) => <p>Nova janela</p>})}>
  Demo
</Button>
```

Você deve utilizar o parâmetro props na definição da função. Assim, a função reescrita ficaria assim: 

```javascript
export function YourComponent(props) {
...

onClick={() => props.fenestra.open(...)}
...

}
```

Aqui segue a alteração e a explicação:

1) Nas expressões do arquivo `./src/App.jsx`, modifique a expressão :

```javascript
content: ({ fenestra }) =>

<YourComponent />
```

Por:

```javascript
content: YourComponent
```

Ou por:

```javascript
content: ({ fenestra }) =>

<YourComponent fenestra={fenestra}/>
```

Você deve instanciar o conteúdo da página com as propriedades do fenestra.

O fenestra vai popular o seu conteudo com as propriedades dele. Veja o exemplo do código no arquivo `./src/App.jsx`.

```javascript
...

({ fenestra }) =>
  <Icon title="Ajuda"
    icon={<FontAwesomeIcon icon={faCircleQuestion} size="3x" />}
    onClick={() => fenestra.open({
      title: "Ajuda",
      left: (window.innerWidth - 990) / 2,
      top: (window.innerHeight - 520) / 2,
      width: 990,
      height: 520,
      content: ({ fenestra }) =>
        <GTiSystemHelp fenestra={fenestra} />
    })}
  />,

...
```

No seu componente, segue a alteração:

```javascript
import { Container, Button } from "react-bootstrap";

export function GTiSystemHelp(props) {
    return (
        <Container>
            <p>Ajuda do sistema...</p>
            <Button
                variant="primary"
                onClick={() => props.fenestra.open({  title: "Nova Janela", content: ({ fenestra }) => <h1>Olá Mundo!</h1>})}
            >
                Primary
            </Button>
        </Container>
    )
}
```

Note que foi adicionado o `props` como parâmetro da função no componente:

```javascript
... GTiSystemHelp(props) {...
```

E foi adicionado a função no `onClick={}`:

```javascript
onClick={() => props.fenestra.open({  title: "Nova Janela", content: ({ fenestra }) => <h1>Olá Mundo!</h1>})}
```

> [Luis Alfredo Galiza] Espero ter ajudado. Até mais.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--gti-sis-float-away-61 "Subir para o topo")

---

## Nova janela sendo executada dentro de uma arrow function

Executar dentro de uma função: ( ! ) Não esquecer de passar o `props` no componente:

```javascript
// Suas importações.
export function YourComponent(props) {

    // Tamanho da janela e do screen.
    const windowWidth = 720;
    const windowHeight = 400;
    const viewportWidth = window.innerWidth;
    const viewportHeight = window.innerHeight;

    // Evento do onClick={}.
    const handleClick = (event, id) => {
        props.fenestra.open({
            title: "Nova Janela",
            top: (viewportHeight - windowHeight) / 2,
            left: (viewportWidth - windowWidth) / 2,
            width: windowWidth,
            height: windowHeight,
            content: ({ fenestra }) =>
              <h1>Olá Mundo! { id }</h1>
          })
    };

    return (
    	<>
    		//...
    	</>
    );
}
```

Botão com o evento `onClink`:

```javascript
return <button onClick={(event) => handleClick(event, "123")}>Nova janela</button>;
```

Para executar um componente para a nova janela e passar o `id` para este componente `<GetResource />`, você pode adicionar uma propriedade `id` ao elemento JSX, como no exemplo abaixo:

```javascript
const handleClick = (event, id) => {
  props.fenestra.open({
    title: "Nova Janela",
    top: (viewportHeight - windowHeight) / 2,
    left: (viewportWidth - windowWidth) / 2,
    width: windowWidth,
    height: windowHeight,
    content: ({ fenestra }) => (
      <GetResource id={id} />
    )
  });
};
```

No exemplo acima, a propriedade `id` é passada para o componente `<GetResource />` como uma prop. O valor do `id` é passado para a função `handleClick` como um parâmetro.

Para recuperar o ID dentro do componente, é necessário passá-lo como uma propriedade do componente. Por exemplo:

```javascript
export function GetResource(props) {
    const { id } = props;
    return <p>ID do Post: {id}</p>
}
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--gti-sis-float-away-61 "Subir para o topo")

---

## Filtrar o nível de usuário para exibir os ícones do Desktop

Para filtrar o nível de usuário e exibir ou não os ícones de acordo com esse nível, você pode utilizar a estrutura condicional `if` dentro da array de ícones, verificando o valor de `userLevel`.

Por exemplo, você pode envolver o ícone de "Configurações" em um bloco `if (userLevel === 1)` para exibi-lo apenas para usuários com nível igual a 1. Veja como ficaria o código:

```javascript
const userLevel = 0;
return (
  <Desktop
    icons={

      [ // Filtra elementos "falsy" do array.

        ({ fenestra }) =>
          userLevel === 1 &&
          <Icon title="Configurações"
            icon={<FontAwesomeIcon icon={faGear} size="3x" />}
            onClick={() => fenestra.open({
              title: "Configurações",
              left: (window.innerWidth - 990) / 2,
              top: (window.innerHeight - 520) / 2,
              width: 990,
              height: 520,
              content: ({ fenestra }) =>
                <SettingsForTheSystem fenestra={fenestra} />
            })}
          />,

        ({ fenestra }) =>
          <Icon title="Usuário"
            icon={<FontAwesomeIcon icon={faUser} size="3x" />}
            onClick={() => fenestra.open({
              title: "Usuário",
              left: (window.innerWidth - 990) / 2,
              top: (window.innerHeight - 520) / 2,
              width: 990,
              height: 520,
              content: ({ fenestra }) =>
                <ListUsers fenestra={fenestra} />
            })}
          />,

        ({ fenestra }) =>
          <Icon title="Clientes"
            icon={<FontAwesomeIcon icon={faAddressCard} size="3x" />}
            onClick={() => fenestra.open({
              title: "Clientes",
              left: (window.innerWidth - 990) / 2,
              top: (window.innerHeight - 520) / 2,
              width: 990,
              height: 520,
              content: ({ fenestra }) =>
                <CustomersList fenestra={fenestra} />
            })}
          />

      ].filter(Boolean) // Filtra elementos "falsy" do array.

    }
  />
)
```

Nesse exemplo, envolvemos a opção de ícone de Configurações em uma verificação condicional que só a exibe se o nível do usuário for 1. Além disso, adicionamos `.filter(Boolean)` ao final do array de ícones para filtrar todos os elementos "falsy" do array, o que inclui a opção de ícone de Configurações quando o nível do usuário é 0.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--gti-sis-float-away-61 "Subir para o topo")

---

## Terminais no processo de programação do projeto GTi SiS Float Away 6.1

Abaixo estão os terminais organizados durante o desenvolvimento dos projeto GTi SiS Float Away 6.1.

[![Terminais durante o processo de desenvolvimento](https://github.com/systemboys/React_Codes/raw/main/Projetos/GTi%20SiS%20Float%20Away%206.1/images/Terminais_Projetos_GTi_SiS.png "Terminais durante o processo de desenvolvimento")](https://github.com/systemboys/React_Codes/raw/main/Projetos/GTi%20SiS%20Float%20Away%206.1/images/Terminais_Projetos_GTi_SiS.png "Terminais durante o processo de desenvolvimento")

| Terminais | Descrição |
| :------------ | :------------ |
| npm api_gsfa6.1 | Execução da API que conecta ao banco de dados do projeto GTi SiS Float Away 6.1 (`npm run dev`). |
| bash api_gsfa6.1 | Projeto da API que conecta ao banco de dados do projeto GTi SiS Float Away 6.1. |
| npm gti-sis-float-away-6.1 | Execução do servidor local do projeto GTi SiS Float Away 6.1 (`npm run dev`). |
| bash gti-sis-float-away-6.1 | Projeto do projeto GTi SiS Float Away 6.1. |
| npm api_gss6.1 | Execução da API que conecta ao banco de dados do projeto GTi SiS Stock 6.1 (`npm run dev`). |
| bash api_gss6.1 | Projeto da API que conecta ao banco de dados do projeto GTi SiS Stock 6.1. |
| npm gti-sis-stock-6.1 | Execução do servidor local do projeto GTi SiS Stock 6.1 (`npm run dev`). |
| bash gti-sis-stock-6.1 | Projeto do projeto GTi SiS Stock 6.1. |

> Os terminais acima está em ordem para o programador se basear no momento do desenvolvimento. Separados em cores, sendo laranja para o Float e verde para o Stock.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--gti-sis-float-away-61 "Subir para o topo")

---