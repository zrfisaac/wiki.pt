# Firebird

Este guia fornece informações essenciais sobre como interagir com o Firebird SQL, incluindo exemplos de consultas comuns, dicas para otimização de desempenho e melhores práticas para trabalhar com o banco de dados. Seja você iniciante ou desenvolvedor experiente, este guia ajudará você a aproveitar ao máximo seu banco de dados Firebird.

## Índice

- [Introdução ao Firebird SQL](#introducao-ao-firebird-sql)  
  Visão geral sobre o Firebird SQL, suas características e como configurá-lo.

- [Conectando ao Banco de Dados Firebird](#conectando-ao-banco-de-dados-firebird)  
  Como estabelecer uma conexão com um banco de dados Firebird usando diferentes métodos.

- [Consultas SQL Básicas no Firebird](#consultas-sql-basicas-no-firebird)  
  Consultas SQL comuns para Firebird, incluindo seleção, inserção, atualização e exclusão de dados.

- [Consultas Avançadas e Funções](#consultas-avancadas-e-funcoes)  
  Operações SQL avançadas, como joins, subconsultas, gatilhos e procedimentos armazenados.

- [Otimização de Desempenho](#otimizacao-de-desempenho)  
  Dicas e melhores práticas para otimizar o desempenho do seu banco de dados Firebird.

- [Tratamento de Erros e Depuração](#tratamento-de-erros-e-depuracao)  
  Como tratar erros e depurar problemas com consultas SQL no Firebird.

---

## Introdução ao Firebird SQL

O Firebird SQL é um sistema de gerenciamento de banco de dados relacional (RDBMS) poderoso e de código aberto, conhecido por seu alto desempenho, pequeno porte e fácil implantação. Ele suporta SQL padrão, bem como recursos avançados como procedimentos armazenados, gatilhos e funções definidas pelo usuário.

### Características do Firebird SQL:
- Multi-plataforma (Linux, Windows, macOS).
- Conformidade ACID para transações confiáveis.
- Suporte para consultas complexas e indexação.
- Procedimentos armazenados, gatilhos e funções definidas pelo usuário.
- Eficiência no manuseio de ambientes multiusuário.

---

## Conectando ao Banco de Dados Firebird

Para se conectar a um banco de dados Firebird, você precisa usar uma string de conexão que especifique o local do arquivo do banco de dados e outros detalhes de conexão.

### Exemplo usando **FireDAC** no Delphi:
```delphi
FDConnection1.Params.Add('DriverID=FB');
FDConnection1.Params.Add('Database=C:\caminho\para\seu\database.fdb');
FDConnection1.Connected := True;
```

### Exemplo usando **ADO** no C#:
```csharp
using System.Data.OleDb;

string connectionString = "Provider=FirebirdOLEDB;Data Source=localhost;Database=C:\\caminho\\para\\seu\\database.fdb;";
OleDbConnection connection = new OleDbConnection(connectionString);
connection.Open();
```

---

## Consultas SQL Básicas no Firebird

Aqui estão algumas consultas SQL comuns para ajudar você a interagir com seu banco de dados Firebird.

### Selecionando Dados
Para recuperar dados de uma tabela:

```sql
SELECT * FROM empregados WHERE departamento = 'Vendas';
```

### Inserindo Dados
Para adicionar uma nova linha em uma tabela:

```sql
INSERT INTO empregados (id, nome, departamento, salario) 
VALUES (1, 'João Silva', 'Vendas', 50000);
```

### Atualizando Dados
Para atualizar um registro existente:

```sql
UPDATE empregados 
SET salario = 55000 
WHERE id = 1;
```

### Deletando Dados
Para deletar um registro:

```sql
DELETE FROM empregados WHERE id = 1;
```

---

## Consultas Avançadas e Funções

### Joins
O Firebird SQL suporta vários tipos de joins, incluindo `INNER JOIN`, `LEFT JOIN` e `RIGHT JOIN`. Exemplo de um `INNER JOIN`:

```sql
SELECT e.nome, d.nome
FROM empregados e
INNER JOIN departamentos d ON e.departamento_id = d.id;
```

### Subconsultas
Uma subconsulta é uma consulta aninhada dentro de outra consulta. Exemplo:

```sql
SELECT nome FROM empregados 
WHERE salario > (SELECT AVG(salario) FROM empregados);
```

### Criando Gatilhos (Triggers)
Gatilhos são usados para executar automaticamente um conjunto de ações quando certos eventos ocorrem, como inserções ou atualizações.

```sql
CREATE TRIGGER atualizar_salario_empregado
FOR empregados
ACTIVE BEFORE UPDATE
AS
BEGIN
  IF (NEW.salario > OLD.salario) THEN
    INSERT INTO alteracoes_salario (empregado_id, salario_antigo, salario_novo) 
    VALUES (NEW.id, OLD.salario, NEW.salario);
END;
```

### Procedimentos Armazenados
Procedimentos armazenados são úteis para encapsular lógica de negócios e realizar operações mais complexas.

```sql
SET TERM ^ ;
CREATE PROCEDURE aumentar_salario (emp_id INT, incremento FLOAT)
AS
BEGIN
  UPDATE empregados 
  SET salario = salario + incremento 
  WHERE id = emp_id;
END;
^
SET TERM ; ^
```
