# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Trabalhando com data e hora

- [Formatando Hata](https://github.com/systemboys/React_Codes/... "Formatando Hata")
- [Formatando Hora](https://github.com/systemboys/React_Codes/... "Formatando Hora")

------------

## Formatando data

Instalar módulo Datas:

```javascript
npm install date-fns
```

Os tipos de de data do TypeScript:

```javascript
npm i @types/date-fns
```

Configuração de Data:

```javascript
// Data
import { parseISO } from 'date-fns';

const date = '2018-04-01 18:00:00'; // Data informada

// Data
const parsedDate = parseISO(date).toISOString();
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](https://github.com/systemboys/React_Codes/... "Subir para o topo")

------------

## Formatando Hora

Configuração da Hora:

```javascript
const hour = "18:19:49"; // Hora informada

// Hora
const Hours = new Date("1970-01-01T" + hour + "Z"); // Hora
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](https://github.com/systemboys/React_Codes/... "Subir para o topo")

------------
