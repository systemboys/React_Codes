# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Trabalhando com data e hora

- [Formatando Data](#formatando-data "Formatando Data")
- [Formatando Hora](#formatando-hora "Formatando Hora")
- [Renderizar data no formato desejado no JSX](#renderizar-data-no-formato-desejado-no-jsx "Renderizar data no formato desejado no JSX")
- [Data atual no elemento HTML](#data-atual-no-elemento-html "Data atual no elemento HTML")
- [Exibir a data no formato dd/mm/aaaa](#exibir-a-data-no-formato-ddmmaaaa "Exibir a data no formato dd/mm/aaaa")
- [Data e Hora atual no elemento HTML](#data-e-hora-atual-no-elemento-html "Data e Hora atual no elemento HTML")
  - [Zero à esquerda para hora, minutos e segundos menores que 10](#zero-%C3%A0-esquerda-para-hora-minutos-e-segundos-menores-que-10 "Zero à esquerda para hora, minutos e segundos menores que 10")

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

Assumindo que `listContent[0]?.date` contém a data no formato "yyyy-mm-dd" e `listContent[0]?.time` contém a hora no formato "hh:mm:ss", essa chamada de função deve retornar a string no formato desejado "Dia dd/mm/yyyy às hh:mm:ss".

Espero que isso ajude!

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--trabalhando-com-data-e-hora "Subir para o topo")

---

## Data atual no elemento HTML

Para colocar a data atual em um input HTML no ReactJS, você pode utilizar o objeto Date do JavaScript. Primeiro, você pode criar uma nova instância do objeto Date e, em seguida, formatar a data para o formato desejado usando os métodos getFullYear(), getMonth() e getDate(). Por fim, você pode passar a data formatada como valor padrão do input usando a prop defaultValue.

Veja um exemplo de como fazer isso:

```javascript
import React from 'react';

function App() {
  const today = new Date();
  const formattedDate = `${today.getFullYear()}-${today.getMonth() + 1}-${today.getDate()}`;

  return (
    <div>
      <input type="date" defaultValue={formattedDate} />
    </div>
  );
}

export default App;
```

Este exemplo cria uma instância do objeto Date contendo a data atual e, em seguida, formata-a no formato "YYYY-MM-DD". Em seguida, a data formatada é passada como valor padrão para um input HTML do tipo "date".

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--trabalhando-com-data-e-hora "Subir para o topo")

---

## Exibir a data no formato dd/mm/aaaa

Para exibir a data no formato dd/mm/aaaa em um input HTML no ReactJS, você pode usar o objeto Date do JavaScript. Para formatar a data, você pode usar os métodos getDay(), getMonth() e getFullYear().

Veja um exemplo de como fazer isso:

```javascript
import React from 'react';

function App() {
  const today = new Date();
  const formattedDate = `${today.getDate().toString().padStart(2, '0')}/${(today.getMonth() + 1).toString().padStart(2, '0')}/${today.getFullYear()}`;

  return (
    <div>
      <input type="text" defaultValue={formattedDate} />
    </div>
  );
}

export default App;
```

Este exemplo cria uma instância do objeto Date contendo a data atual. Em seguida, a data é formatada no formato "dd/mm/aaaa" e é passada como valor padrão para um input HTML do tipo "text". Observe que o método padStart é usado para adicionar um zero à esquerda quando o dia ou mês é menor que 10.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--trabalhando-com-data-e-hora "Subir para o topo")

---

## Data e Hora atual no elemento HTML

Para adicionar a hora atual em um input HTML no ReactJS, você pode usar o objeto Date do JavaScript. Para formatar a hora, você pode usar os métodos getHours(), getMinutes() e getSeconds().

Veja um exemplo de como fazer isso:

```javascript
import React from 'react';

function App() {
  // Data e hora atual.
  const today = new Date();
  const formattedDate = `${today.getDate().toString().padStart(2, '0')}/${(today.getMonth() + 1).toString().padStart(2, '0')}/${today.getFullYear()}`;
  const formattedTime = `${today.getHours().toString().padStart(2, '0')}:${today.getMinutes()}:${today.getSeconds().toString().padStart(2, '0')}`;

  return (
    <div>
      <input type="text" defaultValue={formattedDate} />
      <input type="text" defaultValue={formattedTime} />
    </div>
  );
}

export default App;
```

Este exemplo cria uma instância do objeto Date contendo a data e hora atuais. Em seguida, a hora é formatada no formato "HH:mm:ss" e é passada como valor padrão para um input HTML do tipo "time".

### Zero à esquerda para hora, minutos e segundos menores que 10

Obs.: Para a hora, o resultado será por exemplo: `9:9:9`, indicando nove horas, nove minutos e nove segundos. Com os números meior que 10, o zero à esquerda não será exibido. Para reverter isso, veja o exemplo abaixo:

Você pode usar o método padStart() para adicionar um zero à esquerda quando o número de segundos for menor que 10. Aqui está um exemplo:

```javascript
${today.getSeconds().toString().padStart(2, '0')}
```

Nesse caso, o método toString() é usado para converter o número de segundos em uma string antes de aplicar o padStart(). O primeiro argumento do método padStart() é o comprimento final da string resultante, que deve ter pelo menos 2 caracteres. O segundo argumento é o caractere usado para preencher a string à esquerda, nesse caso, um zero '0'.

Vale para horas também?

Sim, você pode aplicar a mesma lógica para adicionar um zero à esquerda em horas menores que 10. Por exemplo:
```javascript
${(today.getHours() < 10 ? "0" : "") + today.getHours()}:${(today.getMinutes() < 10 ? "0" : "") + today.getMinutes()}:${(today.getSeconds() < 10 ? "0" : "") + today.getSeconds()}
```

Nesse caso, o zero à esquerda é adicionado apenas se o valor for menor que 10, usando o operador ternário ? :. Se o valor for menor que 10, é concatenado um zero à esquerda, caso contrário, não é adicionado nada.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--trabalhando-com-data-e-hora "Subir para o topo")

---
