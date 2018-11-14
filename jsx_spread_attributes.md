# Propagação de Atributos JSX

Propagação de atributos é uma característica do [JSX](https://reactjs.org/docs/introducing-jsx.html). É uma sintaxe para prover as propriedades de um objeto como atributos JSX.

Seguindo o exemplo da [atribuição via desestruturação](destructuring_props.html), nós podemos propagar `restProps` através da nossa `<div>`.

```jsx
function Greeting({ name, ...restProps }) {
  return <div {...restProps}>Hi {name}!</div>;
}
```

[![Edit React rest parameter syntax test](https://codesandbox.io/static/img/play-codesandbox.svg)](https://codesandbox.io/s/ov669r8xwy)

Isso torna o componente `Greeting` super flexível. Nós podemos passar atributos DOM para `Greeting` e confiar que eles serão propagados através da `div`.

```jsx
<Greeting name="Fancy pants" className="fancy-greeting" id="user-greeting" />
```

Evite propagar `props` que não sejam atributos DOM para os componentes.

[atribuição via desestruturação](destructuring_props.html) é popular porque te dá a oportunidade de separar as `props` específicas do componente dos atributos DOM específicos da plataforma.

```jsx
function Greeting({ name, ...platformProps }) {
  return <div {...platformProps}>Hi {name}!</div>;
}
```