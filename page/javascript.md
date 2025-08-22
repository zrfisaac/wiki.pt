# <img src="icon/javascript.png" alt="Ícone" width="24"> JavaScript

> *Última atualização: 2025-08-13*

## 🔢 Tipos

* **Numéricos**
  * `number` – **64 bits** (IEEE 754 double)
    * Inteiros seguros: **-(2^53 - 1)** até **2^53 - 1**
      → `-9.007.199.254.740.991` a `9.007.199.254.740.991`
    * Ponto flutuante: \~15-17 dígitos decimais de precisão
    * Inclui `NaN`, `Infinity` e `-Infinity`
  * `bigint` – tamanho **dinâmico** (inteiro arbitrário)
    * Sem limite prático de magnitude, apenas restrito por memória
    * Não suporta decimais
    * Sintaxe: `123456789012345678901234567890n`

* **Texto**
  * `string` – cada caractere é **UTF-16** (2 bytes por unidade de código)
    * Suporta Unicode completo (alguns caracteres ocupam 4 bytes)
    * Tamanho máximo teórico: \~1 bilhão de caracteres (depende da memória)

* **Booleano**
  * `boolean` – representa `true` ou `false`
    * Internamente pode ser otimizado para **1 bit** em arrays, mas geralmente ocupa **4 bytes** por valor em memória

* **Valores Especiais**
  * `undefined` – valor único (tipo próprio), ocupa espaço mínimo (engine dependente)
  * `null` – valor único (tipo próprio), também de tamanho mínimo

* **Símbolos**
  * `symbol` – identificador único, não tem tamanho numérico definido, armazenado por referência

* **Objetos e Estruturas**
  * `Object` – coleção de propriedades, tamanho depende da quantidade de chaves/valores
  * `Array` – estrutura indexada, cada elemento é um ponteiro para o valor real
  * `Function` – objeto com código executável, tamanho depende da implementação
  * `Date` – internamente armazena um **número de 64 bits** (timestamp em ms desde 1970)
  * `RegExp` – objeto com dados de padrão e flags
  * `Map`/`Set` – estruturas otimizadas para lookup, tamanho cresce conforme o conteúdo

* **Binário**
  * `ArrayBuffer` – bloco fixo de memória binária
  * `TypedArray` – visão tipada do `ArrayBuffer` com tamanhos específicos:
    * `Int8Array` → 1 byte com sinal (-128..127)
    * `Uint8Array` → 1 byte sem sinal (0..255)
    * `Int16Array` → 2 bytes com sinal (-32768..32767)
    * `Uint16Array` → 2 bytes sem sinal (0..65535)
    * `Int32Array` → 4 bytes com sinal (-2.147.483.648..2.147.483.647)
    * `Uint32Array` → 4 bytes sem sinal (0..4.294.967.295)
    * `Float32Array` → 4 bytes (precisão simples IEEE 754)
    * `Float64Array` → 8 bytes (precisão dupla IEEE 754)
  * `DataView` – leitura/escrita flexível de um `ArrayBuffer`
  * `Buffer` *(Node.js)* – igual a `Uint8Array`, mas com métodos extras para manipulação de bytes
