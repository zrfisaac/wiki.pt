# Flutter

Bem-vindo à **Wiki do Flutter**! Este guia fornece uma visão geral do Flutter, um framework de desenvolvimento de interface de usuário de código aberto criado pelo Google para a construção de aplicativos nativos, móveis, web e de desktop com uma única base de código.

## Descrição

O Flutter é um framework de UI (interface do usuário) que permite criar aplicativos de alta performance para dispositivos móveis, web e desktop. Ele usa a linguagem Dart e oferece uma abordagem altamente personalizada para a construção de interfaces. Flutter permite o desenvolvimento rápido com "Hot Reload", e sua arquitetura reativa permite que os desenvolvedores criem interfaces ricas e interativas.

## Links Úteis

- [Site Oficial do Flutter](https://flutter.dev/)
- [Documentação Oficial do Flutter](https://flutter.dev/docs)
- [Flutter GitHub Repository](https://github.com/flutter/flutter)
- [DartPad (Editor Online para Flutter)](https://flutter.dev/docs/get-started/flutter-for)
- [Flutter Community](https://flutter.dev/community)

## Índice

- [Descrição](#descrição)
- [Links Úteis](#links-úteis)
- [Versões do Flutter](#versões-do-flutter)
- [Configurando o Flutter](#configurando-o-flutter)
- [Exemplos Básicos de Código no Flutter](#exemplos-básicos-de-código-no-flutter)

## Versões do Flutter

O Flutter é atualizado regularmente com novas versões que introduzem melhorias e recursos adicionais. Aqui estão algumas versões notáveis:

- **Flutter 1.0**  
  Lançado em dezembro de 2018, o Flutter 1.0 trouxe uma base sólida para o desenvolvimento de aplicativos nativos com uma única base de código.

- **Flutter 2.0**  
  Introduziu o suporte para desenvolvimento web e de desktop, expandindo ainda mais a plataforma e permitindo criar aplicativos em várias plataformas com uma única base de código.

- **Flutter 3.0**  
  Melhorias no desempenho e estabilidade, além de suporte completo para aplicativos móveis, web e desktop.

Para mais detalhes sobre as versões, acesse o [Changelog do Flutter](https://docs.flutter.dev/release/whats-new).

## Configurando o Flutter

Para começar a usar o Flutter, siga os passos abaixo:

1. **Baixar o SDK do Flutter**  
   Acesse a [página de downloads do Flutter](https://flutter.dev/docs/get-started/install) e baixe o SDK para o seu sistema operacional (Windows, macOS ou Linux).

2. **Instalar o Flutter**  
   Siga as instruções de instalação para o seu sistema operacional. Isso instalará o Flutter SDK e as ferramentas necessárias para desenvolver e testar aplicativos Flutter.

3. **Verificar a Instalação**  
   Após a instalação, verifique se o Flutter foi instalado corretamente executando o seguinte comando no terminal:

   ```bash
   flutter doctor
   ```

   Esse comando verifica se todos os componentes necessários estão instalados corretamente.

4. **Criar um Novo Projeto Flutter**  
   Você pode criar um novo projeto Flutter executando o seguinte comando:

   ```bash
   flutter create meu_app
   ```

   Isso criará um novo projeto Flutter com um template básico.

5. **Executar o Aplicativo**  
   Para rodar o aplicativo em um emulador ou dispositivo conectado, use:

   ```bash
   flutter run
   ```

## Exemplos Básicos de Código no Flutter

Aqui estão alguns exemplos simples para ajudá-lo a começar com o Flutter:

**Aplicativo Básico Flutter - Olá Mundo**

1. Crie um novo arquivo Dart chamado `main.dart`.
2. Adicione o seguinte código ao arquivo `main.dart`:

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          title: Text('Olá Mundo no Flutter'),
        ),
        body: Center(
          child: Text('Olá, Flutter!'),
        ),
      ),
    );
  }
}
```

3. Para rodar o código, use o seguinte comando no terminal:

```bash
flutter run
```

**Criando um Botão no Flutter**

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          title: Text('Botão no Flutter'),
        ),
        body: Center(
          child: ElevatedButton(
            onPressed: () {
              print('Botão pressionado!');
            },
            child: Text('Pressione-me'),
          ),
        ),
      ),
    );
  }
}
```

**Usando ListView no Flutter**

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          title: Text('Lista no Flutter'),
        ),
        body: ListView(
          children: [
            ListTile(
              title: Text('Item 1'),
            ),
            ListTile(
              title: Text('Item 2'),
            ),
            ListTile(
              title: Text('Item 3'),
            ),
          ],
        ),
      ),
    );
  }
}
```

**Usando Navegação no Flutter**

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: HomeScreen(),
    );
  }
}

class HomeScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Navegação no Flutter'),
      ),
      body: Center(
        child: ElevatedButton(
          onPressed: () {
            Navigator.push(
              context,
              MaterialPageRoute(builder: (context) => SecondScreen()),
            );
          },
          child: Text('Ir para a segunda tela'),
        ),
      ),
    );
  }
}

class SecondScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Segunda Tela'),
      ),
      body: Center(
        child: ElevatedButton(
          onPressed: () {
            Navigator.pop(context);
          },
          child: Text('Voltar'),
        ),
      ),
    );
  }
}
```

