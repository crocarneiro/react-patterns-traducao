# Função componente

Funções componentes são o jeito mais simples de declarar componentes reusáveis. Eles são apenas funções.

```jsx
function Greeting() {
  return <div>Hi there!</div>;
}
```

Colete as `props` do primeiro argumento da sua função.

```jsx
function Greeting(props) {
  return <div>Hi {props.name}!</div>;
}
```

Defina qualquer número de variáveis locais para fazer o que você precisa na sua função componente.

**Sempre retorne seu componente React no final.**

```jsx
function Greeting(props) {
  let style = {
    fontWeight: "bold",
    color: context.color
  };

  return <div style={style}>Hi {props.name}!</div>;
}
```

Configure `props` padrões usando `defaultProps`.

```jsx
function Greeting(props) {
  return <div>Hi {props.name}!</div>;
}
Greeting.defaultProps = {
  name: "Guest"
};
```