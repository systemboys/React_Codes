# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Arrays

- [Obter dados de um `Array` com o `map()`](#obter-dados-de-um-array-com-map "Obter dados de um Array com map()")
- [Executar Array dentro do retorno de um componente](#executar-array-dentro-do-retorno-de-um-componente "Executar Array dentro do retorno de um componente")
- [Mapeamento direto no map()](#mapeamento-direto-no-map "Mapeamento direto no map()")
- [Pequenos macetes de Array](#pequenos-macetes-de-array "Pequenos macetes de Array")
    - [Filtrar itens mistos de um array](#link-do-texto-de-comeco "Filtrar itens mistos de um array")
    - [Filtrar os números ímpares de um array](#link-do-texto-de-comeco "Filtrar os números ímpares de um array")
    - [Retornar o index da idade maior que 30 anos](#link-do-texto-de-comeco "Retornar o index da idade maior que 30 anos")

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

# Pequenos macetes de Array

## Filtrar itens mistos de um array

Imagina que você tem um array e ele contenha informações mistas, números e strings, mas você quer filtrar para obter apenas os números. Veja o código exemplo:

```javascript
const array = ['1', 2, 'three', 7];

console.log(array.filter(Number.isInteger));

// Resultado: Array [ 2, 7 ]
```

> Entre todos os itens dentro do array, será filtrado apenas os números deixando de fora do novo array as strings.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--arrays "Subir para o topo")

---

## Filtrar os números ímpares de um array

Você tem um array contendo números e você precisa filtrar apenas os ímpares, veja abaixo:

```javascript
const array2 = [1, 2, 3, 4, 5, 6, 7]; 

console.log(array2.filter((number) => number % 2 !== 0));

// Resultado: Array(4) [ 1, 3, 5, 7 ]
```

> O método `filter` retornou um novo array com os elementos que passaram no teste implantados na função fornecida.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--arrays "Subir para o topo")

---

## Retornar o index da idade maior que 30 anos

No exemplo, tratasse de obter apenas o index maior que 30 anos:

```javascript
const ages = [18, 20, 32, 23, 18, 17, 68];

ages.findIndex((n) => n > 30)

// Resultado: 2
```

> Analisando que no array, o 18 está na posição "0" e o 68 na "6", o `findIndex()` está obtendo o primeiro da lista que é maior que 30, no caso é o valor que está na posição 2 que é o "32". Obs.: O 68 também é maior que 30, mas não é o primeiro no caso.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--arrays "Subir para o topo")

---