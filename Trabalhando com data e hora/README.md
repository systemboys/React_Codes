# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Trabalhando com data e hora

- [Formatando Data](#formatando-data "Formatando Data")
- [Formatando Hora](#formatando-hora "Formatando Hora")
- [Renderizar data no formato desejado no JSX](#renderizar-data-no-formato-desejado-no-jsx "Renderizar data no formato desejado no JSX")

---

## Formatando data

Instalar módulo Datas:

```bash
npm install date-fns
```

Os tipos de data do TypeScript:

```bash
npm i @types/date-fns
```

Configuração de Data:

```javascript
import { parseISO } from 'date-fns';

const date = '2018-04-01'; // Data informada

// Data
const parsedDate = parseISO(date).toISOString(); // Data
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--trabalhando-com-data-e-hora "Subir para o topo")

---

## Formatando Hora

Configuração da Hora:

```javascript
const hour = "18:19:49"; // Hora informada

// Hora
const Hours = new Date("1970-01-01T" + hour + "Z"); // Hora
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--trabalhando-com-data-e-hora "Subir para o topo")

---

## Renderizar data no formato desejado no JSX

[![Imagem de exemplo](https://site.com/img/exemplo.png "Imagem de exemplo")](http://link.com "Imagem de exemplo")

Para formatar datas e horas no formato desejado, você pode usar a biblioteca `date-fns`, que é uma das bibliotecas mais populares para lidar com datas em JavaScript.

Para formatar a data e a hora, você pode usar as funções `format` e `parseISO` do `date-fns`.

Primeiro, importe as funções necessárias:

```javascript
import { format, parseISO } from 'date-fns';
```

Em seguida, você pode criar uma função auxiliar que formata a data e a hora de acordo com o formato desejado:

```javascript
// Dia dd/mm/aaaa às 00:00:00
import { format, parseISO } from 'date-fns';
function formatDate(dateStr, timeStr) {
    const parsedDate = parseISO(dateStr);
    const formattedDate = format(parsedDate, 'dd/MM/yyyy');
    const formattedTime = format(parseISO(timeStr), 'HH:mm:ss');
    return `Dia ${formattedDate} às ${formattedTime}`;
}
```

> Aqui, a função `format` é usada novamente para formatar a hora. Ela recebe a string da hora (`timeStr`) como argumento e usa a mesma abordagem da formatação da data. O formato '`HH:mm:ss`' é usado para formatar a hora no formato de 24 horas. Com essa mudança, a hora deve ser formatada corretamente no componente e a saída deve ser do formato "Dia dd/mm/yyyy às HH:mm:ss". Espero que agora esteja tudo certo!

Essa função recebe duas strings: a data e a hora em formato de string. Ela usa a função `parseISO` para converter a string de data em um objeto `Date`, e em seguida usa a função `format` para formatar a data no formato desejado ('dd/MM/yyyy'). Por fim, a função retorna uma string com o texto "Dia" seguido da data formatada e "às" seguido da hora.

No seu componente, você pode chamar essa função passando os valores das colunas "date" e "time" como argumentos:

A hora deve ser formatada com o seguinte formato: 'HH:mm:ss', onde HH representa as horas em formato de 24 horas (00-23), mm representa os minutos (00-59) e ss representa os segundos (00-59).

Para formatar a hora corretamente, você pode usar a função `format` do `date-fns` da seguinte forma:

```javascript
<Col>{formatDate(listContent[0]?.date, listContent[0]?.time)}</Col>
```

Assumindo que `listCompanySystem[0]?.date` contém a data no formato "yyyy-mm-dd" e `listCompanySystem[0]?.time` contém a hora no formato "hh:mm:ss", essa chamada de função deve retornar a string no formato desejado "Dia dd/mm/yyyy às hh:mm:ss".

Espero que isso ajude!

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--trabalhando-com-data-e-hora "Subir para o topo")

---
