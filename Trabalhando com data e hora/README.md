# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Trabalhando com data e hora

- [Formatando Data](https://github.com/systemboys/React_Codes/tree/main/Trabalhando%20com%20data%20e%20hora#formatando-data "Formatando Data")
- [Formatando Hora](https://github.com/systemboys/React_Codes/tree/main/Trabalhando%20com%20data%20e%20hora#formatando-hora "Formatando Hora")

------------

## Formatando data

Instalar módulo Datas:

```javascript
npm install date-fns
```

Os tipos de data do TypeScript:

```javascript
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
[(&uarr;) Subir](https://github.com/systemboys/React_Codes/tree/main/Trabalhando%20com%20data%20e%20hora#react-codes--trabalhando-com-data-e-hora "Subir para o topo")

------------

## Formatando Hora

Configuração da Hora:

```javascript
const hour = "18:19:49"; // Hora informada

// Hora
const Hours = new Date("1970-01-01T" + hour + "Z"); // Hora
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](https://github.com/systemboys/React_Codes/tree/main/Trabalhando%20com%20data%20e%20hora#react-codes--trabalhando-com-data-e-hora "Subir para o topo")

------------
