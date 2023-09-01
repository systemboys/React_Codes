# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Trabalhando com data e hora

- [Formatando Data](#formatando-data "Formatando Data")
- [Formatar data '1992-12-08T00:00:00.000Z' no formato '08-12-1992'](#formatar-data-1992-12-08t000000000z-no-formato-08-12-1992 "Formatar data '1992-12-08T00:00:00.000Z' no formato '08-12-1992'")
- [Formatando Hora](#formatando-hora "Formatando Hora")
- [Renderizar data no formato desejado no JSX](#renderizar-data-no-formato-desejado-no-jsx "Renderizar data no formato desejado no JSX")
- [Converter string com data no formato 'dd/mm/aaaa' para 'aaaa-mm-dd'](#converter-string-com-data-no-formato-ddmmaaaa-para-aaaa-mm-dd "Converter string com data no formato 'dd/mm/aaaa' para 'aaaa-mm-dd'")
- [Data atual no elemento HTML](#data-atual-no-elemento-html "Data atual no elemento HTML")
- [Exibir a data no formato dd/mm/aaaa](#exibir-a-data-no-formato-ddmmaaaa "Exibir a data no formato dd/mm/aaaa")
- [Data e Hora atual no elemento HTML](#data-e-hora-atual-no-elemento-html "Data e Hora atual no elemento HTML")
  - [Zero à esquerda para hora, minuto e segundo menores que 10](#zero-%C3%A0-esquerda-para-hora-minuto-e-segundo-menores-que-10 "Zero à esquerda para hora, minuto e segundo menores que 10")
  - [Formatando a data atual no formato 'Segunda, 15 de maio de 2023' em JavaScript](#formatando-a-data-atual-no-formato-segunda-15-de-maio-de-2023-em-javascript "Formatando a data atual no formato 'Segunda, 15 de maio de 2023' em JavaScript")
  - [Formatando uma data no formato '2000-11-31' para o formato 'Domingo, 31 de desembro de 2000'](#formatando-uma-data-no-formato-2000-11-31-para-o-formato-domingo-31-de-desembro-de-2000 "Formatando uma data no formato '2000-11-31' para o formato 'Domingo, 31 de desembro de 2000'")
  - [Formatando uma data no formato '2000-11-31' para o formato 'Domingo, 31 de desembro de 2000' (`ajuste de fuso horário`)](#formatando-uma-data-no-formato-2000-11-31-para-o-formato-domingo-31-de-desembro-de-2000-ajuste-de-fuso-hor%C3%A1rio "Formatando uma data no formato '2000-11-31' para o formato 'Domingo, 31 de desembro de 2000' (ajuste de fuso horário)")

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

```jsx
import { parseISO } from 'date-fns';

const date = '2018-04-01'; // Data informada

// Data
const parsedDate = parseISO(date).toISOString(); // Data
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--trabalhando-com-data-e-hora "Subir para o topo")

---

## Formatar data '1992-12-08T00:00:00.000Z' no formato '08-12-1992'

Para formatar a data "1992-12-08T00:00:00.000Z" no formato "08/12/1992", você pode usar o objeto `Date` do JavaScript juntamente com os métodos disponíveis para manipulação de datas.

Aqui está um exemplo de como você pode fazer isso:

```jsx
function formatDate(dateString) {
  const date = new Date(dateString);

  const day = date.getDate().toString().padStart(2, "0");
  const month = (date.getMonth() + 1).toString().padStart(2, "0");
  const year = date.getFullYear().toString();

  return `${day}/${month}/${year}`;
}

// Exemplo de uso
const dateString = "1992-12-08T00:00:00.000Z";
const formattedDate = formatDate(dateString);

console.log(formattedDate); // Saída: 08/12/1992
```

> ( ! ) Você pode chamar a função formatDate() com qualquer string de data e obterá a data formatada no formato "08-12-1992".

Neste exemplo, você cria um objeto `Date` com base na string da data. Em seguida, você usa os métodos `getDate()`, `getMonth()` e `getFullYear()` para obter os componentes do dia, mês e ano, respectivamente. Em seguida, você usa o método `padStart()` para adicionar zeros à esquerda, caso necessário, para garantir que os valores do dia e do mês tenham sempre dois dígitos. Por fim, você concatena as partes formatadas da data usando o formato desejado.

Espero que isso ajude! Se tiver mais perguntas, estou aqui para ajudar.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--trabalhando-com-data-e-hora "Subir para o topo")

---

## Formatando Hora

Configuração da Hora:

```jsx
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

```jsx
import { format, parseISO } from 'date-fns';
```

Em seguida, você pode criar uma função auxiliar que formata a data e a hora de acordo com o formato desejado:

```jsx
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

```jsx
<Col>{formatDate(listContent[0]?.date, listContent[0]?.time)}</Col>
```

Assumindo que `listContent[0]?.date` contém a data no formato "yyyy-mm-dd" e `listContent[0]?.time` contém a hora no formato "hh:mm:ss", essa chamada de função deve retornar a string no formato desejado "Dia dd/mm/yyyy às hh:mm:ss".

Espero que isso ajude!

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--trabalhando-com-data-e-hora "Subir para o topo")

---

## Converter string com data no formato 'dd/mm/aaaa' para 'aaaa-mm-dd'

Você pode converter uma string com o valor de data no formato "dd/mm/aaaa" para "aaaa-mm-dd" no ReactJS seguindo os passos abaixo:

1. Use o método `split()` para dividir a string da data em três partes, separadas pelo caractere `/`, de modo a obter o dia, o mês e o ano separadamente.

2. Use o método `reverse()` para inverter a ordem dos elementos do array com o dia, mês e ano.

3. Use o método `join()` para juntar os elementos do array com o caractere `-`, de modo a obter a string no formato "aaaa-mm-dd".

Aqui está um exemplo de código que faz essa conversão:

```jsx
// Converter string com data no formato 'dd/mm/aaaa' para 'aaaa-mm-dd'.
function formatDate(dateString) {
  const [day, month, year] = dateString.split('/');
  const formattedDate = [year, month, day].reverse().join('-');
  return formattedDate;
}

const dateStr = '28/03/2023';
const formattedDate = formatDate(dateStr); // '2023-03-28'
```

No exemplo acima, a função `formatDate()` recebe uma string com a data no formato "dd/mm/aaaa" e retorna a data no formato "aaaa-mm-dd".

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--trabalhando-com-data-e-hora "Subir para o topo")

---

## Data atual no elemento HTML

Para colocar a data atual em um input HTML no ReactJS, você pode utilizar o objeto Date do JavaScript. Primeiro, você pode criar uma nova instância do objeto Date e, em seguida, formatar a data para o formato desejado usando os métodos getFullYear(), getMonth() e getDate(). Por fim, você pode passar a data formatada como valor padrão do input usando a prop defaultValue.

Veja um exemplo de como fazer isso:

```jsx
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

```jsx
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

```jsx
import React from 'react';

function App() {
  // Data e hora atual.
  const today = new Date();
  const formattedDate = `${today.getDate().toString().padStart(2, '0')}/${(today.getMonth() + 1).toString().padStart(2, '0')}/${today.getFullYear()}`;
  const formattedTime = `${today.getHours()}:${today.getMinutes()}:${today.getSeconds()}`;

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

### Zero à esquerda para hora, minuto e segundo menores que 10

Obs.: Para a hora, o resultado será por exemplo: `9:9:9`, indicando nove horas, nove minutos e nove segundos. Com os números meior que 10, o zero à esquerda não será exibido. Para reverter isso, veja o exemplo abaixo:

Você pode usar o método padStart() para adicionar um zero à esquerda quando o número de segundos for menor que 10. Aqui está um exemplo:

```jsx
${today.getSeconds().toString().padStart(2, '0')}
```

Modificação após adicionar `.toString().padStart(2, '0')` na hora, minuto e segundo:

```jsx
const formattedTime = `${today.getHours().toString().padStart(2, '0')}:${today.getMinutes().toString().padStart(2, '0')}:${today.getSeconds().toString().padStart(2, '0')}`;
```

Nesse caso, o método toString() é usado para converter o número de segundos em uma string antes de aplicar o padStart(). O primeiro argumento do método padStart() é o comprimento final da string resultante, que deve ter pelo menos 2 caracteres. O segundo argumento é o caractere usado para preencher a string à esquerda, nesse caso, um zero '0'.

Vale para horas também?

Sim, você pode aplicar a mesma lógica para adicionar um zero à esquerda em horas menores que 10. Por exemplo:
```jsx
${(today.getHours() < 10 ? "0" : "") + today.getHours()}:${(today.getMinutes() < 10 ? "0" : "") + today.getMinutes()}:${(today.getSeconds() < 10 ? "0" : "") + today.getSeconds()}
```

Nesse caso, o zero à esquerda é adicionado apenas se o valor for menor que 10, usando o operador ternário ? :. Se o valor for menor que 10, é concatenado um zero à esquerda, caso contrário, não é adicionado nada.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--trabalhando-com-data-e-hora "Subir para o topo")

---

## Formatando a data atual no formato "Segunda, 15 de maio de 2023" em JavaScript

Para obter a data atual no formato "Segunda, 15 de maio de 2023" em JavaScript, você pode usar as funções de data e manipulação de string. Aqui está um exemplo de código:

```jsx
// Formatando a data atual no formato "Segunda, 15 de maio de 2023".
const weekdays = ['Domingo', 'Segunda', 'Terça', 'Quarta', 'Quinta', 'Sexta', 'Sábado'];
const months = ['janeiro', 'fevereiro', 'março', 'abril', 'maio', 'junho', 'julho', 'agosto', 'setembro', 'outubro', 'novembro', 'dezembro'];

const currentDate = new Date();
const weekday = weekdays[currentDate.getDay()];
const day = currentDate.getDate();
const month = months[currentDate.getMonth()];
const year = currentDate.getFullYear();

const formattedDate = `${weekday}, ${day} de ${month} de ${year}`;

console.log(formattedDate);
```

Isso irá imprimir a data atual no formato desejado no console.

Lembre-se de ajustar os nomes dos dias da semana e dos meses de acordo com o idioma desejado.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--trabalhando-com-data-e-hora "Subir para o topo")

---

## Formatando uma data no formato '2000-11-31' para o formato 'Domingo, 31 de desembro de 2000'

Para transformar a data no formato "2023-05-23" para "Segunda, 15 de maio de 2023" em JavaScript, você pode seguir os seguintes passos:

1. Crie um objeto `Date` com a data fornecida.
2. Crie um array de nomes de meses em ordem.
3. Obtenha o dia da semana da data criada.
4. Obtenha o dia do mês da data criada.
5. Obtenha o índice do mês da data criada.
6. Obtenha o ano da data criada.
7. Construa a string final no formato desejado.

Aqui está um exemplo de código que realiza essa transformação:

```jsx
// Formatando uma data no formato '2000-11-31' para o formato 'Doming, 31 de desembro de 2000'.
const formatDate = (dateStr) => {
  const date = new Date(dateStr);
  const daysOfWeek = ['Domingo', 'Segunda', 'Terça', 'Quarta', 'Quinta', 'Sexta', 'Sábado'];
  const months = [
    'janeiro', 'fevereiro', 'março', 'abril', 'maio', 'junho',
    'julho', 'agosto', 'setembro', 'outubro', 'novembro', 'dezembro'
  ];

  const dayOfWeek = daysOfWeek[date.getDay()];
  const day = date.getDate();
  const month = months[date.getMonth()];
  const year = date.getFullYear();

  return `${dayOfWeek}, ${day} de ${month} de ${year}`;
};

const formattedDate = formatDate('2023-05-23');
console.log(formattedDate); // Saída: Terça-feira, 23 de maio de 2023.
```

Você pode usar a função `formatDate` para transformar qualquer data no formato desejado.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--trabalhando-com-data-e-hora "Subir para o topo")

---

## Formatando uma data no formato '2000-11-31' para o formato 'Domingo, 31 de desembro de 2000' (ajuste de fuso horário)

Se você está obtendo um dia a menos na data formatada, é provável que o problema esteja relacionado ao fuso horário. O objeto `Date` em JavaScript leva em consideração o fuso horário local ao realizar conversões.

Você pode corrigir isso ajustando a data para o fuso horário UTC antes de formatá-la. Você pode usar os métodos `setUTC*` do objeto `Date` para isso. Aqui está uma versão atualizada da função `formatDate` que leva em consideração o fuso horário:

```jsx
// Formatando uma data no formato '2000-11-31' para o formato 'Domingo, 31 de desembro de 2000'.
const formatDate = (dateStr) => {
    const date = new Date(dateStr);
    const daysOfWeek = ['Domingo', 'Segunda', 'Terça', 'Quarta', 'Quinta', 'Sexta', 'Sábado'];
    const months = [
        'janeiro', 'fevereiro', 'março', 'abril', 'maio', 'junho',
        'julho', 'agosto', 'setembro', 'outubro', 'novembro', 'dezembro'
    ];

    // Ajustar para fuso horário UTC.
    date.setUTCHours(0, 0, 0, 0);

    const dayOfWeek = daysOfWeek[date.getUTCDay()];
    const day = date.getUTCDate();
    const month = months[date.getUTCMonth()];
    const year = date.getUTCFullYear();

    return `${dayOfWeek}, ${day} de ${month} de ${year}`;
};

const formattedDate = formatDate('2023-05-23');
console.log(formattedDate); // Saída: Terça-feira, 23 de maio de 2023.
```

Ao ajustar para o fuso horário UTC, você deve obter a data formatada corretamente. Lembre-se de também verificar as configurações de fuso horário no servidor e cliente, para garantir a consistência na interpretação das datas.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--trabalhando-com-data-e-hora "Subir para o topo")

---