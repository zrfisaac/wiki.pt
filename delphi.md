<!-- # [ zrfisaac ] -->

<!-- # [ about ] -->
<!-- # - author : Isaac Caires -->
<!-- # . - email : zrfisaac@gmail.com -->
<!-- # . - site : zrfisaac.github.io -->
<!-- # - version : zrfisaac.wiki.pt.delphi : 0.0.1 -->

<!-- # [ markdown ] -->

<!-- # - : http://blong.com/Conferences/DCon2001/Debugging/Debugging.htm -->

<!-- # [ markdown ] -->
# Delphi

## Descrição
Delphi é uma linguagem de programação orientada a objetos de alto nível e um ambiente de desenvolvimento integrado (IDE) para desenvolvimento rápido de aplicações (RAD). Desenvolvido originalmente pela Borland e agora mantido pela Embarcadero, Delphi é usado principalmente para criar aplicações para Windows, macOS, iOS, Android e Linux. É baseado em Object Pascal e apresenta uma poderosa estrutura de componentes visuais (VCL e FireMonkey) que permite aos desenvolvedores construir aplicações com uma rica interface gráfica de usuário. Delphi é conhecido por seu forte suporte a banco de dados, desempenho e facilidade de uso, tornando-o popular para aplicações empresariais e de negócios.

---

## Índice
- Ajuda
  - [Format](delphi-ajuda-format)
  - [String](delphi-ajuda-string)
  - [Thread](delphi-ajuda-thread)
- Componentes
  - [Active Query Builder](delphi-component-active-query-builder)
  - [ADO](delphi-component-ado)
  - [BDE](delphi-component-bde)
  - [CEF4Delphi](delphi-component-cef4delphi)
  - [Devart](delphi-component-devart)
  - [DevExpress](delphi-component-devexpress)
  - [EurekaLog](delphi-component-eurekalog)
  - [FastReport](delphi-component-fastreport)
  - [Fortes Report](delphi-component-fortesreport)
  - [Indy](delphi-component-indy)
  - [Rave Reports](delphi-component-rave)
  - [WebView4Delphi](delphi-component-webview4delphi)
- [Depuração](#depuração)
  - [CPU](#cpu)
    - [Registradores da CPU](#registradores-da-cpu)
    - [Flags da CPU](#flags-da-cpu)
    - [Instruções de Assembly da CPU](#instruções-de-assembly-da-cpu)
- Downloads
  - CodeGear :
    [`2007`](https://altd.codegear.com/download/radstudio2007/CodeGearRADStudio2007_Dec2007.iso)
  - Embarcadero :
    [`12.2 Athens`](https://altd.embarcadero.com/download/radstudio/12.0/RADStudio_12_2_i_0329_C2CC.iso)
    [`11.3 Alexandria`](https://altd.embarcadero.com/download/radstudio/11.0/RADStudio_11_3_61_3236a.iso)
    [`10.4.2 Sydney`](https://altd.embarcadero.com/download/radstudio/10.4/RADStudio-1042-4203.iso)
    [`10.3.3 Rio`](https://altd.embarcadero.com/download/radstudio/10.3/delphicbuilder10_3_3_7899_nt.iso)
    [`10.2.3 Tokyo`](https://altd.embarcadero.com/download/radstudio/10.2/delphicbuilder10_2_3_2631.iso)
    [`10.1 Berlin`](https://altd.embarcadero.com/download/radstudio/10.1/delphicbuilder10_1_upd1.iso)
    [`10 Seattle`](https://altd.embarcadero.com/download/radstudio/10/delphicbuilder10___upd1.iso)
    [`XE8`](http://altd.embarcadero.com/download/radstudio/xe8/delphicbuilder_xe8_upd1_subscription.iso)
    [`XE7`](https://altd.embarcadero.com/download/radstudio/xe7/delphicbuilder_xe7_upd1_win.iso)
    [`XE6`](https://altd.embarcadero.com/download/radstudio/xe6/delphicbuilder_xe6_upd1_win.iso)
    [`XE5`](https://altd.embarcadero.com/download/radstudio/xe5/delphicbuilder_xe5_upd2_win.iso)
    [`XE4`](https://altd.embarcadero.com/download/radstudio/xe4/delphicbuilder_xe4_upd1_win.iso)
    [`XE2`](https://altd.embarcadero.com/download/radstudio/xe2/delphicbuilder_xe2_4429_win_dl.iso)
    [`XE`](https://altd.embarcadero.com/download/RADStudioXE/delphicbuilder_xe_3953B_win.iso)
    [`2010`](https://altd.embarcadero.com/download/RADStudio2010/delphicbuilder_2010_3615_win.iso)
    [`2009`](https://altd.embarcadero.com/download/Delphi_C++Builder2009/Delphi_C++Builder2009_ISO_June2009.iso)
    [`7`](https://altd.embarcadero.com/download/delphi/d7/english/ent/delphi_7_ent_en.iso)
  - WinWorld :
    [`7`](https://winworldpc.com/product/delphi/70)
    [`6`](https://winworldpc.com/product/delphi/60)
    [`4`](https://winworldpc.com/product/delphi/4x)
    [`3`](https://winworldpc.com/product/delphi/3x)
    [`2`](https://winworldpc.com/product/delphi/2x)
    [`1`](https://winworldpc.com/product/delphi/1x)
- [Versão](#versão)

---

## [Depuração](#índice)

### [CPU](#índice)

#### [Registradores da CPU](#índice)

| Registrador | Nome do registrador | Tamanho | Comentários |
|---|---|---|---|
| EAX | Acumulador estendido | 32 bits | Registrador de propósito geral |
| EBX | Base estendida | 32 bits | Registrador de propósito geral |
| ECX | Contador estendido | 32 bits | Registrador de propósito geral |
| EDX | Dados estendidos | 32 bits | Registrador de propósito geral |
| ESI | Indicador de origem estendido | 32 bits | Registrador de propósito geral |
| EDI | Indicador de destino estendido | 32 bits | Registrador de propósito geral |
| EBP | Ponteiro de base estendido | 32 bits | Registrador de propósito geral |
| ESP | Ponteiro de pilha estendido | 32 bits | Registrador de propósito geral |
| EIP | Ponteiro de instrução estendido | 32 bits | Registrador de status/controle |
| EFL | Flags estendidos | 32 bits | Registrador de status/controle |
| CS | Segmento de código | 16 bits | Para conter um seletor de segmento |
| DS | Segmento de dados | 16 bits | Para conter um seletor de segmento |
| SS | Segmento de pilha | 16 bits | Para conter um seletor de segmento |
| ES | Segmento extra | 16 bits | Para conter um seletor de segmento |
| FS | Outro segmento extra | 16 bits | Para conter um seletor de segmento |
| GS | Outro segmento extra | 16 bits | Para conter um seletor de segmento |
| AX | Acumulador | 16 bits | Palavra baixa de EAX |
| AH | Acumulador alto | 8 bits | Byte alto de AX |
| AL | Acumulador baixo | 8 bits | Byte baixo de AX |
| BX | Base | 16 bits | Palavra baixa de EBX |
| BH | Base alto | 8 bits | Byte alto de BX |
| BL | Base baixo | 8 bits | Byte baixo de BX |
| CX | Contador | 16 bits | Palavra baixa de ECX |
| CH | Contador alto | 8 bits | Byte alto de CX |
| CL | Contador baixo | 8 bits | Byte baixo de CX |
| DX | Dados | 16 bits | Palavra baixa de EDX |
| DH | Dados altos | 8 bits | Byte alto de DX |
| DL | Dados baixos | 8 bits | Byte baixo de DX |
#### [Flags da CPU](#índice)

| Valor | Bit(s) do registrador EFL | Nome do flag/bit | Tipo de flag |
|---|---|---|---|
| CF | 0 | Flag de transporte (Carry flag) | Status |
| PF | 2 | Flag de paridade (Parity flag) | Status |
| AF | 4 | Flag de ajuste (Adjust flag) | Status |
| ZF | 6 | Flag de zero (Zero flag) | Status |
| SF | 7 | Flag de sinal (Sign flag) | Status |
| TF | 8 | Flag de armadilha (Trap flag) | Sistema |
| IF | 9 | Flag de interrupção (Interrupt flag) | Sistema |
| DF | 10 | Flag de direção (Direction flag) | Controle |
| OF | 11 | Flag de estouro (Overflow flag) | Status |
| IO | 12 e 13 | Campo de nível de privilégio de E/S (I/O privilege level field) | Sistema |
| NF | 14 | Flag de tarefa aninhada (Nested task flag) | Sistema |
| RF | 16 | Flag de retomada (Resume flag) | Sistema |
| VM | 17 | Flag de modo virtual 8086 (Virtual 8086 mode flag) | Sistema |
| AC | 18 | Flag de verificação de alinhamento (Alignment check flag) | Sistema |
| VF | 19 | Flag de interrupção virtual (Virtual interrupt flag) | Sistema |
| VP | 20 | Flag de interrupção virtual pendente (Virtual interrupt pending flag) | Sistema |
| ID | 21 | Flag de identificação (Identification flag) | Sistema |

#### [Instruções de Assembly da CPU](#índice)

| Instrução Assembly | Significado |
|---|---|
| `mov eax, 1` | Define EAX para 1 |
| `xor eax, eax` | O mesmo que `mov eax, 0`, mas mais eficiente |
| `mov eax, esi` | Copia o valor de ESI para EAX |
| `mov edx, [eax]` | Move a palavra dupla (DWord) apontada por EAX para EDX |
| `mov dl, $01` | Define o byte baixo de EDX para 1, deixando os outros bytes inalterados |
| `push eax` | Empurra EAX para a pilha, para que EAX possa ser reutilizado |
| `pop eax` | Retira o valor da pilha e armazena em EAX |
| `ret` | Retorna da rotina (o endereço de retorno está na pilha) |
| `call $410123` | Empurra o endereço da próxima instrução para a pilha e pula para o endereço $410123 |
| `mov ebx, [ebp-$5]` | Move a palavra dupla (DWord) começando no endereço 5 menor que o armazenado em EBP para EBX |
| `cmp dword ptr [ebx+$3C], $00` | Compara a palavra dupla (DWord) no endereço $3C bytes após o endereço armazenado em EBX com zero |
| `jz SomeRoutine+$A0` | Se a última operação de comparação sugerir que os dois valores são iguais, pula para $A0 bytes após o primeiro byte da rotina SomeRoutine. As operações de comparação são implementadas como subtrações. JZ é uma contração de **J**ump if **Z**ero. |
| `movsb` | Copia o byte apontado por ESI para o endereço apontado por EDI, então incrementa ESI e EDI em 1 (a menos que o flag de direção esteja definido, onde eles são decrementados) |
| `movsw` | Copia a palavra apontada por ESI para o endereço apontado por EDI, então incrementa ESI e EDI em 2 (a menos que o flag de direção esteja definido, onde eles são decrementados) |
| `add esp, -$08` | Subtrai 8 do ponteiro de pilha |

## [Versão](#índice)

| **Produto** | **Versão do produto** | **Outros nomes** | **Versão interna** | **Versão do pacote** | **Constante CompilerVersion** | **Constante RTLVersion** | **Símbolo definido** |
|---|---|---|---|---|---|---|---|
| **Delphi 12 Athens** | 29 | BDS 23 | 36 | 290 | 36.0 | 36.0 | VER360 |
| **Delphi 11 Alexandria** | 28 | BDS 22 | 35 | 280 | 35.0 | 35.0 | VER350 |
| **Delphi 10.4 Sydney** | 27 | BDS 21 | 34 | 270 | 34.0 | 34.0 | VER340 |
| **Delphi 10.3 Rio** | 26 | BDS 20 | 33 | 260 | 33.0 | 33.0 | VER330 |
| **Delphi 10.2 Tokyo** | 25 | BDS 19 | 32 | 250 | 32.0 | 32.0 | VER320 |
| **Delphi 10.1 Berlin** | 24 | BDS 18 | 31 | 240 | 31.0 | 31.0 | VER310 |
| **Delphi 10 Seattle** | 23 | BDS 17 | 30 | 230 | 30.0 | 30.0 | VER300 |
| **Delphi XE8** | 22 | BDS 16 | 29 | 220 | 29.0 | 29.0 | VER290 |
| **Delphi XE7** | 21 | BDS 15 | 28 | 210 | 28.0 | 28.0 | VER280 |
| **Delphi XE6** | 20 | BDS 14 | 27 | 200 | 27.0 | 27.0 | VER270 |
| **Delphi XE5** | 19 | BDS 12 | 26 | 190 | 26.0 | 26.0 | VER260 |
| **Delphi XE4** | 18 | BDS 11 | 25 | 180 | 25.0 | 25.0 | VER250 |
| **Delphi XE3** | 17 | BDS 10 | 24 | 170 | 24.0 | 24.0 | VER240 |
| **Delphi XE2** | 16 | BDS 9 | 23 | 160 & 161† | 23.0 | 23.0 | VER230 |
| **Delphi XE** | 15 | BDS 8 | 22 | 150 | 22.0 | 22.0 | VER220 |
| **Delphi 2010** | 14 | BDS 7 | 21 | 140 | 21.0 | 21.0 | VER210 |
| **Delphi 2009** | 12 | BDS 6 | 20 | 120 | 20.0 | 20.0 | VER200 |
| **Delphi 2007 .NET** | 11 | BDS 5 | 19 | 110 | 19.0 | 19.0 | VER190 |
| **Delphi 2007 Win32** | 11 | BDS 5 | 18.5 | 110 | 18.5 | 18.0 | VER180 & VER185 |
| **Delphi 2006** | 10 | BDS 4 | 18 | 100 | 18.0 | 18.0 | VER180 |
| **Delphi 2005** | 9 | BDS 3 | 17 | 90 | 17.0 | 17.0 | VER170 |
| **Delphi 8 (.NET only)** | 8 | BDS 2 | 16 | 80 | 16.0 | 16.0 | VER160 |
| **C++ Builder 7** | 7? |  | 15 | 70? | 15.0? | ? | VER150 & BCB |
| **Delphi 7** | 7 |  | 15 | 70 | 15.0 | 15.0 | VER150 |
| **C++ Builder 6** | 6 |  | 14 | 60 | 14.0 | ? | VER140 & BCB |
| **Delphi 6** | 6 |  | 14 | 60 | 14.0 | 14.0 | VER140 |
| **C++ Builder 5** | 5 |  | 13 | 50 | 13.0 | ? | VER130 & BCB |
| **Delphi 5** | 5 |  | 13 | 50 | 13.0 | 13.0 | VER130 |
| **C++ Builder 4** | 4 |  | 12 | 40 | 12.0 | ? | VER120 & BCB |
| **Delphi 4** | 4 |  | 12 | 40 | 12.0 | 12.0 | VER120 |
| **C++ Builder 3** | 3 |  | 11 | 30 | 11.0 | ? | VER110 & BCB |
| **Delphi 3** | 3 |  | 11 | 30 | 11.0 | 11.0 | VER110 |
| **C++ Builder 1** | 1 |  | 10.5 | 10 | 10.0 | ? | VER100 & BCB |
| **Delphi 2** | 2 |  | 10 | 20 | 10.0 | 10.0 | VER100 |
| **Delphi 1** | 1 |  | 8 | 10 | 8.0 | 8.0 | VER80 |
