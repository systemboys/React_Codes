# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Componentes e elementos

- [Formulário responsívo com React-Bootstrap](https://github.com/systemboys/React_Codes/tree/main/Componentes%20e%20elementos#formul%C3%A1rio-respons%C3%ADvo-com-react-bootstrap "Formulário responsívo com React-Bootstrap")
- [Abas horizontais com React-Bootstrap](https://github.com/systemboys/React_Codes/tree/main/Componentes%20e%20elementos#abas-horizontais-com-react-bootstrap "Abas horizontais com React-Bootstrap")
- [Responsive grids com React-Bootstrap](https://github.com/systemboys/React_Codes/tree/main/Componentes%20e%20elementos#responsive-grids-com-react-bootstrap "Responsive grids com React-Bootstrap")
- [Buttons com React-Bootstrap](https://github.com/systemboys/React_Codes/tree/main/Componentes%20e%20elementos#buttons-com-react-bootstrap "Buttons com React-Bootstrap")
- [Utilizando o CSS Modules do React](https://github.com/systemboys/React_Codes/tree/main/Componentes%20e%20elementos#utilizando-o-css-modules-do-react "Utilizando o CSS Modules do React")

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
// Abas horizontais
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

