# ASP.NET

ASP.NET é um framework open-source para o desenvolvimento de aplicativos web dinâmicos. Criado pela Microsoft, ele facilita a criação de aplicações web escaláveis e de alta performance. O ASP.NET suporta várias linguagens de programação, mas o mais comum é usar o C# como a linguagem principal.

---

## Índice

- [Pré-requisitos](#pré-requisitos)  
  Configuração para começar a usar o ASP.NET no seu ambiente de desenvolvimento.

- [Conceitos Básicos do ASP.NET](#conceitos-básicos-do-asp-net)  
  Visão geral dos conceitos fundamentais do ASP.NET, como controllers, views e models.

- [Exemplo de ASP.NET](#exemplo-de-asp-net)  
  Um exemplo simples para criar uma aplicação básica, incluindo a configuração de um controller e uma view.

- [Conceitos Avançados do ASP.NET](#conceitos-avançados-do-asp-net)  
  Tópicos mais avançados, como autenticação, middleware e APIs RESTful.

---

## Pré-requisitos

Para começar a usar o ASP.NET, você precisa de alguns pré-requisitos instalados no seu computador:

1. **.NET SDK**:  
   Baixe e instale o SDK do .NET no [site oficial](https://dotnet.microsoft.com/download).

2. **Editor de Código**:  
   Você pode usar o Visual Studio, Visual Studio Code ou outro editor que suporte .NET. O Visual Studio é altamente recomendado para a maioria dos usuários, pois fornece recursos avançados de depuração e design de interface.

   - **Instalar o Visual Studio**:  
     Baixe o Visual Studio em [visualstudio.microsoft.com](https://visualstudio.microsoft.com/). Durante a instalação, selecione a opção "ASP.NET and web development".

3. **Banco de Dados (Opcional para Exemplos com Banco de Dados)**:  
   Para usar o ASP.NET com banco de dados, você pode usar o SQL Server, PostgreSQL, MySQL, entre outros. O Entity Framework é a principal ferramenta de ORM (Object-Relational Mapping) para o ASP.NET.

---

## Conceitos Básicos do ASP.NET

### Controllers

Os controllers no ASP.NET são responsáveis por lidar com as requisições HTTP, processar a lógica de negócios e retornar a resposta para o usuário. Eles são a parte principal do padrão MVC (Model-View-Controller).

```csharp
using Microsoft.AspNetCore.Mvc;

namespace MeuApp.Controllers
{
    public class HomeController : Controller
    {
        public IActionResult Index()
        {
            return View();
        }

        public IActionResult Saudar(string nome)
        {
            ViewData["Mensagem"] = $"Olá, {nome}!";
            return View();
        }
    }
}
```

### Views

Views no ASP.NET são arquivos que contêm a interface de usuário da aplicação. Elas são responsáveis por exibir os dados que o controller envia.

```html
<!-- Views/Home/Index.cshtml -->
<!DOCTYPE html>
<html>
<head>
    <title>Bem-vindo ao ASP.NET</title>
</head>
<body>
    <h1>Bem-vindo à aplicação ASP.NET!</h1>
</body>
</html>

<!-- Views/Home/Saudar.cshtml -->
<!DOCTYPE html>
<html>
<head>
    <title>Saudação</title>
</head>
<body>
    <h1>@ViewData["Mensagem"]</h1>
</body>
</html>
```

### Models

Models no ASP.NET representam os dados da aplicação e a lógica de negócios. Em muitas aplicações, os models são usados para interagir com o banco de dados.

```csharp
namespace MeuApp.Models
{
    public class Pessoa
    {
        public string Nome { get; set; }
        public int Idade { get; set; }
    }
}
```

---

## Exemplo de ASP.NET

Aqui está um exemplo simples de uma aplicação ASP.NET MVC. Este exemplo mostrará como criar um controller, uma view e passar dados para a view.

### Criar a Aplicação

No terminal, você pode criar uma nova aplicação ASP.NET MVC com o comando:

```bash
dotnet new mvc -n MeuApp
cd MeuApp
```

### Controller

Adicione um novo controller chamado `HomeController`:

```csharp
using Microsoft.AspNetCore.Mvc;
using MeuApp.Models;

namespace MeuApp.Controllers
{
    public class HomeController : Controller
    {
        public IActionResult Index()
        {
            var pessoa = new Pessoa
            {
                Nome = "João",
                Idade = 25
            };
            return View(pessoa);
        }
    }
}
```

### View

Crie uma view chamada `Index.cshtml` que exibe os dados de uma pessoa:

```html
@model MeuApp.Models.Pessoa

<!DOCTYPE html>
<html>
<head>
    <title>Informações de Pessoa</title>
</head>
<body>
    <h1>Nome: @Model.Nome</h1>
    <h2>Idade: @Model.Idade</h2>
</body>
</html>
```

### Rodar a Aplicação

Execute o comando para rodar a aplicação localmente:

```bash
dotnet run
```

A aplicação estará disponível em `http://localhost:5000`. Quando você acessar a URL, verá o nome e a idade da pessoa definidos no controller.

---

## Conceitos Avançados do ASP.NET

### Autenticação

O ASP.NET oferece suporte integrado para autenticação de usuários, com recursos como autenticação de cookie e integração com provedores externos (como Google ou Facebook).

```csharp
public class AccountController : Controller
{
    public IActionResult Login()
    {
        // Lógica de login
        return View();
    }
}
```

Você pode configurar a autenticação no `Startup.cs`:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddAuthentication(CookieAuthenticationDefaults.AuthenticationScheme)
        .AddCookie(options => { options.LoginPath = "/Account/Login"; });
}
```

### Middleware

O middleware no ASP.NET é uma forma de interceptar e processar requisições HTTP. Você pode adicionar middleware para manipular a requisição antes ou depois da execução do controller.

```csharp
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    app.UseMiddleware<MeuMiddleware>();
    app.UseRouting();
    app.UseEndpoints(endpoints => { endpoints.MapControllers(); });
}
```

### APIs RESTful

O ASP.NET é amplamente usado para criar APIs RESTful. Você pode criar um controller de API para fornecer dados em formato JSON.

```csharp
[Route("api/[controller]")]
[ApiController]
public class ProdutosController : ControllerBase
{
    private static List<Produto> _produtos = new List<Produto>
    {
        new Produto { Id = 1, Nome = "Produto A", Preco = 10.0 },
        new Produto { Id = 2, Nome = "Produto B", Preco = 20.0 }
    };

    [HttpGet]
    public IEnumerable<Produto> Get()
    {
        return _produtos;
    }
}
```

### Consumo de API

Você pode consumir APIs em sua aplicação ASP.NET usando o `HttpClient`.

```csharp
using System.Net.Http;
using System.Threading.Tasks;

public class ProdutoService
{
    private readonly HttpClient _httpClient;

    public ProdutoService(HttpClient httpClient)
    {
        _httpClient = httpClient;
    }

    public async Task<IEnumerable<Produto>> GetProdutosAsync()
    {
        var response = await _httpClient.GetStringAsync("https://api.exemplo.com/produtos");
        return JsonSerializer.Deserialize<IEnumerable<Produto>>(response);
    }
}
```
