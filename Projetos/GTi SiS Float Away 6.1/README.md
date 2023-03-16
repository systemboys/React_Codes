
# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / GTi SiS Float Away 6.1

[![GTi SiS Float Away 6.1](https://github.com/systemboys/React_Codes/raw/main/Projetos/GTi%20SiS%20Float%20Away%206.1/images/Front_GTi-SiS-Float-Away-6.1.png "GTi SiS Float Away 6.1")](https://github.com/systemboys/React_Codes/raw/main/Projetos/GTi%20SiS%20Float%20Away%206.1/images/Front_GTi-SiS-Float-Away-6.1.png "GTi SiS Float Away 6.1")

- [React-Fenestra](#react-fenestra "React-Fenestra")
- [Como instalar o GTi SiS Float Away 6.1?](#como-instalar-o-gti-sis-float-away-61 "Como instalar o GTi SiS Float Away 6.1?")
- [Tamanho e posição da janela](#tamanho-e-posi%C3%A7%C3%A3o-da-janela "Tamanho e posição da janela")
- [Centralizar a janela](#centralizar-a-janela "Centralizar a janela")
- [Abrir janelas a partir de outras janelas do Fenestra](#abrir-janelas-a-partir-de-outras-janelas-do-fenestra "Abrir janelas a partir de outras janelas do Fenestra")

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

Com o `npm lts` instalado, crie seu projeto como `Vite`.

```bash
npm create vite@latest project_name
```

>Obs.: Selecione `React` e depois `JavaScript`, o Fenestra não está utilizando `TypyScript`!

2 - Entre no diretório do seu projeto `project_name` e copie os arquivos do projeto:

  - Baixe o arquivo compactado [`Download Zip`](https://github.com/systemboys/gti-sis-float-away-6.1 "Download Zip") do projeto no GitHub;
  - Extraia o diretório `./src`;
  - Copie os arquivos `./index.html` e `./package.json`.

  > Substitua os que foram criados pelo Vite:

3 - Instale as dependências NPM.

```bash
npm i
```

> Se houver erro com indicando conflitos, force a instalação com `npm i --force`.

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

------------

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

const windowWidth = 400;
const windowHeight = 300;

// A variável global window é própria da linguagem Javascript. Ela não se refere à janela do fenestra.
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