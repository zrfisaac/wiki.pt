# C#  

Bem-vindo à **Wiki C#**! Este é um recurso abrangente para desenvolvedores que trabalham com C#, oferecendo insights, dicas e exemplos para ajudá-lo a maximizar suas habilidades de desenvolvimento.  

## Descrição  

C# é uma linguagem de programação moderna e orientada a objetos desenvolvida pela Microsoft como parte da plataforma .NET. Ela é versátil, eficiente e amplamente utilizada para criar aplicações desktop, web e móveis. Com bibliotecas extensivas e suporte ao desenvolvimento multiplataforma via .NET Core e .NET 6/7, o C# permite criar soluções robustas, escaláveis e fáceis de manter.  

Esta wiki serve como um ponto central para explorar os recursos do C#, entender suas capacidades e acessar materiais úteis para melhorar seus projetos.  

## Links Úteis  

- [Documentação Oficial do C#](https://learn.microsoft.com/pt-br/dotnet/csharp/)  
- [Microsoft Learn - .NET](https://learn.microsoft.com/pt-br/dotnet/)  
- [Repositório .NET no GitHub](https://github.com/dotnet/)  
- [Gerenciador de Pacotes NuGet](https://www.nuget.org/)  
- [Padrões de Código C#](https://learn.microsoft.com/pt-br/dotnet/csharp/fundamentals/coding-style/coding-conventions)  

## Índice  

- [Descrição](#descrição)  
- [Links Úteis](#links-úteis)  
- [Versões do C#](#versões-do-c)  
- [Exemplos de Código Básico](#exemplos-de-código-básico)  

## Versões do C#  

O C# evoluiu significativamente desde seu lançamento. Confira alguns marcos importantes:  

- **C# 1.0**  
  Lançado em 2002 com o .NET Framework 1.0, oferecendo capacidades básicas de programação orientada a objetos.  

- **C# 3.0**  
  Introduziu LINQ (Language Integrated Query), expressões lambda e métodos de extensão.  

- **C# 5.0**  
  Apresentou `async/await` para programação assíncrona, simplificando o desenvolvimento de aplicações modernas.  

- **C# 8.0**  
  Adicionou tipos de referência anuláveis, ranges e expressões switch, melhorando a segurança e a legibilidade do código.  

- **C# 10.0**  
  Apresentou `global usings`, namespaces de escopo de arquivo e structs record, simplificando a estrutura do código.  

- **C# 11.0**  
  Versão mais recente, com padrões de lista, correspondência aprimorada (pattern matching) e membros estáticos abstratos em interfaces.  

Para uma lista detalhada de versões e notas de lançamento, visite o [Histórico de Versões do C#](https://learn.microsoft.com/pt-br/dotnet/csharp/whats-new/).  

## Exemplos de Código Básico  

Aqui estão alguns exemplos básicos de código em C# para ajudá-lo a começar:  

**Exemplo "Olá, Mundo"**  
```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Olá, Mundo!");
    }
}
```

**Formulário Simples com um Botão (WinForms)**  
```csharp
using System;
using System.Windows.Forms;

public class MainForm : Form
{
    private Button button;

    public MainForm()
    {
        button = new Button();
        button.Text = "Clique Aqui";
        button.Click += (sender, e) => MessageBox.Show("Botão clicado!");
        Controls.Add(button);
    }

    [STAThread]
    public static void Main()
    {
        Application.Run(new MainForm());
    }
}
```

**Conexão com Banco de Dados usando ADO.NET**  
```csharp
using System;
using System.Data.SqlClient;

class Program
{
    static void Main()
    {
        string connectionString = "Server=seu_servidor;Database=seu_banco;User Id=seu_usuario;Password=sua_senha;";

        using (SqlConnection connection = new SqlConnection(connectionString))
        {
            connection.Open();
            Console.WriteLine("Conexão com o banco de dados bem-sucedida!");

            string query = "SELECT * FROM sua_tabela";
            using (SqlCommand command = new SqlCommand(query, connection))
            using (SqlDataReader reader = command.ExecuteReader())
            {
                while (reader.Read())
                {
                    Console.WriteLine(reader[0]); // Imprime a primeira coluna de cada linha
                }
            }
        }
    }
}
```

