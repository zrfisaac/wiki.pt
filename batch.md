# Batch  

Bem-vindo à **Wiki Batch**! Este espaço é dedicado a quem deseja explorar ou dominar o uso de scripts em Batch, uma linguagem simples e poderosa para automação de tarefas em sistemas Windows.  

## Descrição  

Batch é uma linguagem de script utilizada em arquivos `.bat` ou `.cmd` para executar comandos do prompt do Windows. Apesar de sua simplicidade, é amplamente usada para automatizar processos, gerenciar arquivos e realizar tarefas administrativas no sistema operacional.  

Esta wiki fornece uma introdução detalhada ao Batch, dicas úteis, exemplos práticos e recursos para maximizar sua produtividade.  

## Links Úteis  

- [Documentação do Prompt de Comando](https://learn.microsoft.com/pt-br/windows-server/administration/windows-commands/)  
- [Guia de Comandos Batch](https://ss64.com/nt/)  
- [Foros e Comunidades Batch](https://stackoverflow.com/questions/tagged/batch-file)  
- [Batch Scripting - Introdução Básica](https://www.computerhope.com/batch.htm)  

## Índice  

- [Descrição](#descrição)  
- [Links Úteis](#links-úteis)  
- [Versões e Evolução](#versões-e-evolução)  
- [Exemplos de Código Básico](#exemplos-de-código-básico)  

## Versões e Evolução  

Embora o Batch não tenha versões formais, sua funcionalidade evoluiu com os sistemas operacionais Windows:  

- **MS-DOS (Anos 1980)**  
  Introdução dos primeiros comandos Batch para gerenciamento de arquivos e execução de processos básicos.  

- **Windows 95/98/ME**  
  Batch ganhou mais comandos e começou a suportar variáveis de ambiente e estruturas de controle mais avançadas.  

- **Windows XP e Superior**  
  Novos comandos foram adicionados, como `setlocal`, `endlocal` e `for /f`, permitindo maior controle sobre scripts.  

- **Windows 10/11**  
  Apesar de o PowerShell e outros recursos modernos serem mais utilizados, o Batch continua relevante para tarefas rápidas e compatibilidade com sistemas legados.  

## Exemplos de Código Básico  

Aqui estão alguns exemplos práticos para começar a trabalhar com Batch:  

**Exemplo "Olá, Mundo"**  
```batch
@echo off
echo Olá, Mundo!
pause
```

**Criar um Arquivo com Conteúdo**  
```batch
@echo off
echo Este é um exemplo de Batch > exemplo.txt
echo Arquivo criado com sucesso.
pause
```

**Loop e Condicionais**  
```batch
@echo off
set /p nome="Digite seu nome: "
if "%nome%"=="" (
    echo Você não digitou nada!
) else (
    echo Olá, %nome%!
)
pause
```

**Listar Arquivos de uma Pasta**  
```batch
@echo off
echo Listando arquivos na pasta atual:
dir /b
pause
```

**Excluir Arquivos Temporários**  
```batch
@echo off
echo Excluindo arquivos temporários...
del /q /f %temp%\*
echo Operação concluída.
pause
```
