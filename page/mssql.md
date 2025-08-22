# <img src="icon/mssql.png" alt="Ícone" width="24"> SQL Server

> *Última atualização: 2025-08-11*

O SQL Server é um sistema de gerenciamento de banco de dados relacional (SGBDR) desenvolvido pela Microsoft. Ele é amplamente utilizado em ambientes corporativos para armazenar, gerenciar e recuperar dados.

- [📦 SQL Server 2022 Developer](https://download.microsoft.com/download/c/c/9/cc9c6797-383c-4b24-8920-dc057c1de9d3/SQL2022-SSEI-Dev.exe)
- [📦 SQL Server Management Studio 21](https://download.visualstudio.microsoft.com/download/pr/f55fba7b-3f02-49b7-9aca-a075049a807d/c2d75555c4674948771dd1bb9433103560dbf7ad7bccb1d822818e7af59494cc/vs_SSMS.exe)

## 📦 Banco

- Desativa recursão em triggers no banco atual.

```sql
EXEC sp_configure 'nested triggers', 0;
RECONFIGURE;
```

- Lista os arquivos internos contidos no backup.

```sql
RESTORE FILELISTONLY
FROM DISK = '/BANCO.bak';
```

- Restaura o banco usando caminhos especificados para MDF e LDF.

```sql
RESTORE DATABASE BANCO
FROM DISK = '/BANCO.bak'
WITH
    MOVE 'BANCO_Data' TO '/var/opt/mssql/data/BANCO.mdf',
    MOVE 'BANCO_Log' TO '/var/opt/mssql/data/BANCO.ldf',
    REPLACE;
```

- Oculta todos os outros bancos do usuário informado.

```sql
USE master;
REVOKE VIEW ANY DATABASE TO zrfisaac;
DENY VIEW ANY DATABASE TO zrfisaac;
```

## 🔢 Tipos

* `TINYINT` – 1 byte, sem sinal → 0..255
* `SMALLINT` – 2 bytes, com sinal → -32.768..32.767
* `INT` – 4 bytes, com sinal → -2.147.483.648..2.147.483.647
* `BIGINT` – 8 bytes, com sinal → -9.223.372.036.854.775.808..9.223.372.036.854.775.807
* `REAL` – 4 bytes, precisão simples (\~7 dígitos significativos)
* `FLOAT[(n)]` – 8 bytes por padrão, precisão dupla (\~15 dígitos significativos)
* `DECIMAL(p,s)` / `NUMERIC(p,s)` – precisão exata, p = total de dígitos (1..38), s = dígitos à direita da vírgula
* `CHAR(n)` – n caracteres fixos, 1 byte por caractere (ANSI)
* `VARCHAR(n)` – até n caracteres variáveis, 1 byte por caractere (ANSI)
* `VARCHAR(MAX)` – até 2^31-1 bytes (\~2 GB)
* `NCHAR(n)` – n caracteres fixos, 2 bytes por caractere (Unicode)
* `NVARCHAR(n)` – até n caracteres variáveis, 2 bytes por caractere (Unicode)
* `NVARCHAR(MAX)` – até 2^31-1 bytes (\~1 GB de caracteres Unicode)
* `TEXT` / `NTEXT` – obsoleto, usado para grandes textos
* `BIT` – 1 bit → 0, 1 ou NULL
* `DATE` – 3 bytes, 0001-01-01 até 9999-12-31
* `TIME[(fsp)]` – 3-5 bytes, horas, minutos, segundos, fração de segundo
* `DATETIME` – 8 bytes → 1753-01-01 até 9999-12-31, precisão \~3.33 ms
* `DATETIME2[(fsp)]` – 6-8 bytes, maior precisão, até 100 ns
* `SMALLDATETIME` – 4 bytes → 1900-01-01 até 2079-06-06, precisão 1 minuto
* `DATETIMEOFFSET` – 8-10 bytes, inclui fuso horário
* `BINARY(n)` – n bytes fixos
* `VARBINARY(n)` – até n bytes variáveis
* `VARBINARY(MAX)` – até 2^31-1 bytes (\~2 GB)
* `IMAGE` – obsoleto, usado para grandes binários
* `UNIQUEIDENTIFIER` – 16 bytes → GUID / UUID
* `SQL_VARIANT` – tipo dinâmico que pode armazenar vários tipos de dados
* `XML` – tipo especial para documentos XML
* `CURSOR` – referência para cursores de banco
* `TABLE` – tipo de tabela temporária ou variável de tabela


## 👤 Usuário

- Desativa senha forte e define nova senha para o login.

```sql
ALTER LOGIN SeuLogin WITH CHECK_POLICY = OFF;
ALTER LOGIN SeuLogin WITH PASSWORD = 'ABcd!@34';
```
