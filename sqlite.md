# SQLite

Este guia fornece informações sobre como trabalhar com SQLite, incluindo exemplos comuns de consultas, melhores práticas e dicas para gerenciamento de banco de dados. Seja você um iniciante ou um usuário experiente, este guia ajudará você a aproveitar ao máximo o SQLite.

## Índice

- [Introdução ao SQLite](#introducao-ao-sqlite)  
  Visão geral do SQLite, suas características e como configurá-lo.

- [Conectando-se ao Banco de Dados SQLite](#conectando-se-ao-banco-de-dados-sqlite)  
  Como estabelecer uma conexão com um banco de dados SQLite utilizando diferentes métodos.

- [Consultas SQL Básicas no SQLite](#consultas-sql-basicas-no-sqlite)  
  Consultas SQL comuns no SQLite, incluindo selecionar, inserir, atualizar e excluir dados.

- [Consultas Avançadas e Funções](#consultas-avancadas-e-funcoes)  
  Operações SQL avançadas como junções, subconsultas e triggers no SQLite.

- [Otimização de Performance](#otimizacao-de-performance)  
  Dicas para otimizar a performance do seu banco de dados SQLite.

- [Tratamento de Erros e Depuração](#tratamento-de-erros-e-depuracao)  
  Como tratar erros e depurar consultas SQL no SQLite.

---

## Introdução ao SQLite

SQLite é um motor de banco de dados SQL autônomo, sem servidor e sem configuração. Ao contrário de outros sistemas de gerenciamento de banco de dados (SGBD), o SQLite não requer um processo de servidor separado, e o banco de dados é armazenado como um único arquivo no disco. Isso torna o SQLite ideal para aplicativos embutidos, armazenamento local ou bancos de dados de pequena escala.

### Características principais do SQLite:
- Sem servidor e autônomo.
- Configuração simples, sem necessidade de configuração adicional.
- Suporte multiplataforma e amplamente utilizado.
- Adequado para sistemas embarcados, aplicativos móveis e aplicativos de pequena escala.
- Suporta a maioria dos padrões SQL-92.

---

## Conectando-se ao Banco de Dados SQLite

Para conectar-se a um banco de dados SQLite, você pode usar bibliotecas e ferramentas dependendo da linguagem de programação que está utilizando.

### Exemplo usando **Python** com SQLite3:
```python
import sqlite3

# Conectando ao banco de dados SQLite
connection = sqlite3.connect('exemplo.db')

# Criando um objeto cursor para executar consultas SQL
cursor = connection.cursor()
```

### Exemplo usando **Linha de Comando do SQLite**:
1. Abra o terminal ou prompt de comando.
2. Execute o seguinte comando para abrir a interface de linha de comando do SQLite:
   ```bash
   sqlite3 exemplo.db
   ```
3. Agora você pode executar consultas SQL diretamente na linha de comando.

---

## Consultas SQL Básicas no SQLite

Aqui estão alguns exemplos de consultas SQL comuns que você pode usar no SQLite.

### Selecionando Dados
Para recuperar dados de uma tabela:

```sql
SELECT * FROM funcionarios WHERE departamento = 'TI';
```

### Inserindo Dados
Para inserir um novo registro em uma tabela:

```sql
INSERT INTO funcionarios (id, nome, departamento, salario) 
VALUES (1, 'João Silva', 'RH', 50000);
```

### Atualizando Dados
Para atualizar um registro existente:

```sql
UPDATE funcionarios 
SET salario = 55000 
WHERE id = 1;
```

### Deletando Dados
Para excluir um registro:

```sql
DELETE FROM funcionarios WHERE id = 1;
```

---

## Consultas Avançadas e Funções

### Junções
O SQLite suporta `INNER JOIN`, `LEFT JOIN` e `CROSS JOIN`. Aqui está um exemplo de `INNER JOIN`:

```sql
SELECT f.nome, d.nome 
FROM funcionarios f
INNER JOIN departamentos d ON f.id_departamento = d.id;
```

### Subconsultas
Subconsultas podem ser usadas para recuperar dados que serão usados por outra consulta. Exemplo:

```sql
SELECT nome FROM funcionarios
WHERE salario > (SELECT AVG(salario) FROM funcionarios);
```

### Criando Triggers
Triggers são usadas para executar ações automaticamente quando certos eventos ocorrem, como inserções, atualizações ou exclusões.

```sql
CREATE TRIGGER antes_da_atualizacao
BEFORE UPDATE ON funcionarios
FOR EACH ROW
BEGIN
    INSERT INTO log_audit (acao, id_funcionario) 
    VALUES ('Atualizado', OLD.id);
END;
```

### Criando Views
Você pode criar views no SQLite para simplificar consultas complexas:

```sql
CREATE VIEW resumo_funcionario AS
SELECT id, nome, departamento, salario FROM funcionarios WHERE salario > 40000;
```

---

## Otimização de Performance

SQLite é projetado para ser eficiente na maioria dos casos de uso, mas existem algumas técnicas que você pode usar para melhorar o desempenho:

- **Use Transações**: Agrupar várias consultas dentro de uma única transação pode aumentar significativamente a velocidade das operações.
  
```sql
BEGIN TRANSACTION;
UPDATE funcionarios SET salario = salario + 500 WHERE departamento = 'TI';
INSERT INTO funcionarios (id, nome, departamento, salario) VALUES (2, 'Maria Souza', 'Vendas', 48000);
COMMIT;
```

- **Indexação**: Crie índices em colunas que são frequentemente usadas em cláusulas `WHERE`, `JOIN` ou `ORDER BY`.
  
```sql
CREATE INDEX idx_funcionario_departamento 
ON funcionarios(departamento);
```

- **Use `EXPLAIN`**: O comando `EXPLAIN` pode ajudar a analisar o plano de execução da consulta e melhorar o desempenho.
  
```sql
EXPLAIN QUERY PLAN SELECT * FROM funcionarios WHERE departamento = 'TI';
```

---

## Tratamento de Erros e Depuração

SQLite oferece capacidades básicas de tratamento de erros através da função `sqlite3_errmsg()` ou verificando os códigos de retorno das consultas SQL. Para a maioria das linguagens de programação, o tratamento de erros é feito através de exceções.

### Exemplo em **Python**:

```python
try:
    cursor.execute("SELECT * FROM funcionarios WHERE departamento = 'TI'")
except sqlite3.DatabaseError as e:
    print(f"Erro no banco de dados: {e}")
```

SQLite também suporta o comando `ROLLBACK` para reverter mudanças feitas durante uma transação se ocorrer um erro.

```sql
BEGIN TRANSACTION;
UPDATE funcionarios SET salario = salario + 500 WHERE departamento = 'RH';
-- Se ocorrer um erro, podemos reverter as mudanças
ROLLBACK;
```
