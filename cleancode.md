# Clean Code

Este guia apresenta o conceito de Clean Code (Código Limpo) e fornece melhores práticas, exemplos e dicas para escrever código mantível, legível e eficiente. Clean Code é essencial para melhorar a qualidade do código, a legibilidade e reduzir a dívida técnica, garantindo que sua base de código se mantenha compreensível e sustentável à medida que cresce.

## Índice

- [O que é Clean Code?](#o-que-é-clean-code)
- [Princípios do Clean Code](#princípios-do-clean-code)
- [Melhores Práticas para Escrever Clean Code](#melhores-práticas-para-escrever-clean-code)
- [Cheiros de Código a Evitar](#cheiros-de-código-a-evitar)
- [Refatoração para Clean Code](#refatoração-para-clean-code)
- [Ferramentas e Recursos](#ferramentas-e-recursos)

---

## O que é Clean Code?

Clean Code se refere a um código que é fácil de entender, simples de manter e livre de complexidade desnecessária. Ele segue melhores práticas que garantem que o código seja legível, reutilizável e eficiente. O objetivo principal do Clean Code é escrever código que seja fácil de trabalhar, não apenas para você, mas para qualquer desenvolvedor que possa trabalhar nele no futuro.

As principais características do Clean Code incluem:

- **Legibilidade**: O código deve ser fácil de ler e entender.
- **Simplicidade**: Evite complexidade desnecessária. Mantenha o código o mais simples possível.
- **Manutenibilidade**: O código deve ser fácil de modificar ou expandir no futuro.
- **Testabilidade**: O código deve ser estruturado de forma que facilite os testes.

---

## Princípios do Clean Code

Aqui estão alguns princípios fundamentais do Clean Code que todo desenvolvedor deve seguir:

### 1. **Nomes Significativos**
   - Use nomes descritivos e autoexplicativos para variáveis, funções, classes e métodos.
   - Evite nomes ambíguos ou abreviações excessivas.
   
   **Exemplo:**
   ```python
   # Exemplo ruim
   x = 10  # O que x representa?

   # Exemplo bom
   temperaturaMaxima = 10  # Fica claro o que a variável representa
   ```

### 2. **Funções Pequenas**
   - Funções devem ser pequenas, focadas em uma única tarefa e realizar apenas um trabalho.
   - Uma função deve ter uma razão para mudar.

   **Exemplo:**
   ```python
   # Exemplo ruim
   def processarDadosUsuario():
       carregarDadosUsuario()
       validarDadosUsuario()
       transformarDadosUsuario()
       salvarDadosUsuario()

   # Exemplo bom
   def carregarDadosUsuario():
       # Código para carregar os dados do usuário

   def validarDadosUsuario():
       # Código para validar os dados do usuário

   def transformarDadosUsuario():
       # Código para transformar os dados do usuário

   def salvarDadosUsuario():
       # Código para salvar os dados do usuário
   ```

### 3. **Evitar Duplicação**
   - A duplicação é um sinal de código ruim. Se você se pegar repetindo a mesma lógica, considere refatorá-la em uma função ou método separado.

   **Exemplo:**
   ```python
   # Exemplo ruim
   def obterDetalhesUsuario(usuario):
       # Código para obter os detalhes do usuário
       
   def obterDetalhesAdmin(admin):
       # Código para obter os detalhes do admin

   # Exemplo bom
   def obterDetalhes(pessoa):
       # Código para obter os detalhes de qualquer pessoa (usuário ou admin)
   ```

### 4. **Mantenha Simples (Princípio KISS)**
   - Evite complexidade desnecessária. O código deve ser o mais simples possível enquanto atinge seu objetivo.
   
   **Exemplo:**
   ```python
   # Exemplo ruim
   if (a > b and a > c and a > d and a > e):
       return a

   # Exemplo bom
   maior = max(a, b, c, d, e)
   return maior
   ```

### 5. **Evitar Classes Grandes**
   - Classes grandes são difíceis de manter e entender. Divida classes grandes em classes menores e mais gerenciáveis.
   
   **Exemplo:**
   ```python
   # Exemplo ruim
   class GerenciadorUsuario:
       def adicionar_usuario(self):
           # Código para adicionar o usuário
       def remover_usuario(self):
           # Código para remover o usuário
       def validar_usuario(self):
           # Código para validar o usuário
       def salvar_usuario(self):
           # Código para salvar o usuário

   # Exemplo bom
   class AdicionadorUsuario:
       def adicionar_usuario(self):
           # Código para adicionar o usuário

   class RemoverUsuario:
       def remover_usuario(self):
           # Código para remover o usuário

   class ValidarUsuario:
       def validar_usuario(self):
           # Código para validar o usuário
   ```

### 6. **Tratar Erros de Forma Elegante**
   - Sempre trate erros de forma elegante e forneça mensagens de erro significativas.
   - Não use blocos de captura vazios e evite "engolir" exceções.

   **Exemplo:**
   ```python
   # Exemplo ruim
   try:
       # Algum código
   except Exception as e:
       pass  # Captura silenciosa da exceção

   # Exemplo bom
   try:
       # Algum código
   except ValueError as e:
       print(f"Ocorreu um erro: {e}")
   ```

### 7. **Escreva Testes**
   - Sempre escreva testes para o seu código, garantindo a correção e manutenibilidade. Use testes unitários, testes de integração e testes de ponta a ponta quando necessário.

   **Exemplo:**
   ```python
   # Exemplo bom: Um simples teste unitário usando o framework unittest
   import unittest

   class TesteGerenciadorUsuario(unittest.TestCase):
       def test_adicionar_usuario(self):
           gerenciador = GerenciadorUsuario()
           usuario = gerenciador.adicionar_usuario("João Silva")
           self.assertEqual(usuario.nome, "João Silva")

   if __name__ == "__main__":
       unittest.main()
   ```

---

## Melhores Práticas para Escrever Clean Code

- **Limite o Número de Parâmetros**: Funções não devem ter muitos parâmetros. Se uma função recebe mais de três parâmetros, considere refatorar o código.
  
  **Exemplo:**
  ```python
  # Exemplo ruim
  def criarUsuario(nome, idade, email, endereco, telefone):
      # Código para criar o usuário

  # Exemplo bom
  def criarUsuario(usuario):
      # Código para criar o usuário
  ```

- **Comente de Forma Inteligente**: Escreva comentários para explicar *por que* algo está sendo feito, e não *o que* está sendo feito. O código em si deve tornar claro o *o que*.

  **Exemplo:**
  ```python
  # Exemplo ruim
  x = x + 1  # Incrementa o valor de x

  # Exemplo bom
  # Incrementando x para lidar com o caso em que x é zero
  x = x + 1
  ```

- **Use Constantes**: Use constantes nomeadas em vez de valores hardcoded, especialmente quando o valor é utilizado em múltiplos lugares.

  **Exemplo:**
  ```python
  # Exemplo ruim
  totalPreco = 100 * 0.15  # Taxa de imposto de 15%

  # Exemplo bom
  TAXA_IMPOSTO = 0.15
  totalPreco = 100 * TAXA_IMPOSTO
  ```

---

## Cheiros de Código a Evitar

Aqui estão alguns cheiros de código comuns a serem observados e refatorados:

### 1. **Método Longo**
   - Métodos que fazem demais devem ser divididos em métodos menores e mais focados.

### 2. **Código Duplicado**
   - Se o mesmo código aparece em vários lugares, é hora de refatorar.

### 3. **Classe Grande**
   - Uma classe que lida com muitas responsabilidades deve ser dividida em classes menores e mais focadas.

### 4. **Excesso de Switch Statements**
   - O uso excessivo de switch statements pode indicar que o polimorfismo ou outro padrão de design pode ser mais apropriado.

### 5. **Excesso de Comentários**
   - Comentários não devem ser usados para explicar código ruim. O objetivo é escrever código limpo e autoexplicativo.

---

## Refatoração para Clean Code

Refatoração é o processo de melhorar a estrutura do código existente sem alterar seu comportamento. Aqui estão algumas técnicas comuns de refatoração:

- **Extrair Método**: Se um método está fazendo demais, divida-o em vários métodos menores.
- **Renomear Método ou Variável**: Renomeie um método ou variável para refletir melhor seu propósito.
- **Substituir Números Mágicos**: Substitua números hardcoded por constantes nomeadas para melhorar a legibilidade.
- **Consolidar Código Duplicado**: Combine código duplicado em um único método ou classe reutilizável.

---

## Ferramentas e Recursos

### Ferramentas:
- **Linters**: Use linters para impor diretrizes de estilo e detectar problemas potenciais.
