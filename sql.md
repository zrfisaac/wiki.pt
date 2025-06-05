<!-- # [ zrfisaac ] -->

<!-- # [ about ] -->
<!-- # - author : Isaac Caires -->
<!-- # . - email : zrfisaac@gmail.com -->
<!-- # . - site : zrfisaac.github.io -->
<!-- # - version : zrfisaac.wiki.pt.sql : 0.0.2 -->

<!-- # [ markdown ] -->
# SQL

## Descrição
SQL (Structured Query Language) é a linguagem padrão utilizada para interagir com bancos de dados relacionais. Ela permite criar estruturas, manipular dados e controlar o acesso a essas informações. A linguagem é dividida em subconjuntos, cada um com um propósito específico.

Embora esses comandos sigam um padrão internacional (ANSI/ISO), cada sistema de banco de dados (como PostgreSQL, MySQL, Oracle, SQL Server) pode ter extensões e variações. Por isso, ao escrever comandos reutilizáveis, é comum focar nos recursos mais padronizados e evitar dependências específicas de cada sistema.

---

## Índice
- [Ajuda](#ajuda)
  - [DCL](#dcl) – Data Control Language (Linguagem de Controle de Dados)
  - [DDL](#ddl) – Data Definition Language (Linguagem de Definição de Dados)
  - [DML](#dml) – Data Manipulation Language (Linguagem de Manipulação de Dados)
  - [TCL](#tcl) – Transaction Control Language (Linguagem de Controle de Transações)

---

## [Ajuda](#índice)

### [DCL](#índice)
> Data Control Language (Linguagem de Controle de Dados)

Responsável por gerenciar permissões de acesso aos dados.

- `GRANT`: concede permissões.
- `ALTREVOKEER`: remove permissões.

Exemplo:

```sql
GRANT SELECT, INSERT ON produtos TO usuario_app;
```

### [DDL](#índice)
> Data Definition Language (Linguagem de Definição de Dados)

Usada para criar e modificar a estrutura dos objetos do banco, como tabelas, índices e esquemas.

- `CREATE`: cria um novo objeto (tabela, índice, view etc.).
- `ALTER`: altera a estrutura de um objeto existente.
- `DROP`: exclui um objeto.

Exemplo:

```sql
CREATE TABLE produtos (
    id INT PRIMARY KEY,
    nome VARCHAR(100),
    preco DECIMAL(10,2)
);
```

### [DML](#índice)
> Data Manipulation Language (Linguagem de Manipulação de Dados)

Usada para consultar e modificar os dados dentro das tabelas. Os principais comandos são:

- `SELECT`: consulta dados existentes.
- `INSERT`: insere novos registros.
- `UPDATE`: atualiza dados existentes.
- `DELETE`: remove registros.

Exemplo:

```sql
SELECT nome, idade FROM clientes WHERE cidade = 'Salvador';
```

### [TCL](#índice)
> Transaction Control Language (Linguagem de Controle de Transações)

Utilizada para controlar transações, que são conjuntos de operações executadas de forma atômica (tudo ou nada).

- `BEGIN` / `START TRANSACTION`: inicia uma transação.
- `COMMIT`: salva as alterações feitas.
- `ROLLBACK`: desfaz as alterações em caso de erro.

Exemplo:

```sql
BEGIN;
UPDATE contas SET saldo = saldo - 100 WHERE id = 1;
UPDATE contas SET saldo = saldo + 100 WHERE id = 2;
COMMIT;
```
