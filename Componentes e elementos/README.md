# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Componentes e elementos

- [Componentes no modo `Default Exports`](https://github.com/systemboys/React_Codes/tree/main/Componentes%20e%20elementos#componentes-no-modo-default-exports "Componentes no modo Default Exports")
- [Componentes no modo `Named Exports`](https://github.com/systemboys/React_Codes/tree/main/Componentes%20e%20elementos#componentes-no-modo-named-exports "Componentes no modo Named Exports")
- [`Formulário` responsívo com React-Bootstrap](https://github.com/systemboys/React_Codes/tree/main/Componentes%20e%20elementos#formul%C3%A1rio-respons%C3%ADvo-com-react-bootstrap "Formulário responsívo com React-Bootstrap")
- [`Abas` horizontais com React-Bootstrap](https://github.com/systemboys/React_Codes/tree/main/Componentes%20e%20elementos#abas-horizontais-com-react-bootstrap "Abas horizontais com React-Bootstrap")
- [`Responsive grids` com React-Bootstrap](https://github.com/systemboys/React_Codes/tree/main/Componentes%20e%20elementos#responsive-grids-com-react-bootstrap "Responsive grids com React-Bootstrap")
- [`Buttons` com React-Bootstrap](https://github.com/systemboys/React_Codes/tree/main/Componentes%20e%20elementos#buttons-com-react-bootstrap "Buttons com React-Bootstrap")
- [Utilizando o `CSS Modules` do React](https://github.com/systemboys/React_Codes/tree/main/Componentes%20e%20elementos#utilizando-o-css-modules-do-react "Utilizando o CSS Modules do React")
- [Interfaces com `guias` com React-Bootstrap](https://github.com/systemboys/React_Codes/tree/main/Componentes%20e%20elementos#interfaces-com-guias-com-react-bootstrap "Interfaces com guias com React-Bootstrap")
- [Itens `acionáveis` com React-Bootstrap](https://github.com/systemboys/React_Codes/tree/main/Componentes%20e%20elementos#itens-acion%C3%A1veis-com-react-bootstrap "Itens acionáveis com React-Bootstrap")
- [`Posicionamento` com React-Bootstrap](https://github.com/systemboys/React_Codes/tree/main/Componentes%20e%20elementos#posicionamento-com-react-bootstrap "Posicionamento com React-Bootstrap")
- [Mais opções com `Paginação` com React-Bootstrap](https://github.com/systemboys/React_Codes/tree/main/Componentes%20e%20elementos#mais-op%C3%A7%C3%B5es-com-pagina%C3%A7%C3%A3o-com-react-bootstrap "Mais opções com Paginação com React Bootstrap")
- [`Espaços reservados` com React-Bootstrap](https://github.com/systemboys/React_Codes/tree/main/Componentes%20e%20elementos#espa%C3%A7os-reservados-com-react-bootstrap "Espaços reservados com React Bootstrap")
- [`Barra com animação` com React-Bootstrap](https://github.com/systemboys/React_Codes/tree/main/Componentes%20e%20elementos#barra-com-animação-com-react-bootstrap "Barra com animação com React-Bootstrap")
- [Incrementando `React-FontAwesome`](https://github.com/systemboys/React_Codes/tree/main/Componentes%20e%20elementos#incrementando-react-fontawesome "Incrementando React-FontAwesome")

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
[(&uarr;) Subir](https://github.com/systemboys/React_Codes/tree/main/Componentes%20e%20elementos#react-codes--componentes-e-elementos "Subir para o topo")

------------

## Formulário responsívo com React-Bootstrap

[![Formulário de exemplo](https://github.com/systemboys/React_Codes/raw/main/Componentes%20e%20elementos/images/Formulario_responsivo_com_React-Bootstrap.png "Formulário de exemplo")](https://github.com/systemboys/React_Codes/raw/main/Componentes%20e%20elementos/images/Formulario_responsivo_com_React-Bootstrap.png "Formulário de exemplo")

Se o `React-Bootstrap` não estiver instalado no `npm`, execute o seguinte comando no terminal:

```
npm install react-bootstrap bootstrap
```

Importar os seguintes componentes:

```javascript
import Button from 'react-bootstrap/Button';
import Col from 'react-bootstrap/Col';
import Form from 'react-bootstrap/Form';
import Row from 'react-bootstrap/Row';
```

Elementos do formulário modelo:

```javascript
<Form>
    <Row className="mb-3">
        <Col sm={6}>
            <Form.Group className="mb-3" as={Col} controlId="formGridEmail">
                <Form.Label>Email principal</Form.Label>
                <Form.Control type="email" size="sm" placeholder="Email do sistema..." value="your_email@host.com" />
            </Form.Group>
        </Col>
        <Col sm={6}>
            <Form.Group className="mb-3" as={Col} controlId="formGridTitle">
                <Form.Label>Título do sistema</Form.Label>
                <Form.Control type="text" size="sm" placeholder="Um título..." />
            </Form.Group>
        </Col>
        <Col sm={12}>
            <Form.Group className="mb-3" as={Col} controlId="formGridState">
                <Form.Label>Estado</Form.Label>
                <Form.Select size="sm">
                    <option>Small select</option>
                </Form.Select>
            </Form.Group>
        </Col>
        <Col sm={12}>
            <Form.Group className="mb-3" controlId="exampleForm.ControlAboutSystem">
                <Form.Label>Sobore o sistema</Form.Label>
                <Form.Control as="textarea" size="sm" rows={8} placeholder="Escreva algo sobre o sistema..." />
            </Form.Group>
        </Col>
    </Row>
    <Button variant="primary" type="submit">
        <i class="fa fa-floppy-o" aria-hidden="true"></i> Salvar
    </Button>
</Form>
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](https://github.com/systemboys/React_Codes/tree/main/Componentes%20e%20elementos#react-codes--componentes-e-elementos "Subir para o topo")

------------

## Abas horizontais com React-Bootstrap

[![Abas do React-Bootstrap](https://github.com/systemboys/React_Codes/raw/main/Componentes%20e%20elementos/images/Abas_horizontais_com_React-Bootstrap.png "Abas do React-Bootstrap")](https://github.com/systemboys/React_Codes/raw/main/Componentes%20e%20elementos/images/Abas_horizontais_com_React-Bootstrap.png "Abas do React-Bootstrap")

Se o `React-Bootstrap` não estiver instalado no `npm`, execute o seguinte comando no terminal:

```
npm install react-bootstrap bootstrap
```

Importações dos componentes:

```javascript
import Tab from 'react-bootstrap/Tab';
import Tabs from 'react-bootstrap/Tabs';
```

Elementos do HTML:

```javascript
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
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](https://github.com/systemboys/React_Codes/tree/main/Componentes%20e%20elementos#react-codes--componentes-e-elementos "Subir para o topo")

------------

## Responsive grids com React-Bootstrap

[![Sistema de Grids exemplo](https://github.com/systemboys/React_Codes/raw/main/Componentes%20e%20elementos/images/Responsive_grids_com_React-Bootstrap.png "Sistema de Grids exemplo")](https://github.com/systemboys/React_Codes/raw/main/Componentes%20e%20elementos/images/Responsive_grids_com_React-Bootstrap.png "Sistema de Grids exemplo")

Se o `React-Bootstrap` não estiver instalado no `npm`, execute o seguinte comando no terminal:

```
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
[(&uarr;) Subir](https://github.com/systemboys/React_Codes/tree/main/Componentes%20e%20elementos#react-codes--componentes-e-elementos "Subir para o topo")

------------

## Buttons com React-Bootstrap

[![Botões do React-Bootstrap](https://github.com/systemboys/React_Codes/raw/main/Componentes%20e%20elementos/images/Buttons_com_React-Bootstrap.png "Botões do React-Bootstrap")](https://github.com/systemboys/React_Codes/raw/main/Componentes%20e%20elementos/images/Buttons_com_React-Bootstrap.png "Botões do React-Bootstrap")

Se o `React-Bootstrap` não estiver instalado no `npm`, execute o seguinte comando no terminal:

```
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
[(&uarr;) Subir](https://github.com/systemboys/React_Codes/tree/main/Componentes%20e%20elementos#react-codes--componentes-e-elementos "Subir para o topo")

------------

## Utilizando o CSS Modules do React

O arquivo de estilo deverá ter o seguinte nome:

```
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

```
<div class="_youClassName_n97f3_18"></div>
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](https://github.com/systemboys/React_Codes/tree/main/Componentes%20e%20elementos#react-codes--componentes-e-elementos "Subir para o topo")

------------

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
[(&uarr;) Subir](https://github.com/systemboys/React_Codes/tree/main/Componentes%20e%20elementos#react-codes--componentes-e-elementos "Subir para o topo")

------------

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
[(&uarr;) Subir](https://github.com/systemboys/React_Codes/tree/main/Componentes%20e%20elementos#react-codes--componentes-e-elementos "Subir para o topo")

------------

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
[(&uarr;) Subir](https://github.com/systemboys/React_Codes/tree/main/Componentes%20e%20elementos#react-codes--componentes-e-elementos "Subir para o topo")

------------

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
[(&uarr;) Subir](https://github.com/systemboys/React_Codes/tree/main/Componentes%20e%20elementos#react-codes--componentes-e-elementos "Subir para o topo")

------------

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
[(&uarr;) Subir](https://github.com/systemboys/React_Codes/tree/main/Componentes%20e%20elementos#react-codes--componentes-e-elementos "Subir para o topo")

------------

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
[(&uarr;) Subir](https://github.com/systemboys/React_Codes/tree/main/Componentes%20e%20elementos#react-codes--componentes-e-elementos "Subir para o topo")

------------

## Incrementando React-FontAwesome

[![React-FontAwesome](https://github.com/systemboys/React_Codes/raw/main/Componentes%20e%20elementos/images/React-FontAwesome.png "React-FontAwesome")](https://github.com/systemboys/React_Codes/raw/main/Componentes%20e%20elementos/images/React-FontAwesome.png "React-FontAwesome")

Implementação de ícones do `React-FontAwesome` em seu projeto.

Importar os componentes:

```javascript
// React-Fontawesome
import { FontAwesomeIcon } from '@fortawesome/react-fontawesome';
import { faPrint } from '@fortawesome/free-solid-svg-icons';
```

> Para cada ícone, você deve consultar o site oficial do [Font Awesome](https://fontawesome.com/ "Font Awesome") e verificar qual a classe você deseja colocando os dados no parâmentro `icon={faPrint}` do elemento HTML.

Elemento HTML:

```javascript
<FontAwesomeIcon icon={faPrint} size="1x" />
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](https://github.com/systemboys/React_Codes/tree/main/Componentes%20e%20elementos#react-codes--componentes-e-elementos "Subir para o topo")

------------

