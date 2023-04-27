# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Trabalhando com números

- [Formatação de números](#formata%C3%A7%C3%A3o-de-n%C3%BAmeros "Formatação de números")

---

## Formatação de números

Para formatar o valor como moeda brasileira, você pode usar o método `toLocaleString` do JavaScript, passando `'pt-BR'` como parâmetro para definir o idioma e `{ style: 'currency', currency: 'BRL' }` para definir o formato de moeda. Então, o seu código ficaria assim:

```javascript
<p className={styles.price}>
  {card.value !== "0.00" 
    ? parseFloat(card.value).toLocaleString('pt-BR', { style: 'currency', currency: 'BRL' })
    : "Grátis"
  }
</p>
```

Este código irá verificar se o valor de `card.value` é diferente de `"0.00"`. Se for, ele irá formatar o valor como moeda brasileira e exibir na página. Se não, ele irá exibir "Grátis". Note que, para usar o método `toLocaleString`, é preciso converter o valor para um número, por isso incluí o método `parseFloat` na expressão.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--trabalhando-com-n%C3%BAmeros "Subir para o topo")

---