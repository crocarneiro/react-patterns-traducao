# Renderização de propriedade

Aqui está um componente que renderiza uma função de `callback`. Ele é inútil, mas é uma boa ilustração para iniciar.

```jsx
const Width = ({ children }) => children(500);
```

O componente chama `children` como uma função com um número qualquer de argumentos. Aqui, foi passado apenas um argumento, o número `500`. Para usar este componente, nós passamos para ele uma [função como filho](function_as_children.html).

```html
<Width>{width => <div>window is {width}</div>}</Width>
```

Então obtemos a saída.

```html
<div>window is 500</div>
```

Com esta configuração, nós podemos usar este `width` para tomar decisões sobre a renderização.

```html
<Width>
  {width => (width > 600 ? <div>min-width requirement met!</div> : null)}
</Width>
```

[![Edit 2018_11_21_react_render_prop_teste1](https://codesandbox.io/static/img/play-codesandbox.svg)](https://codesandbox.io/s/81n2x025j9)

Se nós planejamos utilizar muito esta condição, nós podemos definir outros componentes para encapsular a lógica reutilizada.

```jsx
const MinWidth = ({ width: minWidth, children }) => (
  <Width>{width => (width > minWidth ? children : null)}</Width>
);
```

Obviamente um componente `Width` estático não é útil porém, um que acompanha a largura da janela é. Aqui está uma amostra da implementação.

```jsx
class WindowWidth extends React.Component {
  constructor() {
    super();
    this.state = { width: 0 };
  }

  componentDidMount() {
    this.setState(
      { width: window.innerWidth },
      window.addEventListener("resize", ({ target }) =>
        this.setState({ width: target.innerWidth })
      )
    );
  }

  render() {
    return this.props.children(this.state.width);
  }
}
```

[![Edit 2018_11_21_react_render_prop_teste2](https://codesandbox.io/static/img/play-codesandbox.svg)](https://codesandbox.io/s/91prr35x0w)

Muitos desenvolvedores preferem [componentes de alta ordem](high_order_component.html) para esse tipo de funcionalidade. É uma questão de preferência.