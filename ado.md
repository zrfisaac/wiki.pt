<!-- # [ zrfisaac ] -->

<!-- # [ about ] -->
<!-- # - author : Isaac Caires -->
<!-- # . - email : zrfisaac@gmail.com -->
<!-- # . - site : zrfisaac.github.io -->
<!-- # - version : zrfisaac.wiki.pt.ado : 25.6.14.1 -->

<!-- # [ markdown ] -->
# ADO

## Descrição
ADO (ActiveX Data Objects) é uma tecnologia da Microsoft que fornece uma interface de programação para acesso a dados, especialmente bancos de dados. Ela permite que desenvolvedores conectem-se a fontes de dados, executem comandos SQL e manipulem registros de forma simples e consistente.

---

## Índice
- [Bug](#bug)
  - [Erro de Recordset](#bug--erro-de-recordset)


## [Bug](#índice)

### [Bug](#bug) > [Erro de Recordset](#índice)
> Erro de Recordset em ADO causado por ausência de SET NOCOUNT ON em Stored Procedure

Quando uma **stored procedure no SQL Server não usa `SET NOCOUNT ON`**, o ADO em Delphi pode receber um **recordset vazio** devido às mensagens de "`X row(s) affected`", fazendo com que o **recordset esperado não seja acessado corretamente**. Isso causa erros como `Recordset is not open` ou falhas ao acessar dados.

> Project raised exception class EOleException with message 'Recordset is not open'
