# NSIS

NSIS (Nullsoft Scriptable Install System) é uma ferramenta de software de código aberto para a criação de instaladores para Windows. Foi originalmente desenvolvido pela Nullsoft, os criadores do Winamp, e agora é mantido por uma comunidade ativa de colaboradores. O NSIS é leve, mas poderoso, oferecendo um alto nível de personalização para a criação de pacotes de instalação profissionais.

## Índice

---

## **Variáveis Internas do NSIS**

### **Caminhos e Diretórios**
- `$INSTDIR` – O diretório onde o aplicativo será instalado.
- `$OUTDIR` – O diretório de saída atual (usado para operações de arquivos).
- `$TEMP` – O diretório temporário do sistema.
- `$WINDIR` – O diretório do Windows (ex.: `C:\Windows`).
- `$SYSDIR` – O diretório do sistema (ex.: `C:\Windows\System32`).
- `$DESKTOP` – O diretório da Área de Trabalho do usuário.
- `$STARTMENU` – O diretório do Menu Iniciar do usuário.
- `$PROGRAMFILES` – O diretório de Arquivos de Programas.
- `$COMMONFILES` – O diretório de Arquivos Comuns.
- `$APPDATA` – O diretório de Dados de Aplicativos.
- `$LOCALAPPDATA` – O diretório de Dados de Aplicativos Locais.
- `$MUSIC`, `$PICTURES`, `$VIDEOS` – Diretórios para músicas, imagens e vídeos.
- `$DOCUMENTS` – A pasta de Documentos do usuário atual.

### **Específicas do Instalador**
- `$EXEDIR` – O diretório onde o executável do instalador está localizado.
- `$EXEFILE` – O caminho completo do executável do instalador.
- `$PLUGINSDIR` – O diretório temporário onde os plugins são extraídos durante a execução.

### **Informações do Usuário**
- `$USERNAME` – O nome do usuário que está executando o instalador.
- `$LANGUAGE` – O idioma usado pelo instalador.
- `$CMDLINE` – Os argumentos da linha de comando passados para o instalador.

### **Variáveis de Registro**
- `$HWNDPARENT` – O identificador da janela pai do instalador.

### Arquitetura do Sistema
- `${RunningX64}` – Uma constante que indica se o sistema operacional é de 64 bits. Seu valor será `1` se o instalador estiver sendo executado em um sistema operacional de 64 bits, ou `0` caso contrário.
