# Visual Basic

Bem-vindo à **Wiki Visual Basic**! Este é um recurso abrangente para desenvolvedores que desejam aprender ou aprimorar seus conhecimentos em Visual Basic, uma das linguagens de programação mais utilizadas no desenvolvimento de aplicativos Windows e soluções de automação.

## Descrição

Visual Basic (VB) é uma linguagem de programação de alto nível desenvolvida pela Microsoft, conhecida pela sua simplicidade e facilidade de uso. Inicialmente, foi criada para desenvolvimento de aplicativos de interface gráfica, mas ao longo dos anos evoluiu para suportar programação orientada a objetos e outras funcionalidades modernas. O Visual Basic é amplamente utilizado em sistemas empresariais, automação de tarefas e desenvolvimento de aplicativos para Windows.

Esta wiki fornece uma introdução ao Visual Basic, com exemplos de código, boas práticas e links úteis para ajudá-lo a iniciar ou aprimorar seus projetos.

## Links Úteis

- [Documentação Oficial do Visual Basic](https://learn.microsoft.com/pt-br/dotnet/visual-basic/)
- [Visual Basic no GitHub](https://github.com/dotnet/visualbasic)
- [Referência de Sintaxe do Visual Basic](https://learn.microsoft.com/pt-br/dotnet/visual-basic/language-reference/)
- [Guia de Estilo Visual Basic](https://learn.microsoft.com/pt-br/dotnet/visual-basic/programming-guide/)
- [Exemplos de Código do Visual Basic](https://docs.microsoft.com/pt-br/samples/browse/?languages=visual-basic)

## Índice

- [Descrição](#descrição)
- [Links Úteis](#links-úteis)
- [Versões do Visual Basic](#versões-do-visual-basic)
- [Exemplos de Código Básico](#exemplos-de-código-básico)

## Versões do Visual Basic

O Visual Basic passou por diversas versões desde seu lançamento. Aqui estão algumas das mais importantes:

- **Visual Basic 6.0**  
  Lançado em 1998, foi amplamente utilizado para desenvolvimento de aplicativos Windows, mas foi descontinuado com a introdução do .NET Framework.

- **Visual Basic .NET (VB.NET)**  
  Lançado em 2002 com o .NET Framework, foi uma reescrita completa da linguagem para suportar programação orientada a objetos e a nova arquitetura da Microsoft.

- **VB 2010 - 2019**  
  A Microsoft continuou a evolução da linguagem com melhorias no suporte a LINQ, async/await, e novos recursos para facilitar o desenvolvimento de aplicativos de desktop e web.

- **VB 2022**  
  A versão mais recente com aprimoramentos contínuos de desempenho, compatibilidade com o .NET 5 e além, e suporte a novas ferramentas de desenvolvimento como MAUI.

Para um histórico detalhado das versões do Visual Basic, consulte a [Documentação de Versões do Visual Basic](https://learn.microsoft.com/pt-br/dotnet/visual-basic/language-reference/).

## Exemplos de Código Básico

Aqui estão alguns exemplos para começar a programar em Visual Basic:

**Exemplo "Olá, Mundo"**  
```vb
Module Module1
    Sub Main()
        Console.WriteLine("Olá, Mundo!")
    End Sub
End Module
```

**Lendo um Arquivo de Texto**  
```vb
Module Module1
    Sub Main()
        Dim conteudo As String = System.IO.File.ReadAllText("exemplo.txt")
        Console.WriteLine(conteudo)
    End Sub
End Module
```

**Usando um Loop For**  
```vb
Module Module1
    Sub Main()
        For i As Integer = 0 To 4
            Console.WriteLine("Iteração " & i)
        Next
    End Sub
End Module
```

**Função Simples**  
```vb
Module Module1
    Function Saudacao(nome As String) As String
        Return "Olá, " & nome
    End Function

    Sub Main()
        Console.WriteLine(Saudacao("Alice"))
    End Sub
End Module
```

**Criando uma Classe e Objeto**  
```vb
Module Module1
    Class Pessoa
        Public Nome As String

        Sub New(nome As String)
            Me.Nome = nome
        End Sub

        Sub Saudacao()
            Console.WriteLine("Olá, " & Me.Nome)
        End Sub
    End Class

    Sub Main()
        Dim pessoa As New Pessoa("Alice")
        pessoa.Saudacao()
    End Sub
End Module
```

**Exemplo de uso de Eventos**  
```vb
Module Module1
    Event Saudacao As Action

    Sub Main()
        AddHandler Saudacao, AddressOf ExibirSaudacao
        RaiseEvent Saudacao
    End Sub

    Sub ExibirSaudacao()
        Console.WriteLine("Saudação recebida!")
    End Sub
End Module
```

