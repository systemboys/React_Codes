# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Arrays

- [Obter dados de um Array com map()](https://github.com/systemboys/React_Codes/tree/main/Array#obter-dados-de-um-array-com-map "Obter dados de um Array com map()")

------------
## Obter dados de um Array com `map()`

Crie um arquivo como por exemplo `data.js`:

```javascript
export default[
    {id:1, file: 'https://site.com/img/background1.png', name:'file 1'},
    {id:2, file: 'https://site.com/img/background2.png', name:'file 2'},
    {id:3, file: 'https://site.com/img/background3.png', name:'file 3'},
    {id:4, file: 'https://site.com/img/background4.png', name:'file 4'},
    {id:5, file: 'https://site.com/img/background5.png', name:'file 5'},
    {id:6, file: 'https://site.com/img/background6.png', name:'file 6'},
    {id:7, file: 'https://site.com/img/background7.png', name:'file 7'},
    {id:8, file: 'https://site.com/img/background8.png', name:'file 8'},
]
```

> Cada linha entre as chaves, vamos fazer de conta que é um registro!

Importe o arquivo no componente:

```javascript
// Arquivo de dados onde estão os planos de fundo
import Background from './data.js';
```

No componente (dentro da função que carrega o conteúdo) crie a função como mostra abaixo:

```javascript
// Função que faz o laço em busca dos itens do Array
function List_Background() {
    return Background.map(Background => {
        return (
            <li>
                {Background.name}
            </li>
        )
    })
}
```

No `retorno` de seu componente, vamos interpolar a função:

```javascript
return (
    <>
        <ul>
            {List_Background()}
        </ul>
    </>
);
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](https://github.com/systemboys/React_Codes/tree/main/Array#react-codes--arrays "Subir para o topo")
