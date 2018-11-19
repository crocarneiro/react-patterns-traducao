# Renderização Condicional

Você não pode utilizar comandos `if/else` dentro da declaração de um componente, portanto, o [operador condicional (ternário)](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Operators/Operador_Condicional) e a [avaliação de curto-circuito (short-circuit)](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Operators/Operadores_Logicos#Short-Circuit_Evaluation) são seus amigos.

### `if`
```jsx
{
  condition && <span>Rendered when `truthy`</span>;
}
```
[![Edit n32yo273nl](https://codesandbox.io/static/img/play-codesandbox.svg)](https://codesandbox.io/s/n32yo273nl)

### `unless`
```jsx
{
  condition || <span>Rendered when `falsy`</span>;
}
```
[![Edit 2018_11_19_react_conditional_rendering_test2](https://codesandbox.io/static/img/play-codesandbox.svg)](https://codesandbox.io/s/zw18667l1m)

### `if-else`
```jsx
{
  condition ? (
    <span>Rendered when `truthy`</span>
  ) : (
    <span>Rendered when `falsy`</span>
  );
}
```
[![Edit 2018_11_19_react_conditional_rendering_test3](https://codesandbox.io/static/img/play-codesandbox.svg)](https://codesandbox.io/s/jv8jro7969)