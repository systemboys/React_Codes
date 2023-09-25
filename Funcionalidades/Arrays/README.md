# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes")

## Arrays

### *Sumário*

- [Obter dados de um `Array` com o `map()`](#obter-dados-de-um-array-com-map "Obter dados de um Array com map()")
- [Executar Array dentro do retorno de um componente](#executar-array-dentro-do-retorno-de-um-componente "Executar Array dentro do retorno de um componente")
- [Mapeamento direto no map()](#mapeamento-direto-no-map "Mapeamento direto no map()")
- [Pequenos macetes de Array](#pequenos-macetes-de-array "Pequenos macetes de Array")
    - [Filtrar itens mistos de um array](#filtrar-itens-mistos-de-um-array "Filtrar itens mistos de um array")
    - [Filtrar os números ímpares de um array](#filtrar-os-n%C3%BAmeros-%C3%ADmpares-de-um-array "Filtrar os números ímpares de um array")
    - [Retornar o index da idade maior que 30 anos](#retornar-o-index-da-idade-maior-que-30-anos "Retornar o index da idade maior que 30 anos")
- [Array `map()`, `filter()` e `reduce()`](#array-map-filter-e-reduce "Array map(), filter() e reduce()")
    - [Array map()](#array-map "Array map()")
    - [Array filter()](#array-filter "Array filter()")
    - [Array Reduce()](#array-reduce "Array Reduce()")

---
## Obter dados de um Array com `map()`

Crie um arquivo como por exemplo `data.js`:

```jsx
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

```jsx
// Arquivo de dados onde estão os Itens
import YourItems from './data.js';
```

No componente (dentro da função que carrega o conteúdo) coloque a função antes do retorna, o `map()` com os itens do Array:

```jsx
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

```jsx
return (
    <>
        <select>
            {List_YourItems()}
        </select>
    </>
);
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

## Executar Array dentro do retorno de um componente

Para mapear o array dentro do retorno de um componente em um select por exemplo, você pode fazer o seguinte:

```jsx
function MeuComponente() {
    const dataTableRecords = [
        { value: 'valor 1', label: 'Opção 1' },
        { value: 'valor 2', label: 'Opção 2' },
        { value: 'valor 3', label: 'Opção 3' }
    ];
    return (
        <select>
            {dataTableRecords.map(item => (
                <option key={item.value} value={item.value}>{item.label}</option>
            ))}
        </select>
    );
}
```

Nesse exemplo, criamos um array `dataTableRecords` com três objetos que representam as opções do select. Em seguida, utilizamos o método `map()` para criar um array de elementos `<option>` com base nos objetos do array `dataTableRecords`. Cada elemento `<option>` tem o atributo value com o valor do objeto e o texto da opção com o atributo label. Note que é importante incluir a propriedade `key` em cada elemento gerado pelo `map()` para ajudar o React a identificar qual item deve ser atualizado em caso de mudanças na lista. Por fim, o array de elementos `<option>` é renderizado dentro do elemento `<select>`.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

## Mapeamento direto no map()

Colocar o array diretamente no `map()`.

```jsx
function MeuComponente() {
    return (
        <Container>
            {[
                { link: 'https://www.google.com/', name: 'Google', title: 'Ir para o Google' },
                { link: 'https://www.youtube.com/', name: 'YouTube', title: 'Ir para o YouTube' },
                { link: 'https://www.bing.com/', name: 'Bing', title: 'Ir para o Bing' }
            ].map(item => (
                <>
                   <p><a href={item.link} target="_blank" title={item.title}>{item.name}</a></p>
                </>
            ))}
        </Container>
    );
}
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

# Pequenos macetes de Array

## Filtrar itens mistos de um array

Imagina que você tem um array e ele contenha informações mistas, números e strings, mas você quer filtrar para obter apenas os números. Veja o código exemplo:

```jsx
const array = ['1', 2, 'three', 7];

console.log(array.filter(Number.isInteger));

// Resultado: Array [ 2, 7 ]
```

> Entre todos os itens dentro do array, será filtrado apenas os números deixando de fora do novo array as strings.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

## Filtrar os números ímpares de um array

Você tem um array contendo números e você precisa filtrar apenas os ímpares, veja abaixo:

```jsx
const array2 = [1, 2, 3, 4, 5, 6, 7]; 

console.log(array2.filter((number) => number % 2 !== 0));

// Resultado: Array(4) [ 1, 3, 5, 7 ]
```

> O método `filter` retornou um novo array com os elementos que passaram no teste implantados na função fornecida.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

## Retornar o index da idade maior que 30 anos

No exemplo, tratasse de obter apenas o index maior que 30 anos:

```jsx
const ages = [18, 20, 32, 23, 18, 17, 68];

ages.findIndex((n) => n > 30)

// Resultado: 2
```

> Analisando que no array, o 18 está na posição "0" e o 68 na "6", o `findIndex()` está obtendo o primeiro da lista que é maior que 30, no caso é o valor que está na posição 2 que é o "32". Obs.: O 68 também é maior que 30, mas não é o primeiro no caso.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---

# Array map(), filter() e reduce()

Quem é que nunca precisou manipular arrays? Extrair somente os IDs de uma lista de produtos, ou obter dessa lista, somente os produtos de uma determinada categoria, ou então calcular o valor total dos produtos dessa lista. Nesse exemplo veremos três funções que resolvem esses problemas de forma simples.

## Array map()

O map() permite que você crie um novo array utilizando informações de um array já existente. No nosso caso, o nosso array já existente é o "produtos", e o novo array que será criado será o "ids":

```jsx
const produtos = [
  { id: 1, name: 'detergente', valor: 2.00, categoria: 'limpeza' },
  { id: 2, name: 'amaciante', valor: 6.50, categoria: 'limpeza' },
  { id: 3, name: 'pão', valor: 2.00, categoria: 'alimento' },
  { id: 4, name: 'queijo', valor: 7.00, categoria: 'alimento' },
  { id: 5, name: 'leite', valor: 2.20, categoria: 'alimento' }
];

// Passando a função de callback.
const ids = produtos.map(produto => produto.id);
const nomes = produtos.map(produto => produto.name);

// Teste 1.
console.log(ids); // Retornando [1, 2, 3, 4, 5].

// Teste 2.
console.log(nomes); // Retornando ["detergente", "amaciante", "pão", "queijo", "leite"]
```

Para o map() funcionar, foi passado para o map() uma função callback, essa função recebe cada produto retornando o resultado, o valor que vai no novo array.

> Utilizando o map(), você consegue criar um novo array a partir do array original contendo informações ou transformações dessas informações.

Dicamos que você tem um array de números e que você quer duplicá-los criando um novo array com os resultados.

```jsx
const numeros = [1, 2, 3, 4, 5];

// Duplicar.
const duplicados = numeros.map(x => x * 2);

// Teste.
console.log(duplicados); // Retornando [2, 4, 6, 8, 10].
```

> Os valores do primeiro array foram transformados e seu resultado foi para um novo array criado pelo map(). Então, o callback que é passado para o map() recebe cada item e retorna o valor que você quer no array final.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

## Array filter()

O array filter() é um conceito um pouco mais simples de entender. Você cria um novo array a partir de outro array filtrando fora alguns itens. Será imposta uma regra para o map() e sendo respeitada determinado parâmetro.

Dado o array `produtos`, e queremos que vá para o novo array apenas os alimentos. Veja o código abaixo:

```jsx
const produtos = [
  { id: 1, name: 'detergente', valor: 2.00, categoria: 'limpeza' },
  { id: 2, name: 'amaciante', valor: 6.50, categoria: 'limpeza' },
  { id: 3, name: 'pão', valor: 2.00, categoria: 'alimento' },
  { id: 4, name: 'queijo', valor: 7.00, categoria: 'alimento' },
  { id: 5, name: 'leite', valor: 2.20, categoria: 'alimento' }
];

const alimentos = produtos.filter(p => p.categoria === 'alimento');

// Teste 1.
console.log(alimentos); // Retornando [Object, Object, Object].

/* Teste 1 retornando os objetos completos de cada um.
[Object, Object, Object]
  0: Object
    id: 3
    name: "pão"
    valur: 2
    categoria: "alimento"
  1: Object
    id: 4
    name: "queijo"
    valur: 7
    categoria: "alimento"
  2: Object
    id: 3
    name: "leite"
    valur: 2.2
    categoria: "alimento"
*/

// Teste 2.
console.log(alimentos.map(a => a.nome)); // Retornando ["pão", "queijo", "leite"].
```

No "Teste 1" `console.log(alimentos)` Foi declarada a constante `alimentos` com a função que filtra `p` (digamos que `p` é produtos), no caso, algo que tenha um valor que seja convertido em boleano (`true` ou `false`). O retorno do console.log é `[Object, Object, Object]`.

No "Teste 2" `console.log(alimentos.map(a => a.nome))` é combinado um array com o outro array. Digamos que você queira apenas os nomes dos alimentos ao invés do objeto completo. O retorno do console.log é `["pão", "queijo", "leite"]`.

No "Teste 3" `` se você quiser combinar o `filter()` com o `map()` é possível, basta colocar o map() na declaração da constante como no exemplo abaixo:

```jsx
const alimentos = produtos
    .filter(p => p.categoria === 'alimento');
    .map(a => a.nome);
```

> Isso é interessante, você pode combinar uma função com a outra e cada uma faz uma coisa específica. Os métodos podem ser colocados um abaixo do outro.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

## Array Reduce

Com o Reduce você pode gerar um único valor atravéz de uma coleção (uma lista, um array ...).

Digamos que você tenha um array de números, e que você quer somar todos os valores de uma coluna no array obtendo um valor total. Com o Reduce isso é possível.

Veja código abaixo, como o Reduce funciona:

```jsx
// Definida a constante com o seguinte array:
const numeros = [1, 2, 3, 4];

// Vamos somar todos os números dentro do array:
const total = numeros.reduce((acc, numero) => acc + numero, 0);

// Teste.
console.log(total); // Retornando "10".
```

> O reduce, na primeira vez que ele intera com o array, ele pega o "1" e o "2" do array, o primeiro elemento vai ser o acumulado e o segundo vai se chamar "numero", ele retorna o acumulado mais o numero, no retorno do acumulado mais o numero ele soma o primeiro e o segundo elemento que no caso é o "1" e o "2" retornando "3", após isso, ele busca o próximo item do array que é o "3", o resultado da rodada anterior é "6", soma com o próximo trazendo o resultado "10". O zero "0" no final da linha na constante "total", é uma opção de passar um valor inicial para o array para ser o primeiro valor acumulado e o numero vai ser o primeiro item do array.

Agora utilizando o array de "produtos" para somar o valor total deles:

```jsx
const produtos = [
  { id: 1, name: 'detergente', valor: 2.00, categoria: 'limpeza' },
  { id: 2, name: 'amaciante', valor: 6.50, categoria: 'limpeza' },
  { id: 3, name: 'pão', valor: 2.00, categoria: 'alimento' },
  { id: 4, name: 'queijo', valor: 7.00, categoria: 'alimento' },
  { id: 5, name: 'leite', valor: 2.20, categoria: 'alimento' }
];

const total = produtos.reduce((acc, p) => acc + p.valor, 0);

// Teste.
console.log(total); // Retornando "39.2".
```

> Sempre a cada rodada que acontece do reduce, o valor que você está retornando vai se tornar o próximo acumulado e ele pega o próximo do array.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#sum%C3%A1rio "Subir para o topo")

---