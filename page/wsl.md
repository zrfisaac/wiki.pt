# <img src="icon/wsl.png" alt="Ícone" width="24"> WSL

> *Última atualização: 2025-08-11*

O WSL, sigla para Windows Subsystem for Linux, é uma camada de compatibilidade da Microsoft que permite aos desenvolvedores e usuários rodarem um ambiente Linux diretamente no Windows, sem a necessidade de uma máquina virtual completa ou de um dual-boot.

- [🌐 Instalação para versões mais antigas do WSL](https://learn.microsoft.com/pt-br/windows/wsl/install-manual)

- Habilitar o Subsistema do Windows para Linux

```bash
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```

- Habilitar o recurso máquina virtual

```bash
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

- Baixar o pacote de atualização do kernel do Linux

  - [Pacote de atualização do kernel do Linux WSL2 para computadores x64](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi)

- Lista todas as distribuições Linux disponíveis para instalação no WSL

```bash
wsl --list --online
```

- Instala a distribuição do Ubuntu 22.04 no seu sistema Windows

```bash
wsl --install -d Ubuntu-22.04
```

- Lista todas as distribuições Linux instaladas no WSL

```bash
wsl -l -v
```

- Define a versão do WSL para a distribuição especificada

```bash
wsl --set-version Ubuntu-22.04 2
```

- Define a distribuição do Ubuntu 22.04 como a padrão

```bash
wsl --set-default Ubuntu-22.04
```

- Encerra todas as distribuições e libera os recursos que elas estavam usando

```bash
wsl --shutdown
```

- Lista todas as distribuições Linux instaladas no WSL

```bash
wsl --list
```

- Inicia o terminal da distribuição do Ubuntu 22.04

```bash
wsl -d Ubuntu-22.04
```
