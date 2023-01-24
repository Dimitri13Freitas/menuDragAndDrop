# Menu Mobile

Plugin para um menu mobile compativel com desktop.

```js
// 1 - Copie o arquivo menuMobile.js da pasta js e cole no seu site.

// 2 - Link o arquivo utilizando o import em seu arquivo javascript pessoal, Exemplo:
import { MenuMobile } from "./js/plugins/menuMobile.js";
```

ATENÇÃO, LEIA ABAIXO

Para que a importação funcione seu javascript pessoal precisa ser ´type='module'.

Exemplo:

```html
<script type="module" src="./js/script.js"></script>
;
```

```js
import { MenuMobile } from "./js/plugins/menuMobile.js";

// 4 - Atribua a uma variavel a classe escolhida, Exemplo:
const menu = new MenuMobile();
```

Para que o plugin funcione é necessario colocar dois elementos HTML como parâmetro da classe. Neste caso são:

- O container que será o elemento pai de toda que vai ser usado como 'wrapper'.
- E sua navegação.

```js
// Apenas o elemento para receber valores e os elementos para a comparação
const searchBar = new SearchOnKeyDown("input", "ul li");
```

Caso seus elementos de pesquisa possuem filhos é acrescentado mais um parâmetro, Exemplo:

```js
// Esta é a mesma lógica do exemplo a cima, porém e preciso adicionar o tópico que deseja usarm como elemento de comparação
const searchBar = new SearchOnKeyDown("input", ".container div", "h1");
```

Logo após isso inicie o script com:

```js
searchBar.init();
```

Assim já está pronto para uso.

Se ainda resta alguma dúvida olhe a pasta de `examples` no repositório, onde tem os dois exemplos na prática.

## Preferências

A seguir vem funções que você pode ou não ativar, pois não afetam no propósito principal do plugin:

### FocusOnLoad

Com esta função ativa o elemento input já vai estar pronto para escrita sem que precise ser selecionado a cada carregamento de página.

```js
// Considerando os exemplos ja vistos
searchBar.focusOnLoad();
```

### Anima

A cada evento de pesquisa irá ser executada uma animação que você mesmo pode criar.
Atribuindo a sua animação a uma classe só é necessario colocar a mesma como parametro na função

```js
searchBar.anima("anima");
// Considere o exemplo a abaixo
```

```css
/* Este é um exemplo de animação no CSS, não se limite a somente isso use sua criatividade */
.anima {
  animation: animacao 0.3s;
}
@keyframes animacao {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
```

### LoadEffect

Semelhante a função de Anima vista acima, porém só é preciso colocar o elemento que você mesmo pode criar com sua criatividade.

```js
searchBar.loadEffect(".loadElement");
// Considere o exemplo a abaixo
```

```html
<div class="loadElement"></div>
```

```css
/* Para que o script funcione da melhor forma é preciso colocar o loadElement como "display: none;" */
.loadElement {
  display: none;
  height: 5px;
  animation: animacao;
}

@keyframes animacao {
  from {
    width: 0;
  }
  to {
    width: 30px;
  }
}
```
