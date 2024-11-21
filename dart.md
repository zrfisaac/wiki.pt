# Dart

Bem-vindo à **Wiki do Dart**! Este guia fornece uma visão geral do Dart, uma linguagem de programação de código aberto e de propósito geral otimizada para a construção de aplicativos móveis, de desktop e para a web.

## Descrição

Dart é uma linguagem desenvolvida pelo Google, projetada para o desenvolvimento do lado do cliente. É particularmente popular para a criação de aplicativos móveis com Flutter, mas também é utilizada para desenvolvimento backend e para a web. O Dart compila tanto para código nativo quanto para JavaScript, permitindo alto desempenho em diversas plataformas.

Dart oferece recursos como um sistema de tipos forte, programação assíncrona com `Futures` e `Streams`, e um conjunto robusto de bibliotecas para o desenvolvimento moderno.

## Links Úteis

- [Site Oficial do Dart](https://dart.dev/)
- [Downloads do Dart](https://dart.dev/get-dart)
- [Documentação Oficial do Dart](https://dart.dev/guides)
- [DartPad](https://dartpad.dev/) - Um editor online para experimentar o código Dart
- [Repositório Oficial do Dart no GitHub](https://github.com/dart-lang/sdk)

## Índice

- [Descrição](#descrição)
- [Links Úteis](#links-úteis)
- [Versões do Dart](#versões-do-dart)
- [Configurando o Dart](#configurando-o-dart)
- [Exemplos Básicos de Código em Dart](#exemplos-básicos-de-código-em-dart)

## Versões do Dart

O Dart é continuamente atualizado com novos recursos, melhorias e correções de bugs. Aqui estão algumas das versões mais notáveis:

- **Dart 2.0**  
  A versão principal que introduziu a segurança de null, facilitando a prevenção de erros relacionados a valores nulos, além de melhorar o desempenho da linguagem.

- **Dart 2.12**  
  Introduziu suporte estável para segurança de null e melhorou a inferência de tipos, o que ajuda os desenvolvedores a escreverem códigos mais seguros e confiáveis.

- **Dart 2.18**  
  Melhorou o desempenho da Dart VM e introduziu novos recursos da linguagem, como extensões e um melhor tratamento de erros.

Para uma lista completa de mudanças e versões, acesse o [Changelog do Dart](https://dart.dev/tools/sdk/releases).

## Configurando o Dart

Para começar a usar o Dart, siga os passos abaixo:

1. **Baixar o SDK do Dart**  
   Acesse a [página de downloads do Dart](https://dart.dev/get-dart) e baixe o SDK para o seu sistema operacional (Windows, macOS ou Linux).

2. **Instalar o Dart**  
   Siga as instruções de instalação na página oficial para o seu sistema operacional. Isso instalará tanto o SDK do Dart quanto a ferramenta de linha de comando `dart`.

3. **Instalar uma IDE**  
   Embora você possa usar qualquer editor de texto para escrever código Dart, é recomendável usar uma IDE como o Visual Studio Code ou IntelliJ IDEA com o plugin Dart para facilitar o desenvolvimento.

4. **Verificar a Instalação**  
   Após a instalação, verifique se o Dart foi instalado corretamente executando o seguinte comando no terminal:

   ```bash
   dart --version
   ```

5. **Criar um Projeto em Dart**  
   Você pode criar um novo projeto em Dart executando o seguinte comando:

   ```bash
   dart create meu_projeto
   ```

   Isso criará um novo projeto Dart com um arquivo simples `main.dart`.

## Exemplos Básicos de Código em Dart

Aqui estão alguns exemplos simples para ajudá-lo a começar com o Dart:

**Olá Mundo em Dart**

1. Crie um novo arquivo chamado `olamundo.dart`.
2. Adicione o seguinte código ao arquivo `olamundo.dart`:

```dart
void main() {
  print('Olá, Mundo!');
}
```

3. Para rodar o código, use o seguinte comando no terminal:

```bash
dart olamundo.dart
```

**Criando uma Classe em Dart**

```dart
class Carro {
  String modelo;
  int ano;

  Carro(this.modelo, this.ano);

  void exibirInfo() {
    print('Modelo: $modelo, Ano: $ano');
  }
}

void main() {
  var meuCarro = Carro('Toyota', 2020);
  meuCarro.exibirInfo();
}
```

**Programação Assíncrona em Dart**

Dart tem suporte nativo para programação assíncrona usando `Future` e `Stream`. Aqui está um exemplo usando `Future`:

```dart
Future<String> buscarDados() async {
  await Future.delayed(Duration(seconds: 2));
  return 'Dados recuperados!';
}

void main() async {
  print('Buscando dados...');
  String resultado = await buscarDados();
  print(resultado);
}
```

**Usando Dart com Flutter**

Se você está usando o Dart com Flutter, pode criar um projeto Flutter com o seguinte comando:

```bash
flutter create meu_app_flutter
```

Isso criará um projeto Flutter, onde o Dart é usado para a lógica do negócio.

