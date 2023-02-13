# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Styled Components

- [Várias classes na propriedade `className={}`](#v%C3%A1rias-classes-na-propriedade-classname "Várias classes na propriedade className={}")
- [Trabalhando com `Styled Components`](#trabalhando-com-styled-components "Trabalhando com Styled Components")
- [`Estilizando` com código `JavaScript`](#estilizando-com-c%C3%B3digo-javascript "Estilizando com código JavaScript")

## Várias classes na propriedade `className={}`

Para usar mais de uma classe em um component, utilizamos o `TemplateString` para utilizar o JavaScript dentro de uma classe:

```javascript
<button className={`${styles.button} ${styles.primary}`}>Enviar</button>
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--styled-components "Subir para o topo")


------------

## Trabalhando com Styled Components

Instalando o `Styled Components`:

```bash
npm i styled-components
```

Instalando o `Type Styled Components` como dependência de desenvolvimento:

```bash
npm i @types/styled-components -D
```

> É importante que você esteja com a `extenção do Styled Components` instalada em seu VSCode!

[![Extenção do Styled Components](https://github.com/systemboys/React_Codes/raw/main/Styled%20Components/images/vscode-styled-components.png "Extenção do Styled Components")](https://github.com/systemboys/React_Codes/raw/main/Styled%20Components/images/vscode-styled-components.png "Extenção do Styled Components")

Arquivo `App.tsx`:

> Vamos colocar um fragmento `<></>` no return, aquela div que renderiza, não aparece no HTML, algo apenas para colocar por volta dos componentes!

```javascript
export function App() {
    return (
        <>
            <Button variant="primary" />
            <Button variant="secondary" />
            <Button variant="danger" />
            <Button variant="success" />
            <Button />
        </>
    )
}
```

Aplicando estilizações condicionais às propriedades que os botões recebem.

No arquivo `Button.tsx` está a estilização dos nossos botões:

```javascript
import styles from './Button.module.css';

interface ButtonProps {
    variant?: 'primary' | 'secondary' | 'danger' | 'success';
}

export function Button({ variant = 'primary' }: ButtonProps) {
    return <button className={`${styles.button} ${styles.[variant]}`}>Enviar</button>
}
```

Vamos fazer o uso do CSS Modules, criando um arquivo `Button.module.css`.

```css
.button {
    width: 100px;
    height: 40px;
}
.primary {
    background: purple;
}
.secondary {
    background: orange;
}
.danger {
    background: red;
}
.success {
    background: green;
}
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--styled-components "Subir para o topo")

------------

### Estilizando com código JavaScript

Vamos começar com um arquivo `Button.styles.js` ou `*.ts`, dependendo do seu projeto:

```javascript
import styled, { css } from 'styled-components';

export type ButtonVariant = 'primary' | 'secondary' | 'danger' | 'success';

interface ButtonContainerProps {
    variant: ButtonVariant;
}

const ButtonVariants = {
    primary: 'purple',
    secondary: 'orange',
    danger: 'red',
    success: 'green'
}

export const ButtonContainer = styled.button<ButtonContainerProps>`
    width: 100px;
    height: 40px;

    ${props => {
        return css`
            background-color: ${ButtonVariants[props.variant]}
        `
    }}
`
```

No arquivo `Button.tsx`, na className:

```javascript
import { ButtonContainer, ButtonVariant } from './Button.module.css';

interface ButtonProps {
    variant?: ButtonVariant;
}

export function Button({ variant = 'primary' }: ButtonProps) {
    return <ButtonContainer variant={variant}>Enviar</ButtonContainer>
}
```

> Dessa forma, estamos utilizando um components estilizado!

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--styled-components "Subir para o topo")


