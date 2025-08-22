# <img src="icon/flutter.png" alt="Ícone" width="24"> Flutter

> *Última atualização: 2025-08-12*

O Flutter é um framework da Google para criar aplicativos nativos para iOS, Android, web e desktop usando uma única base de código em Dart. Ele permite construir interfaces visuais modernas e responsivas com desempenho nativo.

## 🗂️ Estrutura

```cpp
projeto/
│
├── android/                          // Código específico do Android (Gradle, Manifest, Java/Kotlin)
│   └── app/build/outputs/            // Output do Android
│       ├── apk/                      // APKs gerados
│       │   └── debug/
│       │       └── app-debug.apk
│       └── bundle/                   // App Bundles (.aab)
│
├── ios/                              // Código específico do iOS (Xcode, Swift/Objective-C)
│   └── build/                        // Output do iOS (IPA, binários Xcode)
│
├── lib/                              // Código Dart principal do app
│   ├── main.dart                     // Ponto de entrada da aplicação
│   └── src/                          // (opcional) código organizado por pastas, ex: screens, widgets, models
│       ├── screens/                  // Telas/pages do app
│       │   └── home_screen.dart
│       ├── widgets/                  // Widgets reutilizáveis
│       │   └── custom_button.dart
│       └── models/                   // Modelos de dados
│           └── user.dart
│
├── build/                            // Output do Flutter em geral
│   ├── linux/                        // Binários Linux (`.out` ou executável)
│   ├── windows/                      // Binários Windows (`.exe`)
│   └── web/                          // Build web (HTML, JS, CSS)
│
├── test/                             // Testes unitários ou widget tests
│   └── widget_test.dart
│
├── pubspec.yaml                      // Configuração do projeto e dependências
├── pubspec.lock                      // Arquivo gerado com versões exatas das dependências
├── README.md                         // Documentação
└── .gitignore                        // Arquivos/pastas ignoradas pelo Git
```

## 🔢 Tipos

* **Numéricos**
  * `int` – inteiro com **tamanho dinâmico**
    * 64 bits em sistemas modernos (Dart 2.0+)
    * Suporta valores: **-9.223.372.036.854.775.808** até **9.223.372.036.854.775.807**
    * Em web (compilado para JavaScript), limites são como `number` JS (-2^53+1 até 2^53-1)
  * `double` – ponto flutuante de **64 bits** (IEEE 754 double)
    * Precisão: \~15-17 dígitos decimais
    * Suporta `NaN`, `Infinity` e `-Infinity`

* **Texto**
  * `String` – sequência de caracteres UTF-16
    * Cada caractere ocupa 2 bytes (ou 4 bytes para caracteres fora do BMP)
    * Tamanho máximo depende da memória disponível

* **Booleano**
  * `bool` – `true` ou `false`
    * Internamente ocupa 1 bit lógico, mas geralmente 1 byte ou mais em memória

* **Valores Especiais**
  * `null` – ausência de valor
    * Desde Dart 2.12, suporta **null safety**
  * Em Flutter/Dart, não existe `undefined` como em JS

* **Coleções e Estruturas**
  * `List<T>` – array indexado dinamicamente
    * Pode ser growable (tamanho variável) ou fixo (`List.filled`)
  * `Map<K,V>` – coleção de pares chave/valor
  * `Set<T>` – conjunto de valores únicos
  * `Queue<T>` – fila/deque
  * `Runes` – representação de códigos Unicode de uma `String`
  * `Symbol` – referência de símbolo (usado principalmente para reflexão)

* **Funções e Objetos**

  * `Function` – bloco executável
  * `Object` – supertipo de todos os objetos
  * `dynamic` – tipo genérico que pode armazenar qualquer coisa
  * `var` – inferência de tipo, mas fixo após atribuição (exceto se for `dynamic`)
  * `final` – valor imutável após inicialização
  * `const` – valor constante em tempo de compilação

* **Binário**
  * `Uint8List` / `Int8List` / `Uint16List` / `Int16List` / `Uint32List` / `Int32List` / `Float32List` / `Float64List` – Arrays tipados, equivalentes ao `TypedArray` do JS
    * `Uint8List` → 1 byte, 0..255
    * `Int8List` → 1 byte, -128..127
    * `Uint16List` → 2 bytes, 0..65535
    * `Int16List` → 2 bytes, -32768..32767
    * `Uint32List` → 4 bytes, 0..4.294.967.295
    * `Int32List` → 4 bytes, -2.147.483.648..2.147.483.647
    * `Float32List` → 4 bytes, precisão simples
    * `Float64List` → 8 bytes, precisão dupla
