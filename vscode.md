# Visual Studio Code

Bem-vindo à **Wiki do Visual Studio Code**! Este guia fornece uma visão geral do Visual Studio Code (VS Code), um editor de código leve e poderoso desenvolvido pela Microsoft.

## Descrição

O Visual Studio Code (VS Code) é um editor de código-fonte open-source disponível para Windows, macOS e Linux. Ele é projetado para o desenvolvimento web e em nuvem, proporcionando um ambiente rápido e personalizável para programar em linguagens como JavaScript, Python, TypeScript, HTML, CSS e muito mais.

O VS Code inclui uma variedade de recursos, como ferramentas de depuração, integração com Git, um marketplace para extensões e suporte para várias linguagens de programação e frameworks.

## Links Úteis

- [Site Oficial do Visual Studio Code](https://code.visualstudio.com/)
- [Downloads do Visual Studio Code](https://code.visualstudio.com/download)
- [Documentação Oficial do Visual Studio Code](https://code.visualstudio.com/docs)
- [Marketplace do Visual Studio Code](https://marketplace.visualstudio.com/vscode)
- [Repositório do Visual Studio Code no GitHub](https://github.com/Microsoft/vscode)

## Índice

- [Descrição](#descrição)
- [Links Úteis](#links-úteis)
- [Versões do Visual Studio Code](#versões-do-visual-studio-code)
- [Configuração Básica e Instalação do Visual Studio Code](#configuração-básica-e-instalação-do-visual-studio-code)
- [Exemplos de Código Básico no Visual Studio Code](#exemplos-de-código-básico-no-visual-studio-code)

## Versões do Visual Studio Code

O Visual Studio Code é frequentemente atualizado, com novas versões trazendo melhorias, correções de bugs e novos recursos. As versões notáveis incluem:

- **VS Code 1.0**  
  O lançamento estável inicial, que introduziu um editor rápido, leve e personalizável. Incluía suporte para uma grande variedade de linguagens e extensões.

- **VS Code 1.20**  
  Introduziu várias melhorias na depuração, juntamente com novos recursos para compartilhamento ao vivo e melhor suporte ao Git.

- **VS Code 1.30**  
  Esta versão trouxe controle de versão integrado e extensões para mais linguagens, incluindo uma popular para Python.

- **VS Code 1.50**  
  Adicionou vários recursos como espaço de trabalho multi-root, aprimoramentos no IntelliSense e integração com Git, além de novas extensões para produtividade.

Para uma lista completa de recursos e melhorias em cada lançamento, consulte as [Notas de Lançamento do VS Code](https://code.visualstudio.com/updates).

## Configuração Básica e Instalação do Visual Studio Code

Para começar com o Visual Studio Code, siga os passos abaixo:

1. **Baixar o Visual Studio Code**  
   Acesse a página de [Downloads do Visual Studio Code](https://code.visualstudio.com/download) e escolha a versão adequada para o seu sistema operacional (Windows, macOS ou Linux).

2. **Instalar o Visual Studio Code**  
   Após o download do instalador, execute-o e siga as instruções de configuração. O instalador configurará automaticamente as dependências necessárias.

3. **Instalar Extensões**  
   O Visual Studio Code pode ser estendido com várias extensões. Para instalar extensões:
   - Abra o VS Code.
   - Vá até a visualização **Extensões** clicando no ícone de Extensões na Barra de Atividades no lado da janela.
   - Pesquise as extensões que deseja instalar (exemplo: Python, GitLens, Prettier) e clique em **Instalar**.

4. **Configurar o Git**  
   Se você pretende usar o Git dentro do VS Code, certifique-se de que o Git está instalado no seu sistema. Você pode instalá-lo a partir do [site oficial do Git](https://git-scm.com/). Após instalar o Git, o VS Code detectará automaticamente.

5. **Personalizar o VS Code**  
   O VS Code permite alterar temas, fontes e configurações. Você pode acessar as configurações clicando em **Arquivo > Preferências > Configurações** ou pressionando **Ctrl + ,**.

## Exemplos de Código Básico no Visual Studio Code

Aqui estão alguns exemplos básicos para ajudar você a começar a programar no Visual Studio Code:

**Exemplo "Hello World" em JavaScript**  
1. Abra o Visual Studio Code e crie um novo arquivo chamado `app.js`.
2. Escreva o seguinte código JavaScript em `app.js`:

```javascript
console.log("Hello, World!");
```

3. Para rodar o arquivo JavaScript:
   - Abra o terminal no VS Code selecionando **Terminal > Novo Terminal**.
   - Execute o comando `node app.js` para ver a saída no terminal.

**Exemplo "Hello World" em Python**  
1. Abra o Visual Studio Code e crie um novo arquivo chamado `hello.py`.
2. Escreva o seguinte código Python em `hello.py`:

```python
print("Hello, World!")
```

3. Para rodar o arquivo Python:
   - Abra o terminal no VS Code selecionando **Terminal > Novo Terminal**.
   - Execute o comando `python hello.py` para ver a saída no terminal.

**Criando e Usando uma Classe em JavaScript**

```javascript
class Car {
    constructor(model, year) {
        this.model = model;
        this.year = year;
    }

    displayInfo() {
        console.log(`Model: ${this.model}, Year: ${this.year}`);
    }
}

const myCar = new Car("Toyota", 2020);
myCar.displayInfo();
```

**Usando Git no Visual Studio Code**

1. **Clonar um Repositório**: Abra o painel **Controle de Origem**, clique no botão **Clonar Repositório** e forneça a URL do repositório.
2. **Fazer um Commit**: Após fazer alterações, abra o painel **Controle de Origem**, escreva uma mensagem de commit e clique em **Commit**.
3. **Enviar as Alterações**: Envie suas alterações para o repositório remoto selecionando **Sincronizar** no painel **Controle de Origem**.
