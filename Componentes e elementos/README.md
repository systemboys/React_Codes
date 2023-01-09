# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Componentes e elementos

- [Formulário responsívo com React-Bootstrap](https://github.com/systemboys/React_Codes/tree/main/Componentes%20e%20elementos#formul%C3%A1rio-respons%C3%ADvo-com-react-bootstrap "Formulário responsívo com React-Bootstrap")

------------

## Formulário responsívo com React-Bootstrap

Se o `React-Bootstrap` não estiver instalado no `npm`, execute o seguinte comando no terminal:

```javascript
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