<!-- # [ zrfisaac ] -->

<!-- # [ about ] -->
<!-- # - author : Isaac Caires -->
<!-- # . - email : zrfisaac@gmail.com -->
<!-- # . - site : zrfisaac.github.io -->
<!-- # - version : zrfisaac.wiki.pt.mssql : 25.6.14.1 -->

<!-- # [ markdown ] -->
# SQL Server

## Descrição
SQL Server é um sistema gerenciador de banco de dados relacional (SGBDR) desenvolvido pela Microsoft, projetado para armazenar, recuperar e gerenciar dados. Ele suporta uma ampla gama de aplicações, desde projetos de pequena escala até grandes sistemas empresariais. O SQL Server oferece recursos robustos como consultas avançadas, análises, segurança e integração com ferramentas da Microsoft, tornando-o uma solução poderosa para aplicações orientadas a dados.

---

## Índice
- Ajuda
  - BACKUP
  - DATE
  - DATETIME
  - HASH
  - INFORMATION_SCHEMA
  - STRING
  - TRIGGER
  - VIEW
- Download
  - Driver ODBC para SQL Server:
      [`18-aarch64`](https://go.microsoft.com/fwlink/?linkid=2281322)
      [`18-amd64`](https://go.microsoft.com/fwlink/?linkid=2280794)
      [`18-i386`](https://go.microsoft.com/fwlink/?linkid=2281260)
      [`17-amd64`](https://go.microsoft.com/fwlink/?linkid=2266337)
      [`17-i386`](https://go.microsoft.com/fwlink/?linkid=2266446)
  - OLE DB para SQL Server:
      [`19-aarch64`](https://go.microsoft.com/fwlink/?linkid=2277846)
      [`19-amd64`](https://go.microsoft.com/fwlink/?linkid=2278038)
      [`19-i386`](https://go.microsoft.com/fwlink/?linkid=2278037)
  - SQL Server Developer:
      [`2022`](https://download.microsoft.com/download/c/c/9/cc9c6797-383c-4b24-8920-dc057c1de9d3/SQL2022-SSEI-Dev.exe)
      [`2019`](https://go.microsoft.com/fwlink/?linkid=866662)
  - SQL Server Express
      - [`2008 R2 SP2`](https://www.microsoft.com/pt-br/download/details.aspx?id=30438):
        [`SQLEXPR_x64_PTB.exe`](https://download.microsoft.com/download/6/a/5/6a543f17-0dc1-43e5-a48f-45eafa826d25/SQLEXPR_x64_PTB.exe)
        [`SQLEXPR_x86_PTB.exe`](https://download.microsoft.com/download/6/a/5/6a543f17-0dc1-43e5-a48f-45eafa826d25/SQLEXPR_x86_PTB.exe)
        [`SQLEXPR32_x86_PTB.exe`](https://download.microsoft.com/download/6/a/5/6a543f17-0dc1-43e5-a48f-45eafa826d25/SQLEXPR32_x86_PTB.exe)
        [`SQLEXPRADV_x64_PTB.exe`](https://download.microsoft.com/download/6/a/5/6a543f17-0dc1-43e5-a48f-45eafa826d25/SQLEXPRADV_x64_PTB.exe)
        [`SQLEXPRWT_x86_PTB.exe`](https://download.microsoft.com/download/6/a/5/6a543f17-0dc1-43e5-a48f-45eafa826d25/SQLEXPRWT_x86_PTB.exe)
  - SQL Server Management Studio:
      [`setup`](https://aka.ms/ssmsfullsetup)
- [Exemplo](#exemplo)
  - Coluna
  - Banco de dados
  - Função
  - [Procedimento](#procedimento)
  - [Tabela](#tabela)
  - Usuário
  - Visão
- Padrão
  - Porta: `1433` `5920`
  - Usuário: `sa`
  - Banco de dados: `master`
- Script
  - Coluna

---

## [Exemplo](#índice)

### [Procedimento](#índice)

```sql
IF  EXISTS (
  SELECT TOP 1 NULL
  FROM SYSOBJECTS WITH(NOLOCK)
  WHERE XTYPE = N'P'
  AND NAME = N'PR_DEBUG'
) DROP PROCEDURE PR_DEBUG
GO
CREATE PROCEDURE PR_DEBUG
  @P_DATA VARCHAR(32)
AS
  SELECT @P_DATA AS P_DEBUG
GO
EXEC PR_DEBUG @P_DATA = 'DEBUG'
```

### [Tabela](https://www.google.com/url?sa=E&source=gmail&q=#índice)

```sql
IF NOT EXISTS (
  SELECT TOP 1 NULL
  FROM INFORMATION_SCHEMA.TABLES WITH(NOLOCK)
  WHERE INFORMATION_SCHEMA.TABLES.TABLE_TYPE = N'BASE TABLE'
  AND INFORMATION_SCHEMA.TABLES.TABLE_NAME = N'TB_DEBUG'
)
BEGIN
  CREATE TABLE TB_DEBUG (
     CL_ID         INT  IDENTITY(1, 1) NOT NULL
    ,CL_DEBUG      INT                 NOT NULL
    ,CL_NAME       VARCHAR     ( 400)  NOT NULL
    ,CL_STATUS     VARCHAR     (   1)  NOT NULL
    CONSTRAINT CT_DF_TB_DEBUG_CL_STATUS
    DEFAULT('N')
    -- CONSTRAINT
    ,CONSTRAINT CT_CK_TB_DEBUG_CL_STATUS
    CHECK(CL_STATUS  IN ('Y','N'))
    -- PRIMARY KEY
    ,CONSTRAINT PK_TB_DEBUG_CL_ID
    PRIMARY KEY (CL_ID)
    -- FOREIGN KEY
    ,CONSTRAINT FK_TB_DEBUG_CL_DEBUG
    FOREIGN KEY (CL_DEBUG)
    REFERENCES TB_DEBUG(CL_ID)
  )
END
```

## [Script](#índice)

### [Script](#script) > [Procedimento](#índice)
