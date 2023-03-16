# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Arrays

- [Obter dados de um `Array` com o `map()`](#obter-dados-de-um-array-com-map "Obter dados de um Array com map()")
- [Executar Array dentro do retorno de um componente](#executar-array-dentro-do-retorno-de-um-componente "Executar Array dentro do retorno de um componente")
- [Mapeamento direto no map()](#mapeamento-direto-no-map "Mapeamento direto no map()")

---
## Obter dados de um Array com `map()`

Crie um arquivo como por exemplo `data.js`:

```javascript
export default [
    { id:1, option: 'Opção 1' },
    { id:2, option: 'Opção 2' },
    { id:3, option: 'Opção 3' },
    { id:4, option: 'Opção 4' },
    { id:5, option: 'Opção 5' },
    { id:6, option: 'Opção 6' },
    { id:7, option: 'Opção 7' },
    { id:8, option: 'Opção 8' }
]
```

> Cada linha entre as chaves, vamos fazer de conta que é um registro!

Importe o arquivo no componente:

```javascript
// Arquivo de dados onde estão os Itens
import YourItems from './data.js';
```

No componente (dentro da função que carrega o conteúdo) coloque a função antes do retorna, o `map()` com os itens do Array:

```javascript
// Função que faz o laço em busca dos itens do Array
function List_YourItems() {
    return YourItems.map(YourItems => {
        return (
            <option value={YourItems.id}>{YourItems.option}</option>
        )
    })
}
```

No `retorno` de seu componente onde deve ser listados os itens do Array, vamos interpolar a função:

```javascript
return (
    <>
        <select>
            {List_YourItems()}
        </select>
    </>
);
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--arrays "Subir para o topo")

---

## Executar Array dentro do retorno de um componente

Para mapear o array dentro do retorno de um componente em um select por exemplo, você pode fazer o seguinte:

```javascript
function MeuComponente() {
    const opcoes = [
        { valor: 'valor1', label: 'Opção 1' },
        { valor: 'valor2', label: 'Opção 2' },
        { valor: 'valor3', label: 'Opção 3' }
    ];
    return (
        <select>
            {opcoes.map(opcao => (
                <option key={opcao.valor} value={opcao.valor}>{opcao.label}</option>
            ))}
        </select>
    );
}
```

Nesse exemplo, criamos um array `opcoes` com três objetos que representam as opções do select. Em seguida, utilizamos o método `map()` para criar um array de elementos `<option>` com base nos objetos do array `opcoes`. Cada elemento `<option>` tem o atributo value com o valor do objeto e o texto da opção com o atributo label. Note que é importante incluir a propriedade `key` em cada elemento gerado pelo `map()` para ajudar o React a identificar qual item deve ser atualizado em caso de mudanças na lista. Por fim, o array de elementos `<option>` é renderizado dentro do elemento `<select>`.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--arrays "Subir para o topo")

---

## Mapeamento direto no map()

Colocar o array diretamente no `map()`.

```javascript
function MeuComponente() {
    return (
        <Container>
            {[
                { link: 'https://www.google.com/', name: 'Google', title: 'Ir para o Google' },
                { link: 'https://www.youtube.com/', name: 'YouTube', title: 'Ir para o YouTube' },
                { link: 'https://www.bing.com/', name: 'Bing', title: 'Ir para o Bing' }
            ].map(opcao => (
                <>
                   <p><a href={opcao.link} target="_blank" title={opcao.title}>{opcao.name}</a></p>
                </>
            ))}
        </Container>
    );
}
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--arrays "Subir para o topo")

---