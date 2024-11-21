# CSS

Este guia fornece informações essenciais sobre o uso do CSS (Cascading Style Sheets) no desenvolvimento web, abordando conceitos básicos, sintaxe, propriedades de estilo e práticas comuns. O CSS é utilizado para controlar a aparência e o layout de um site, permitindo que você estilize elementos como texto, cores e layouts, além de posicionar elementos na página.

## Índice

- [Introdução ao CSS](#introdução-ao-css)
  Visão geral do CSS e suas principais características.
  
- [Configurando o CSS](#configurando-o-css)
  Instruções de como configurar e usar o CSS no seu projeto.
  
- [Sintaxe do CSS](#sintaxe-do-css)
  Compreensão da sintaxe e estrutura das regras CSS.
  
- [Propriedades Comuns do CSS](#propriedades-comuns-do-css)
  Visão geral das propriedades CSS mais utilizadas e como aplicá-las.
  
- [Seletores CSS](#seletores-css)
  Como direcionar elementos HTML utilizando seletores.
  
- [Técnicas de Layout com CSS](#técnicas-de-layout-com-css)
  Técnicas para controlar layouts usando CSS.
  
- [Design Responsivo com CSS](#design-responsivo-com-css)
  Como criar designs responsivos utilizando consultas de mídia (media queries).

---

## Introdução ao CSS

O CSS (Cascading Style Sheets) é usado para definir a apresentação visual de um documento escrito em HTML ou XML. Ele permite que você aplique estilos como fontes, cores, espaçamento e layout, oferecendo controle total sobre a aparência dos elementos na tela.

Características principais do CSS:
- **Separação de conteúdo e estilo**: O CSS separa a estrutura (HTML) do estilo (CSS), tornando os sites mais fáceis de manter.
- **Natureza cascata**: Os estilos podem ser aplicados em camadas, permitindo substituir regras e facilitar personalizações.
- **Flexibilidade no estilo**: É possível estilizar texto, fundos, bordas e muito mais.

---

## Configurando o CSS

Existem três formas comuns de incluir o CSS nos seus documentos HTML: inline, interno e externo.

### CSS Inline
O CSS inline é aplicado diretamente dentro de um elemento HTML, utilizando o atributo `style`.

```html
<p style="color: blue; font-size: 16px;">Este é um parágrafo azul.</p>
```

### CSS Interno
O CSS interno é colocado dentro de uma tag `<style>` na seção `<head>` do seu documento HTML.

```html
<head>
  <style>
    body {
      background-color: lightgray;
    }
  </style>
</head>
```

### CSS Externo
O CSS externo é definido em um arquivo `.css` separado, que é vinculado ao seu documento HTML. Essa é a forma mais eficiente para estilizar sites maiores.

```html
<head>
  <link rel="stylesheet" type="text/css" href="styles.css">
</head>
```

---

## Sintaxe do CSS

O CSS utiliza uma sintaxe simples para definir regras de estilo. Uma regra consiste em um **seletor** e um **bloco de declaração**.

### Sintaxe Básica

```css
seletor {
  propriedade: valor;
}
```

- **Seletor**: Destina-se a elemento HTML que você deseja estilizar.
- **Propriedade**: O estilo que você deseja aplicar (por exemplo, `color`, `font-size`).
- **Valor**: O valor da propriedade (por exemplo, `blue`, `16px`).

Exemplo:

```css
h1 {
  color: blue;
  font-size: 24px;
}
```

Essa regra altera a cor de elementos `<h1>` para azul e define o tamanho da fonte para 24 pixels.

---

## Propriedades Comuns do CSS

Aqui estão algumas das propriedades CSS mais comuns, utilizadas frequentemente no desenvolvimento web:

### Propriedades de Texto
- **`color`**: Especifica a cor do texto.
  ```css
  p {
    color: #333;
  }
  ```

- **`font-size`**: Define o tamanho da fonte do texto.
  ```css
  p {
    font-size: 16px;
  }
  ```

- **`font-family`**: Especifica a fonte para o texto.
  ```css
  body {
    font-family: Arial, sans-serif;
  }
  ```

### Propriedades do Modelo de Caixa
- **`margin`**: Cria espaço fora do elemento.
  ```css
  div {
    margin: 10px;
  }
  ```

- **`padding`**: Cria espaço dentro do elemento.
  ```css
  div {
    padding: 10px;
  }
  ```

- **`border`**: Adiciona uma borda ao redor do elemento.
  ```css
  div {
    border: 1px solid black;
  }
  ```

### Propriedades de Fundo
- **`background-color`**: Define a cor de fundo de um elemento.
  ```css
  body {
    background-color: #f0f0f0;
  }
  ```

- **`background-image`**: Define uma imagem como fundo.
  ```css
  body {
    background-image: url('background.jpg');
  }
  ```

---

## Seletores CSS

Os seletores são usados para direcionar elementos HTML e aplicar estilos. Existem vários tipos de seletores no CSS.

### Seletores Básicos
- **Seletor Universal (`*`)**: Seleciona todos os elementos.
  ```css
  * {
    margin: 0;
    padding: 0;
  }
  ```

- **Seletor de Elemento (`p`, `h1`, etc.)**: Seleciona todos os elementos de um determinado tipo.
  ```css
  p {
    font-size: 14px;
  }
  ```

- **Seletor de Classe (`.nome-classe`)**: Seleciona elementos com uma classe específica.
  ```css
  .destaque {
    background-color: yellow;
  }
  ```

- **Seletor de ID (`#nome-id`)**: Seleciona um elemento com um ID específico.
  ```css
  #cabecalho-principal {
    color: red;
  }
  ```

### Seletores de Agrupamento
Você pode agrupar vários seletores para aplicar os mesmos estilos a diferentes elementos.

```css
h1, h2, h3 {
  font-family: 'Arial', sans-serif;
}
```

---

## Técnicas de Layout com CSS

O CSS fornece vários métodos para criar layouts, incluindo Flexbox e CSS Grid.

### Flexbox
O Flexbox é um sistema de layout unidimensional que permite um fácil alinhamento dos itens em uma linha ou coluna.

```css
.container {
  display: flex;
  justify-content: space-between;
}

.item {
  flex: 1;
}
```

### CSS Grid
O CSS Grid é um sistema de layout bidimensional que oferece maior controle sobre linhas e colunas.

```css
.container {
  display: grid;
  grid-template-columns: 1fr 2fr 1fr;
}

.item {
  grid-column: span 2;
}
```

---

## Design Responsivo com CSS

O design responsivo garante que um site funcione bem em diferentes tamanhos de tela e dispositivos. As consultas de mídia (media queries) no CSS permitem aplicar estilos com base na largura da tela, tipo de dispositivo ou orientação.

### Exemplo de Consulta de Mídia

```css
@media (max-width: 600px) {
  body {
    background-color: lightblue;
  }
}
```

Essa regra aplica a cor de fundo azul claro quando a largura da tela for de 600px ou menos.

---

## Recursos

- [MDN Web Docs - CSS](https://developer.mozilla.org/pt-BR/docs/Web/CSS)
- [W3Schools - Tutorial CSS](https://www.w3schools.com/css/)
- [CSS-Tricks](https://css-tricks.com/)
