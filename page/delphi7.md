# <img src="icon/delphi7.png" alt="Ícone" width="24"> Delphi 7

> *Última atualização: 2025-08-09*

O Delphi 7, lançado em 2002, foi uma das versões mais populares e icônicas do ambiente de desenvolvimento integrado (IDE) Delphi, que utiliza a linguagem Object Pascal. Por muitos anos, foi a ferramenta padrão para o desenvolvimento de aplicativos Windows.

## 🧩 Assembly

No Delphi, você pode usar assembly inline (asm) com diversos tipos de dados. Nem todos são diretos, mas aqui estão os principais:
Perfeito! Aqui está uma descrição clara para colocar no seu código ou documentação:

```pascal
program ExemploAssembly;

{$APPTYPE CONSOLE}

uses
  SysUtils;

function Soma(a, b: Integer): Integer;
asm
  // No Delphi, os parâmetros a e b vêm da pilha:
  // a -> [EBP+8]
  // b -> [EBP+12]
  // O compilador resolve automaticamente os nomes 'a' e 'b' para os offsets corretos.

  MOV EAX, a  // Coloca 'a' em EAX (registrador de retorno). Por baixo dos panos, pega [EBP+8]
  ADD EAX, b  // Soma 'b' a EAX. Por baixo dos panos, pega [EBP+12]
  // EAX já é o registrador de retorno, então não precisamos fazer mais nada
end;

var
  resultado: Integer;
begin
  resultado := Soma(5, 7);
  Writeln('Resultado: ', resultado); // Deve imprimir 12
  Readln;
end.
```

No Delphi, você pode usar assembly inline (`asm`) com diversos tipos de dados. Nem todos são diretos, mas aqui estão os principais:

* **Inteiro:**
    * Tipos: `Byte`, `ShortInt`, `Word`, `SmallInt`, `Integer`, `Cardinal`, `Int64`, `UInt64`
    * Observação: São os mais simples de manipular; podem ser movidos diretamente para registradores (`AL`, `AX`, `EAX`, `RAX`, etc.).

* **Ponteiro:**
    * Tipos: `Pointer`, `PChar`, `PByte`, arrays e registros alocados por referência
    * Observação: Você pode acessar o valor ou o conteúdo apontado diretamente.

* **Booleano:**
    * Tipos: `Boolean`, `ByteBool`, `WordBool`, `LongBool`
    * Observação: Internamente são inteiros, então funcionam bem em operações com registradores.

* **Ponto Flutuante:**
    * Tipos: `Single`, `Double`, `Extended`
    * Observação: É necessário usar registradores de ponto flutuante (`ST0`, `ST1`) ou SSE (`XMM0`, etc.), não dá para mover direto para `EAX`.

* **Tipos Complexos:**
    * Tipos: `String`, `Variant`, `Record` com métodos, `Dynamic Array`
    * Observação: Podem ser usados via ponteiro ou acessando internamente, mas exigem cuidado, porque têm gerenciamento de memória automático.

## 🗂️ Estrutura

```cpp
Projeto/
│
├── Binaries/                     // Binários gerados (.exe, .dll)
│
├── DataModule/                   // DataModules para banco e lógica central
│   └── udMain.pas                // Classe: TDtmMain, variável: DMMain
│
├── Libraries/                    // Bibliotecas externas
│   └── Indy_10.6.3.11/           // Exemplo de biblioteca externa
│
├── Objects/                      // Arquivos intermediários do compilador (.dcu, .obj)
│
├── Forms/                        // Formulários principais
│   ├── ufSplash.pas              // Classe: TFrmSplash, variável: FrmSplash
│   ├── ufCliente.pas             // Classe: TFrmCliente, variável: FrmCliente
│   ├── ufMain.pas                // Classe: TFrmMain, variável: FrmMain
│   ├── ufPedido.pas              // Classe: TFrmPedido, variável: FrmPedido
│   └── ufProduto.pas             // Classe: TFrmProduto, variável: FrmProduto
│
└── Projeto.dpr                   // Projeto principal Delphi
```

## 🔢 Tipos

* **Inteiro**
    * `Byte` (0..255) – 1 byte, sem sinal
    * `ShortInt` (-128..127) – 1 byte, com sinal
    * `Word` (0..65535) – 2 bytes, sem sinal
    * `SmallInt` (-32768..32767) – 2 bytes, com sinal
    * `LongWord` (0..4.294.967.295) – 4 bytes, sem sinal
    * `Integer` (-2.147.483.648..2.147.483.647) – 4 bytes, com sinal
    * `Int64` (-9.223.372.036.854.775.808..9.223.372.036.854.775.807) – 8 bytes, com sinal
    * `UInt64` (0..18.446.744.073.709.551.615) – 8 bytes, sem sinal

* **Ponto Flutuante**
    * `Single` – 4 bytes, precisão simples
    * `Double` – 8 bytes, precisão dupla
    * `Extended` – 10 ou 12 bytes dependendo da plataforma, precisão estendida

* **Booleano**
    * `Boolean` – 1 byte, `True` ou `False`
    * `ByteBool` – 1 byte, compatível com C
    * `WordBool` – 2 bytes
    * `LongBool` – 4 bytes

* **Caracteres**
    * `Char` – 1 caractere (Unicode no Delphi moderno, 2 bytes)
    * `AnsiChar` – 1 byte
    * `String` – cadeia de caracteres gerenciada
    * `AnsiString` – cadeia de caracteres ANSI gerenciada
    * `WideString` – cadeia de caracteres Unicode gerenciada

* **Ponteiro**
    * `Pointer` – ponteiro genérico
    * `PChar` – ponteiro para caractere
    * `^Tipo` – ponteiro para qualquer tipo
    * `Array` – vetor de elementos de mesmo tipo
    * `Record` – conjunto de campos de tipos diversos
    * `Variant` – tipo dinâmico que pode armazenar vários tipos

* **Enumerador**
    * `enum` – valores simbólicos (ex.: `type TDia = (Segunda, Terca, Quarta, Quinta, Sexta);`)
    * Internamente são inteiros (`Byte`, `Word` ou `Integer`)
