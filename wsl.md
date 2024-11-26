# WSL

O Windows Subsystem for Linux (WSL) permite executar distribuições Linux diretamente no Windows.

---

## Índice

[Introdução](#introdução)  
[Comandos](#comandos)  
 - [Instalar uma Distribuição](#instalar-uma-distribuição)  
 - [Listar Distribuições Instaladas](#listar-distribuições-instaladas)  
 - [Encerrar Todas as Instâncias](#encerrar-todas-as-instâncias)  
 - [Remover uma Distribuição](#remover-uma-distribuição)  
[Dicas Adicionais](#dicas-adicionais)  

---

## Comandos

### Instalar uma Distribuição

Para instalar uma distribuição Linux no WSL, use:

```bash
wsl --install -d <nome_da_distribuição>
```

**Exemplo**:  
Para instalar o Ubuntu, execute:  
```bash
wsl --install -d Ubuntu
```

---

### Listar Distribuições Instaladas

Para ver todas as distribuições do WSL instaladas no sistema, use:  

```bash
wsl --list --verbose
```

**Exemplo de Saída**:
```
  NAME        STATE           VERSION
* Ubuntu      Running         2
  Debian      Stopped         2
  kali-linux  Stopped         2
```

---

### Encerrar Todas as Instâncias

Para encerrar todas as instâncias ativas do WSL, use:

```bash
wsl --shutdown
```

Este comando interrompe todas as distribuições em execução e libera a memória utilizada.

---

### Remover uma Distribuição

Para remover uma distribuição instalada no WSL, use:

```bash
wsl --unregister <nome_da_distribuição>
```

**Exemplo**:  
Para remover a distribuição Ubuntu:  
```bash
wsl --unregister Ubuntu
```

---

## Dicas Adicionais

- Para verificar a versão do WSL instalada, execute:
  ```bash
  wsl --version
  ```

- Para atualizar uma distribuição para o WSL 2:
  ```bash
  wsl --set-version <nome_da_distribuição> 2
  ```

- Para definir o WSL 2 como padrão para instalações futuras:
  ```bash
  wsl --set-default-version 2
  ```
