# SOLID

Os princípios **SOLID** são cinco princípios fundamentais para a programação orientada a objetos que ajudam a criar sistemas mais manuteníveis, flexíveis e escaláveis. Esses princípios promovem boas práticas de design, facilitando o desenvolvimento e a manutenção de código de qualidade.

## Índice

- [Princípio da Responsabilidade Única (SRP)](solid-srp)  
  O princípio da responsabilidade única afirma que uma classe deve ter apenas uma razão para mudar, ou seja, deve ser responsável por uma única parte do funcionamento do sistema.

- [Princípio do Aberto/Fechado (OCP)](solid-ocp)  
  O princípio do aberto/fechado estabelece que uma classe deve ser aberta para extensão, mas fechada para modificação, permitindo que o comportamento de uma classe seja alterado sem modificar seu código original.

- [Princípio da Substituição de Liskov (LSP)](solid-lsp)  
  O princípio da substituição de Liskov afirma que objetos de uma classe derivada devem poder substituir objetos de sua classe base sem afetar a funcionalidade do sistema.

- [Princípio da Segregação de Interface (ISP)](solid-isp)  
  O princípio da segregação de interface defende que muitas interfaces específicas são melhores do que uma interface única e geral. As classes não devem ser forçadas a implementar métodos que não utilizam.

- [Princípio da Inversão de Dependência (DIP)](solid-dip)  
  O princípio da inversão de dependência sugere que classes de alto nível não devem depender de classes de baixo nível. Ambas devem depender de abstrações, e as abstrações não devem depender de detalhes, mas sim os detalhes das abstrações.

---

## Princípio da Responsabilidade Única (SRP)

O **Princípio da Responsabilidade Única** (SRP - Single Responsibility Principle) afirma que uma classe deve ter apenas uma razão para mudar, ou seja, deve ser responsável por uma única parte da funcionalidade do sistema. Isso torna o código mais simples de entender e de manter, já que cada classe tem uma responsabilidade bem definida.

Exemplo:

```csharp
// Classe com responsabilidade única: Gerenciamento de Usuários
public class UserManager
{
    public void CreateUser(string name, string email)
    {
        // lógica para criar usuário
    }
    
    public void DeleteUser(int userId)
    {
        // lógica para deletar usuário
    }
}
```

---

## Princípio do Aberto/Fechado (OCP)

O **Princípio do Aberto/Fechado** (OCP - Open/Closed Principle) afirma que uma classe deve ser aberta para extensão, mas fechada para modificação. Isso significa que, se for necessário adicionar um novo comportamento, devemos estender a classe sem alterar seu código original.

Exemplo:

```csharp
public abstract class Shape
{
    public abstract double Area();
}

public class Circle : Shape
{
    public double Radius { get; set; }
    
    public override double Area()
    {
        return Math.PI * Radius * Radius;
    }
}

public class Square : Shape
{
    public double Side { get; set; }
    
    public override double Area()
    {
        return Side * Side;
    }
}
```

---

## Princípio da Substituição de Liskov (LSP)

O **Princípio da Substituição de Liskov** (LSP - Liskov Substitution Principle) afirma que objetos de uma classe derivada devem poder substituir objetos de sua classe base sem afetar a funcionalidade do sistema. Ou seja, uma classe filha deve ser capaz de herdar e reutilizar comportamentos de sua classe base sem quebrar a lógica.

Exemplo:

```csharp
public class Bird
{
    public virtual void Fly()
    {
        Console.WriteLine("Flying...");
    }
}

public class Sparrow : Bird
{
    public override void Fly()
    {
        Console.WriteLine("Sparrow flying...");
    }
}

public class Penguin : Bird
{
    // Aqui não violamos o LSP, pois o Pinguim não deve voar
    public override void Fly()
    {
        throw new NotImplementedException("Penguins cannot fly.");
    }
}
```

---

## Princípio da Segregação de Interface (ISP)

O **Princípio da Segregação de Interface** (ISP - Interface Segregation Principle) defende que muitas interfaces específicas são melhores do que uma única interface geral. As classes não devem ser forçadas a implementar métodos que não utilizam, o que torna o sistema mais flexível e evita a implementação de funcionalidades desnecessárias.

Exemplo:

```csharp
public interface IPrinter
{
    void Print();
}

public interface IScanner
{
    void Scan();
}

public class Printer : IPrinter
{
    public void Print() 
    {
        Console.WriteLine("Printing...");
    }
}

public class Scanner : IScanner
{
    public void Scan() 
    {
        Console.WriteLine("Scanning...");
    }
}
```

---

## Princípio da Inversão de Dependência (DIP)

O **Princípio da Inversão de Dependência** (DIP - Dependency Inversion Principle) sugere que as classes de alto nível não devem depender de classes de baixo nível. Ambas devem depender de abstrações. As abstrações não devem depender de detalhes, mas sim os detalhes das abstrações.

Exemplo:

```csharp
public interface IWriter
{
    void Write(string message);
}

public class FileWriter : IWriter
{
    public void Write(string message)
    {
        // escreve em um arquivo
        Console.WriteLine($"Writing to file: {message}");
    }
}

public class DatabaseWriter : IWriter
{
    public void Write(string message)
    {
        // escreve em um banco de dados
        Console.WriteLine($"Writing to database: {message}");
    }
}

public class MessageService
{
    private IWriter _writer;

    public MessageService(IWriter writer)
    {
        _writer = writer;
    }

    public void WriteMessage(string message)
    {
        _writer.Write(message);
    }
}
```

