<!-- # [ zrfisaac ] -->

<!-- # [ about ] -->
<!-- # - author : Isaac Caires -->
<!-- # . - email : zrfisaac@gmail.com -->
<!-- # . - site : zrfisaac.github.io -->
<!-- # - version : zrfisaac.wiki.pt.lazarus : 25.6.14.1 -->

<!-- # [ markdown ] -->
# Lazarus

## Descrição
Lazarus é um ambiente de desenvolvimento integrado (IDE) gratuito e de código aberto para a linguagem Object Pascal, baseado no compilador Free Pascal (FPC). Ele é inspirado no antigo Delphi da Borland, oferecendo uma alternativa moderna e multiplataforma para desenvolvimento de software com interfaces gráficas (GUI) e aplicações de linha de comando.

---

## Índice
- Ajuda
  - [Macros](#macros) (Variables)

---

## [Ajuda](#índice)

### [Macros](#índice)

| Variável            | Descrição                                                          | Exemplo de Valor                              |
| ------------------- | ------------------------------------------------------------------ | --------------------------------------------- |
| `$(TargetCPU)`      | Arquitetura da CPU de destino                                      | `i386`, `x86_64`, `arm`, etc.                 |
| `$(TargetOS)`       | Sistema operacional de destino                                     | `win32`, `win64`, `linux`, `darwin`           |
| `$(SrcCPU)`         | Arquitetura da CPU onde o compilador está rodando                  | `x86_64`, `i386`                              |
| `$(SrcOS)`          | Sistema operacional onde o compilador está rodando                 | `linux`, `windows`                            |
| `$(FPCVer)`         | Versão do compilador Free Pascal                                   | `3.2.2`, `3.0.4`                              |
| `$(LazarusDir)`     | Caminho raiz da instalação do Lazarus                              | `C:\lazarus`, `/usr/share/lazarus`            |
| `$(ProjPath)`       | Caminho completo da pasta do projeto                               | `C:\Projetos\MeuApp\`                         |
| `$(PkgOutDir)`      | Pasta de saída dos arquivos compilados de pacotes                  | `lib\$(TargetCPU)-$(TargetOS)`                |
| `$(Name)`           | Nome do projeto ou pacote                                          | `MeuApp`                                      |
| `$(Ext)`            | Extensão de arquivo de acordo com o sistema operacional de destino | `.exe`, `.so`, `.dylib`                       |
| `$(TargetFile)`     | Caminho completo do binário gerado                                 | `project1.exe`                                |
| `$(TargetFileExt)`  | Extensão do arquivo binário                                        | `.exe`, `.so`, etc.                           |
| `$(TargetFileName)` | Nome do arquivo binário                                            | `project1`                                    |
| `$(TargetDir)`      | Diretório onde o binário final será salvo                          | `bin\win64\`                                  |
| `$(CompPath)`       | Caminho do compilador FPC usado                                    | `C:\lazarus\fpc\3.2.2\bin\i386-win32\fpc.exe` |
| `$(FPCSourceDir)`   | Caminho para os fontes do FPC                                      | `C:\lazarus\fpc\3.2.2\source`                 |
| `$(UserHome)`       | Diretório do usuário atual                                         | `C:\Users\Isaac`, `/home/isaac`               |
| `$(AppType)`        | Tipo de aplicação                                                  | `GUI`, `Console`, `Library`                   |
| `$(BuildMode)`      | Modo de compilação selecionado                                     | `Default`, `Debug`, `Release`                 |
