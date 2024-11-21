# ASP.NET MVC

---

### **Índice**  
1. [Introdução ao ASP.NET MVC](#introdução-ao-aspnet-mvc)  
2. [Instalação do ASP.NET MVC](#instalação-do-aspnet-mvc)  
3. [Estrutura de Arquivos do ASP.NET MVC](#estrutura-de-arquivos-do-aspnet-mvc)  
4. [Rotas no ASP.NET MVC](#rotas-no-aspnet-mvc)  
5. [Controladores e Views](#controladores-e-views)  
6. [Configuração do Banco de Dados](#configuração-do-banco-de-dados)  
7. [Comandos Úteis](#comandos-úteis)  
8. [Recursos e Links Adicionais](#recursos-e-links-adicionais)  

---

### **Introdução ao ASP.NET MVC**  

ASP.NET MVC é um framework de desenvolvimento web que segue o padrão de arquitetura Model-View-Controller (MVC), desenvolvido pela Microsoft. Ele permite que você crie aplicações web escaláveis e bem estruturadas, separando a lógica de negócio, a interface do usuário e o controle de fluxo.  

---

### **Instalação do ASP.NET MVC**  

#### Requisitos  
- Visual Studio (recomendado para desenvolvimento)  
- .NET SDK (Software Development Kit)  
- .NET Core ou .NET Framework (dependendo da versão que você escolher)  

#### Instalação via Visual Studio  
1. Abra o Visual Studio e selecione "Criar um novo projeto".  
2. Escolha o template "Aplicativo Web ASP.NET Core" e clique em "Avançar".  
3. Selecione a opção "Aplicativo Web (Modelo MVC)" para criar um projeto MVC.  
4. Configure o nome do projeto e o local para salvá-lo.  
5. Clique em "Criar".  

#### Instalação via .NET CLI  
Se você preferir usar a linha de comando, execute o seguinte comando para criar um novo projeto MVC:  
```bash
dotnet new mvc -n NomeDoProjeto
cd NomeDoProjeto
dotnet run
```

---

### **Estrutura de Arquivos do ASP.NET MVC**  

A estrutura de arquivos no ASP.NET MVC segue um padrão que facilita o desenvolvimento e organização de projetos. Aqui estão os principais diretórios e arquivos:  

- **`Controllers/`**  
  Contém os controladores, que gerenciam as requisições e a lógica do fluxo da aplicação.  
  Exemplo: `HomeController.cs`  

- **`Views/`**  
  Contém as Views (páginas da web) que são renderizadas e enviadas para o usuário. Cada controlador pode ter uma pasta de Views associada.  
  Exemplo: `Views/Home/Index.cshtml`  

- **`Models/`**  
  Contém as classes de modelo que representam os dados da aplicação e são usadas para manipulação e validação.  
  Exemplo: `Product.cs`  

- **`wwwroot/`**  
  Contém arquivos estáticos como CSS, JavaScript e imagens que são servidos para o cliente.  

- **`appsettings.json`**  
  Arquivo de configuração da aplicação, usado para armazenar configurações, como string de conexão com o banco de dados.  

---

### **Rotas no ASP.NET MVC**  

No ASP.NET MVC, as rotas são configuradas no arquivo `Startup.cs` ou `Program.cs` (dependendo da versão do .NET). O padrão de rotas pode ser ajustado para diferentes necessidades.  

#### Rota Padrão  
No arquivo `Program.cs` (ou `Startup.cs` em versões mais antigas), a configuração de rota padrão é geralmente assim:  
```csharp
public class Program
{
    public static void Main(string[] args)
    {
        CreateHostBuilder(args).Build().Run();
    }

    public static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureWebHostDefaults(webBuilder =>
            {
                webBuilder.UseStartup<Startup>();
            });
}
```

A rota padrão é configurada em `Configure` dentro de `Startup.cs`:
```csharp
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
    }
    else
    {
        app.UseExceptionHandler("/Home/Error");
        app.UseHsts();
    }

    app.UseHttpsRedirection();
    app.UseStaticFiles();

    app.UseRouting();

    app.UseEndpoints(endpoints =>
    {
        endpoints.MapControllerRoute(
            name: "default",
            pattern: "{controller=Home}/{action=Index}/{id?}");
    });
}
```

A rota padrão acima mapeia para `HomeController` e o método `Index`.

---

### **Controladores e Views**  

#### Criando um Controlador  
No ASP.NET MVC, controladores são classes que gerenciam o fluxo de requisição e resposta. Para criar um controlador, crie uma classe que herda de `Controller`.

Exemplo de controlador simples:
```csharp
public class HomeController : Controller
{
    public IActionResult Index()
    {
        return View();
    }

    public IActionResult About()
    {
        return View();
    }
}
```

#### Criando uma View  
Views são arquivos que definem o conteúdo HTML exibido para o usuário. No ASP.NET MVC, as Views geralmente têm a extensão `.cshtml`.

Exemplo de `Index.cshtml`:
```html
@{
    ViewData["Title"] = "Home Page";
}

<div class="text-center">
    <h1 class="display-4">@ViewData["Title"]</h1>
    <p>Welcome to ASP.NET Core MVC!</p>
</div>
```

#### Vínculo entre Controlador e View  
O controlador `HomeController` com a ação `Index` renderiza a view `Index.cshtml` automaticamente.  
Quando o usuário acessar a rota `/Home/Index`, o método `Index` será chamado, e o resultado será a renderização da View `Index.cshtml`.

---

### **Configuração do Banco de Dados**  

#### 1. Instalar o Entity Framework Core  
Use o NuGet ou a CLI do .NET para instalar o pacote do Entity Framework Core.

Via CLI:  
```bash
dotnet add package Microsoft.EntityFrameworkCore.SqlServer
```

#### 2. Configurar a String de Conexão  
No arquivo `appsettings.json`, adicione a string de conexão para o banco de dados:

```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=localhost;Database=MyDatabase;User Id=myusername;Password=mypassword;"
  }
}
```

#### 3. Criar e Configurar o Modelo  
Exemplo de modelo `Product.cs`:
```csharp
public class Product
{
    public int Id { get; set; }
    public string Name { get; set; }
    public decimal Price { get; set; }
}
```

#### 4. Criar o Contexto do Banco de Dados  
Crie uma classe `ApplicationDbContext` que herda de `DbContext`:
```csharp
public class ApplicationDbContext : DbContext
{
    public DbSet<Product> Products { get; set; }

    public ApplicationDbContext(DbContextOptions<ApplicationDbContext> options) : base(options) { }
}
```

#### 5. Configurar o Contexto no `Startup.cs`  
```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddDbContext<ApplicationDbContext>(options =>
        options.UseSqlServer(Configuration.GetConnectionString("DefaultConnection")));
    services.AddControllersWithViews();
}
```

---

### **Comandos Úteis**  

1. **Rodar o Projeto:**  
   ```bash
   dotnet run
   ```

2. **Criar Novo Controlador:**  
   ```bash
   dotnet aspnet-codegenerator controller NomeDoControlador --controller
   ```

3. **Gerar Migrations (Banco de Dados):**  
   ```bash
   dotnet ef migrations add InitialCreate
   ```

4. **Atualizar o Banco de Dados:**  
   ```bash
   dotnet ef database update
   ```
