# PHP

PHP é uma linguagem de script popular e de uso geral, especialmente adequada para o desenvolvimento web. É amplamente usada para construir sites e aplicativos dinâmicos, oferecendo recursos poderosos para trabalhar com bancos de dados, manipular requisições HTTP e gerar conteúdo HTML.

---

## Índice

- [Pré-requisitos](#pré-requisitos)  
  Configuração para usar PHP localmente ou em um servidor.

- [Conceitos Básicos do PHP](#conceitos-básicos-do-php)  
  Visão geral dos conceitos fundamentais do PHP, incluindo variáveis, funções, loops e arrays.

- [Exemplo de PHP](#exemplo-de-php)  
  Um exemplo simples para demonstrar recursos comuns do PHP, como conexão com banco de dados, processamento de formulários e exibição de conteúdo dinâmico.

- [Conceitos Avançados de PHP](#conceitos-avançados-de-php)  
  Tópicos mais complexos, como programação orientada a objetos, tratamento de erros e integração com APIs externas.

---

## Pré-requisitos

Antes de começar a trabalhar com PHP, garanta que você tenha o seguinte instalado:

1. **PHP**:  
   Você precisa ter o PHP instalado na sua máquina local ou servidor. Você pode baixar o PHP no site oficial [aqui](https://www.php.net/downloads). Também é possível instalá-lo usando um gerenciador de pacotes para seu sistema, como:

   - **No Ubuntu**:
     ```bash
     sudo apt update
     sudo apt install php php-cli php-mbstring php-xml php-curl
     ```

   - **No Windows**:  
     Você pode usar o XAMPP, WAMP ou instalar o PHP manualmente.

2. **Servidor Web (Opcional para testes)**:  
   Para servir arquivos PHP via HTTP, você pode usar um servidor web como Apache ou Nginx. Alternativamente, você pode usar o servidor embutido do PHP para testes:
   ```bash
   php -S localhost:8000
   ```

3. **Banco de Dados (Opcional para exemplos relacionados a banco de dados)**:  
   Para interagir com um banco de dados no PHP, você pode instalar o MySQL ou PostgreSQL. Para instalar o MySQL, por exemplo:
   ```bash
   sudo apt install mysql-server
   ```

---

## Conceitos Básicos do PHP

### Variáveis e Tipos de Dados

As variáveis em PHP começam com o símbolo de cifrão (`$`) e não requerem a declaração explícita de seu tipo de dado. Os tipos de dados mais comuns incluem inteiros, flutuantes, strings e booleanos.

```php
<?php
$nome = "João";  // string
$idade = 25;     // inteiro
$estudante = true;  // booleano
$altura = 1.75;  // flutuante

echo "Meu nome é $nome, eu tenho $idade anos.";
?>
```

### Funções

Funções em PHP são declaradas usando a palavra-chave `function` e podem receber parâmetros. Veja um exemplo simples:

```php
<?php
function saudacao($nome) {
    return "Olá, $nome!";
}

echo saudacao("Alice"); // Saída: Olá, Alice!
?>
```

### Arrays

Arrays podem armazenar múltiplos valores em uma única variável. O PHP suporta tanto arrays indexados quanto associativos.

```php
<?php
// Array indexado
$cores = ["vermelho", "verde", "azul"];
echo $cores[1]; // Saída: verde

// Array associativo
$pessoa = ["nome" => "João", "idade" => 25];
echo $pessoa["nome"]; // Saída: João
?>
```

### Loops

O PHP suporta vários tipos de loops como `for`, `while` e `foreach`.

```php
<?php
// Loop for
for ($i = 0; $i < 5; $i++) {
    echo "Número $i <br>";
}

// Loop foreach para array associativo
$pessoa = ["nome" => "João", "idade" => 25];
foreach ($pessoa as $chave => $valor) {
    echo "$chave: $valor <br>";
}
?>
```

---

## Exemplo de PHP

Aqui está um exemplo simples demonstrando como usar PHP para manipulação de formulários e exibição de conteúdo dinâmico. Este script aceitará entradas de usuário através de um formulário, processará as informações e exibirá uma mensagem.

### Formulário HTML (index.html)

```html
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <title>Exemplo de Formulário PHP</title>
</head>
<body>
    <form action="processar.php" method="post">
        <label for="nome">Nome:</label><br>
        <input type="text" id="nome" name="nome" required><br><br>
        
        <label for="idade">Idade:</label><br>
        <input type="number" id="idade" name="idade" required><br><br>
        
        <input type="submit" value="Enviar">
    </form>
</body>
</html>
```

### Script PHP (processar.php)

```php
<?php
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    $nome = htmlspecialchars($_POST['nome']);
    $idade = (int)$_POST['idade'];

    echo "<h1>Olá, $nome!</h1>";
    echo "<p>Você tem $idade anos.</p>";
} else {
    echo "<p>Requisição inválida.</p>";
}
?>
```

Neste exemplo, o formulário em `index.html` envia dados para `processar.php`, que processa a entrada e exibe uma mensagem com o nome e idade fornecidos.

---

## Conceitos Avançados de PHP

### Programação Orientada a Objetos (OOP)

O PHP suporta programação orientada a objetos, permitindo que você defina classes e crie objetos.

```php
<?php
class Carro {
    public $marca;
    public $modelo;
    public $ano;

    function __construct($marca, $modelo, $ano) {
        $this->marca = $marca;
        $this->modelo = $modelo;
        $this->ano = $ano;
    }

    function exibirInfo() {
        echo "Carro: $this->ano $this->marca $this->modelo <br>";
    }
}

$meuCarro = new Carro("Toyota", "Corolla", 2020);
$meuCarro->exibirInfo(); // Saída: Carro: 2020 Toyota Corolla
?>
```

### Tratamento de Erros

O PHP possui vários métodos para tratar erros, incluindo blocos `try-catch`.

```php
<?php
try {
    $arquivo = fopen("arquivo_inexistente.txt", "r");
    if (!$arquivo) {
        throw new Exception("Arquivo não encontrado.");
    }
} catch (Exception $e) {
    echo "Erro: " . $e->getMessage();
}
?>
```

### Trabalhando com APIs

Você pode facilmente interagir com APIs externas utilizando a biblioteca `cURL` do PHP ou a função `file_get_contents()`.

```php
<?php
// Exemplo usando cURL para obter dados de uma API
$ch = curl_init();
curl_setopt($ch, CURLOPT_URL, "https://api.exemplo.com/dados");
curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
$resposta = curl_exec($ch);
curl_close($ch);

$dado = json_decode($resposta, true);
echo "Dados da API: " . $dado['chave'];
?>
```

Este exemplo obtém dados de uma API e exibe o resultado.

