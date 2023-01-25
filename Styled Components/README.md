# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Styled Components

- [Várias classes na propriedade `className={}`](https://github.com/systemboys/React_Codes/tree/main/Styled%20Components#v%C3%A1rias-classes-na-propriedade-classname "Várias classes na propriedade className={}")
- [Trabalhando com `Styled Components`](https://github.com/systemboys/React_Codes/tree/main/Styled%20Components#trabalhando-com-styled-components "Trabalhando com Styled Components")

## Várias classes na propriedade `className={}`

Interpolar classe para colocar mais de uma:

```javascript
<button className={`${styles.button} ${styles.primary}`}>Enviar</button>
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](https://github.com/systemboys/React_Codes/tree/main/Styled%20Components#react-codes--styled-components "Subir para o topo")


------------

## Trabalhando com Styled Components

Instalando o `Styled Components`:

```
npm i styled-components
```

Instalando o `Type Styled Components` como dependência de desenvolvimento:

```
npm i @types/styled-components -D
```

Arquivo `App.tsx`:

> Vamos colocar um fragmento `<></>` no return, aquela div que renderiza, não aparece no HTML, algo apenas para colocar por volta dos componentes!

```javascript
export function App() {
    return (
        <>
            <Button color="primary" />
            <Button color="secondary" />
            <Button color="danger" />
            <Button color="success" />
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
    color?: 'primary' | 'secondary' | 'danger' | 'success';
}

export function Button({ color = 'primary' }: ButtonProps) {
    return <button className={`${styles.button} ${styles.[color]}`}>Enviar</button>
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
[(&uarr;) Subir](https://github.com/systemboys/React_Codes/tree/main/Styled%20Components#react-codes--styled-components "Subir para o topo")

------------

