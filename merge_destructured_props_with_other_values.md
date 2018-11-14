# Mesclagem de Props Desestruturadas com Outros Valores

Componentes são abstrações.<br />
Boas abstrações permitem extensão.

Considere este componente que usa um atributo `class` para estilizar um botão.

```jsx
function MyButton(props) {
  return <button className="btn" {...props} />;
}
```

Isso funciona bem até que tentemos extender com outra classe.

```jsx
<MyButton className="delete-btn">Delete...</MyButton>
```

[![Edit 2018_11_14_react_merge_destructured_props_test](https://codesandbox.io/static/img/play-codesandbox.svg)](https://codesandbox.io/s/7wkm0qno4x)

Neste caso, `delete-btn` substitui `btn`.

A ordem é muito importante na [propagação de atributos JSX](jsx_spread_attributes.html).<br />
A `props.className` sendo propagada está sobreescrevendo o `className` em nosso componente.

Nós podemos mudar a ordem mas agora `className` nunca vai ser nada além de `btn`.

```jsx
function MyButton(props) {
  return <button {...props} className="btn" />;
}
```

Nós precisamos usar [atribuição via desestruturação](destructuring_props.html) para pegar a `className` de entrada e mesclar com a `className` base. Podemos fazer isso simplesmente adicionando todos os valores em um array e juntando eles com um espaço em branco.

```jsx
function MyButton({ className, ...props }) {
  let classNames = ["btn", className].join(" ");
  return <button className={classNames} {...props} />;
}
```

[![Edit 2018_11_14_react_merge_destructured_props_test2](https://codesandbox.io/static/img/play-codesandbox.svg)](https://codesandbox.io/s/q57xlp28w)

Para prevenir-se de `undefined` aparecer como uma `className`, use [valores padrões](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment#Default_values_2).

```jsx
function MyButton({ className = "", ...props }) {
  let classNames = ["btn", className].join(" ");
  return <button className={classNames} {...props} />;
}
```