# PowerShell

PowerShell é uma linguagem de script e shell poderosa projetada para administração de sistemas, automação e gerenciamento de configurações. Ela permite que administradores automatizem tarefas, gerenciem configurações de sistema e interajam com várias aplicações e serviços usando scripts.

## Índice

- [Introdução ao PowerShell](#introdução-ao-powershell)
- [Configurando o PowerShell](#configurando-o-powershell)
- [Sintaxe do PowerShell](#sintaxe-do-powershell)
- [Comandos e Cmdlets Comuns](#comandos-e-cmdlets-comuns)
- [Trabalhando com Arquivos e Diretórios](#trabalhando-com-arquivos-e-diretórios)
- [Funções e Variáveis](#funções-e-variáveis)
- [Execução de Scripts e Automação](#execução-de-scripts-e-automação)
- [Recursos](#recursos)

---

## Introdução ao PowerShell

PowerShell é uma linguagem de script e shell desenvolvida pela Microsoft. Originalmente focado na administração de sistemas Windows, o PowerShell evoluiu para uma ferramenta multiplataforma, funcionando em Windows, Linux e macOS. Sua principal característica é o uso de **cmdlets** (comandos especializados) e objetos, permitindo que administradores e desenvolvedores automatizem tarefas complexas de forma fácil.

Principais características:
- **Cmdlets**: Comandos especializados do PowerShell que realizam tarefas específicas.
- **Objetos**: O PowerShell trabalha com objetos, permitindo manipulação avançada e fácil filtragem de dados.
- **Pipeline**: A capacidade de encadear comandos, onde a saída de um comando pode ser passada como entrada para outro.

---

## Configurando o PowerShell

### Instalando o PowerShell

O PowerShell está disponível para Windows, Linux e macOS. A versão moderna, chamada **PowerShell Core**, pode ser instalada em qualquer plataforma suportada.

#### No Windows
1. O PowerShell já está instalado no Windows como parte do sistema operacional.
2. Para instalar o PowerShell Core, você pode baixar o instalador no [site oficial do PowerShell](https://github.com/PowerShell/PowerShell).

#### No Linux / macOS
Para instalar o PowerShell, você pode usar o gerenciador de pacotes da sua distribuição.

Exemplo para Ubuntu:
```bash
sudo apt-get install -y wget apt-transport-https software-properties-common
wget -q "https://packages.microsoft.com/config/ubuntu/20.04/prod.list" -O /etc/apt/sources.list.d/microsoft-prod.list
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
sudo apt-get update
sudo apt-get install -y powershell
```

---

## Sintaxe do PowerShell

A sintaxe do PowerShell é flexível e permite que você execute uma variedade de comandos e scripts. Os comandos no PowerShell são conhecidos como **cmdlets**.

### Cmdlets Básicos
- **Get-Help**: Exibe ajuda sobre cmdlets e comandos.
  ```powershell
  Get-Help Get-Process
  ```

- **Get-Command**: Mostra todos os cmdlets disponíveis.
  ```powershell
  Get-Command
  ```

- **Get-Process**: Exibe os processos em execução no sistema.
  ```powershell
  Get-Process
  ```

- **Set-ExecutionPolicy**: Define a política de execução de scripts.
  ```powershell
  Set-ExecutionPolicy RemoteSigned
  ```

### Variáveis e Tipos de Dados
No PowerShell, você cria variáveis com o prefixo `$`. O PowerShell suporta tipos de dados como strings, inteiros, arrays e objetos.

```powershell
# Definindo variáveis
$nome = "Isaac"
$numero = 42
```

---

## Comandos e Cmdlets Comuns

Aqui estão alguns cmdlets comuns usados no PowerShell para tarefas administrativas e automação.

### Trabalhando com Processos
- **Start-Process**: Inicia um novo processo.
  ```powershell
  Start-Process "notepad.exe"
  ```

- **Stop-Process**: Interrompe um processo em execução.
  ```powershell
  Stop-Process -Name "notepad"
  ```

### Trabalhando com Arquivos
- **Get-Item**: Obtém informações sobre um item (arquivo ou diretório).
  ```powershell
  Get-Item "C:\Caminho\para\arquivo.txt"
  ```

- **Copy-Item**: Copia um item de um local para outro.
  ```powershell
  Copy-Item "C:\origem\arquivo.txt" "C:\destino"
  ```

- **Remove-Item**: Deleta um arquivo ou diretório.
  ```powershell
  Remove-Item "C:\Caminho\para\arquivo.txt"
  ```

---

## Trabalhando com Arquivos e Diretórios

O PowerShell fornece um conjunto de cmdlets para navegar e gerenciar arquivos e diretórios.

- **Get-ChildItem**: Lista os itens de um diretório.
  ```powershell
  Get-ChildItem "C:\Caminho\para\diretório"
  ```

- **New-Item**: Cria um novo arquivo ou diretório.
  ```powershell
  New-Item -Path "C:\Caminho" -Name "novo_arquivo.txt" -ItemType "File"
  ```

- **Set-Location**: Altera o diretório atual.
  ```powershell
  Set-Location "C:\Caminho\para\diretório"
  ```

---

## Funções e Variáveis

### Funções
Funções no PowerShell são blocos de código que podem ser reutilizados. Elas são definidas usando a palavra-chave `function`.

Exemplo de uma função simples:
```powershell
function Say-Hello {
    Write-Host "Hello, World!"
}

# Chamando a função
Say-Hello
```

### Variáveis
As variáveis são precedidas pelo `$`. O PowerShell suporta variáveis globais, locais e de script.

```powershell
$variavelLocal = "Valor local"
$variavelGlobal = "Valor global"
```

---

## Execução de Scripts e Automação

O PowerShell é amplamente usado para automação de tarefas. Você pode criar scripts para realizar tarefas repetitivas como gerenciamento de usuários, backups ou configurações de sistema.

### Executando um Script
Para executar um script no PowerShell, navegue até o diretório onde o script está localizado e execute-o com a extensão `.ps1`.

```powershell
.\script.ps1
```

### Automação com Agendador de Tarefas
O PowerShell pode ser integrado com o Agendador de Tarefas do Windows para executar scripts em intervalos programados.

Exemplo de agendamento com `New-ScheduledTask`:
```powershell
$action = New-ScheduledTaskAction -Execute "powershell.exe" -Argument "C:\Caminho\para\script.ps1"
$trigger = New-ScheduledTaskTrigger -At "9:00AM" -Daily
Register-ScheduledTask -Action $action -Trigger $trigger -TaskName "MeuScriptDiario"
```

---

## Recursos

- [Documentação Oficial do PowerShell](https://docs.microsoft.com/pt-br/powershell/)
- [PowerShell Gallery](https://www.powershellgallery.com/)
- [PowerShell no GitHub](https://github.com/PowerShell/PowerShell)
