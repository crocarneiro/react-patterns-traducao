# Filhos do Tipo Array

Prover um `array` como filho de um componente é muito comum. É assim que listas são desenhadas em React.

Nós usamos `map()` para criar um vetor de elementos React para cada valor no `array` (ou vetor).

```html
<ul>
  {["first", "second"].map(item => (
    <li>{item}</li>
  ))}
</ul>
```

Isso é equivalente à prover um `array` literal.

```html
<ul>{[<li>first</li>, <li>second</li>]}</ul>
```

Veja o exemplo deste repositório de teste do [react-bootstrap](https://react-bootstrap.netlify.com/): [https://github.com/crocarneiro/react-bootstrap-test/blob/master/src/App.js](https://github.com/crocarneiro/react-bootstrap-test/blob/master/src/App.js).

Este padrão pode ser combinado com [desestruturação de `props`](destructuring_props.html), [propagação de atributos JSX](jsx_spread_attributes.html), e outros componentes, para fazer algo profissional.

```html
<ul>
  {arrayOfMessageObjects.map(({ id, ...message }) => (
    <Message key={id} {...message} />
  ))}
</ul>
```