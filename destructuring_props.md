# Atribuição via Desestruturação

[Atribuição via desestruturação](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Operators/Atribuicao_via_desestruturacao) é uma característica do Javascript que foi adicionada à linguagem no ES2015, então, pode não parecer muito familiar. Pense nela como o oposto da atribuição literal.

```jsx
let person = { name: "chantastic" };
let { name } = person;
```

Funciona com vetores também.

```jsx
let things = ["one", "two"];
let [first, second] = things;
```

Atribuição via desestruturação é muito usada in funções componentes. Essas declarações de componentes abaixo são equivalentes:

```jsx
function Greeting(props) {
  return <div>Hi {props.name}!</div>;
}

function Greeting({ name }) {
  return <div>Hi {name}!</div>;
}
```

Existe uma sintaxe para coletar as `props` restantes para dentro de um objeto, ela é chamada de [sintaxe de parâmetros rest](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Functions/rest_parameters) e se parece com isso:

```jsx
function Greeting({ name, ...restProps }) {
  return <div>Hi {name}!</div>;
}
```

[![Edit React rest parameter syntax test](https://codesandbox.io/static/img/play-codesandbox.svg)](https://codesandbox.io/s/ov669r8xwy)

Aqueles três pontos (`...`) pegam todas as propriedades restantes e atribuem-nas ao objeto `restProps`.

Então, o que você faz com o `restProps` uma vez que você o tem?

Continue lendo...