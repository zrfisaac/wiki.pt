# HTML

Este guia fornece informações essenciais sobre o uso do HTML no desenvolvimento web, abordando elementos básicos, estrutura, atributos e práticas comuns. O HTML (Hypertext Markup Language) é a linguagem padrão usada para criar páginas web. Ele fornece a estrutura básica dos documentos da web, incluindo cabeçalhos, parágrafos, links, imagens e formulários.

## Índice

- [Introdução ao HTML](#introdução-ao-html)
  Visão geral do HTML e seus principais recursos.
  
- [Configurando o HTML](#configurando-o-html)
  Instruções sobre como configurar e criar um arquivo HTML.
  
- [Estrutura do HTML](#estrutura-do-html)
  Aprenda sobre a estrutura de um documento HTML.
  
- [Elementos HTML](#elementos-html)
  Visão geral dos elementos HTML mais comuns e seu uso.
  
- [Atributos HTML](#atributos-html)
  Como usar atributos nos elementos HTML.
  
- [Trabalhando com Formulários](#trabalhando-com-formulários)
  Como criar e manipular formulários em HTML.
  
- [Casos de Uso Comuns para HTML](#casos-de-uso-comuns-para-html)
  Exemplos práticos de como o HTML é utilizado.

---

## Introdução ao HTML

HTML (Hypertext Markup Language) é a linguagem fundamental para criar páginas e aplicativos web. Ele define a estrutura e o layout do conteúdo web e é a base de todos os sites.

Principais recursos do HTML:
- **Estrutura do Documento**: Define a organização do conteúdo da web.
- **Semântica**: Usa tags para definir o significado do conteúdo (por exemplo, cabeçalhos, parágrafos, listas).
- **Acessibilidade**: Ajuda a garantir que o conteúdo da web seja acessível para todos os usuários, incluindo aqueles com deficiências.
- **Hiperlinks**: Permite a navegação entre páginas, documentos e recursos.

---

## Configurando o HTML

Para começar a usar HTML, você precisa criar um arquivo HTML com a extensão `.html`. Esse arquivo conterá o seu conteúdo HTML.

### Documento HTML Básico

```html
<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Minha Primeira Página HTML</title>
</head>
<body>
  <h1>Bem-vindo ao Meu Site</h1>
  <p>Esta é uma página HTML simples.</p>
</body>
</html>
```

---

## Estrutura do HTML

Um documento HTML é composto por várias seções principais. Essas seções fornecem a estrutura de uma página web.

### Declaração `<!DOCTYPE html>`

Essa declaração define o tipo de documento e a versão do HTML (neste caso, HTML5).

```html
<!DOCTYPE html>
```

### O Elemento `<html>`

O elemento `<html>` é a raiz do documento HTML e contém todos os outros elementos HTML.

```html
<html lang="pt-br">
  <!-- Conteúdo vai aqui -->
</html>
```

### O Elemento `<head>`

O elemento `<head>` contém metadados sobre o documento, como o título, a codificação de caracteres e links para recursos externos, como folhas de estilo ou scripts.

```html
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Título do Documento</title>
</head>
```

### O Elemento `<body>`

O elemento `<body>` contém o conteúdo visível da página web, como texto, imagens e links.

```html
<body>
  <h1>Título da Página</h1>
  <p>Conteúdo da página.</p>
</body>
```

---

## Elementos HTML

Os elementos HTML são os blocos de construção de uma página web. Eles são definidos por tags e geralmente vêm em pares: uma tag de abertura e uma tag de fechamento.

### Elementos HTML Comuns

- **Cabeçalhos**: As tags `<h1>` a `<h6>` representam cabeçalhos de diferentes níveis.
  ```html
  <h1>Este é um Cabeçalho de Nível 1</h1>
  <h2>Este é um Cabeçalho de Nível 2</h2>
  ```

- **Parágrafos**: A tag `<p>` é usada para parágrafos.
  ```html
  <p>Este é um parágrafo de texto.</p>
  ```

- **Links**: A tag `<a>` define um hiperlink.
  ```html
  <a href="https://exemplo.com">Visite o Exemplo</a>
  ```

- **Imagens**: A tag `<img>` é usada para incorporar imagens.
  ```html
  <img src="imagem.jpg" alt="Descrição da imagem">
  ```

- **Listas**: Listas não ordenadas usam `<ul>` e listas ordenadas usam `<ol>`.
  ```html
  <ul>
    <li>Item 1</li>
    <li>Item 2</li>
  </ul>

  <ol>
    <li>Primeiro item</li>
    <li>Segundo item</li>
  </ol>
  ```

---

## Atributos HTML

Os atributos fornecem informações adicionais sobre os elementos HTML e são adicionados à tag de abertura do elemento.

### Atributos Comuns

- **`href`**: Especifica o URL na tag `<a>`.
  ```html
  <a href="https://www.exemplo.com">Ir para o Exemplo</a>
  ```

- **`src`**: Especifica a fonte de uma imagem na tag `<img>`.
  ```html
  <img src="imagem.jpg" alt="Imagem Exemplo">
  ```

- **`alt`**: Fornece uma descrição alternativa para imagens.
  ```html
  <img src="imagem.jpg" alt="Uma paisagem bonita">
  ```

- **`id`**: Identifica exclusivamente um elemento no documento.
  ```html
  <div id="elementoUnico">Conteúdo</div>
  ```

- **`class`**: Especifica um nome de classe para estilo ou para ser usado por JavaScript.
  ```html
  <p class="destaque">Texto em Destaque</p>
  ```

---

## Trabalhando com Formulários

Formulários são usados para coletar entradas de usuários, como texto, seleções e botões.

### Estrutura Básica de Formulário

```html
<form action="/enviar" method="POST">
  <label for="nome">Nome:</label>
  <input type="text" id="nome" name="nome">
  
  <label for="email">E-mail:</label>
  <input type="email" id="email" name="email">
  
  <input type="submit" value="Enviar">
</form>
```

### Elementos de Formulário

- **Entrada de Texto**: `<input type="text">`
- **Entrada de Senha**: `<input type="password">`
- **Botão de Envio**: `<input type="submit">`
- **Caixa de Seleção**: `<input type="checkbox">`
- **Botão de Rádio**: `<input type="radio">`

---

## Casos de Uso Comuns para HTML

O HTML é usado para uma variedade de fins no desenvolvimento web. Aqui estão alguns casos de uso comuns:

- **Construção de Páginas Web**: Estruturar conteúdo como texto, imagens, links e muito mais.
- **Formulários**: Coletar informações de usuários para inscrições, pesquisas e logins.
- **Incorporar Multimídia**: Incorporar vídeos, áudio e outros tipos de mídia usando tags como `<video>` e `<audio>`.
- **Construção de Navegação**: Criar menus de navegação e links para diferentes seções de um site ou para sites externos.

---

## Recursos Adicionais

- [MDN Web Docs - HTML](https://developer.mozilla.org/pt-BR/docs/Web/HTML)
- [W3Schools - Tutorial de HTML](https://www.w3schools.com/html/)
- [HTML.com](https://html.com/)

