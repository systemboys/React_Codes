# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Arrays

- [Obter dados de um `Array` com o `map()`](#obter-dados-de-um-array-com-map "Obter dados de um Array com map()")

---
## Obter dados de um Array com `map()`

Crie um arquivo como por exemplo `data.js`:

```javascript
export default[
    {id:1, option: 'Opção 1'},
    {id:2, option: 'Opção 2'},
    {id:3, option: 'Opção 3'},
    {id:4, option: 'Opção 4'},
    {id:5, option: 'Opção 5'},
    {id:6, option: 'Opção 6'},
    {id:7, option: 'Opção 7'},
    {id:8, option: 'Opção 8'},
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
