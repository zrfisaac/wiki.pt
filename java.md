# Java

Bem-vindo à **Wiki de Java**! Este recurso foi projetado para ajudar os desenvolvedores a entender e utilizar o Java na criação de aplicativos robustos e orientados a objetos.

## Descrição

Java é uma linguagem de programação de alto nível, orientada a objetos, desenvolvida pela Sun Microsystems (atualmente pertencente à Oracle). Ela é amplamente utilizada para a construção de aplicativos multiplataforma, aplicativos web, aplicativos móveis (via Android) e sistemas empresariais de grande escala.

O Java é conhecido por sua portabilidade, escalabilidade e segurança. Sua filosofia "Write Once, Run Anywhere" (Escreva uma vez, execute em qualquer lugar) significa que os aplicativos Java são compilados em bytecode que pode ser executado em qualquer sistema que tenha uma Máquina Virtual Java (JVM), independentemente do hardware ou sistema operacional subjacente.

## Links Úteis

- [Documentação Oficial do Java](https://docs.oracle.com/en/java/)
- [Repositório Oficial do Java no GitHub](https://github.com/openjdk/jdk)
- [Visão Geral da Plataforma Java](https://www.oracle.com/java/)
- [Tutoriais de Java](https://docs.oracle.com/javase/tutorial/)
- [Maven - Gerenciamento de Dependências para Java](https://maven.apache.org/)

## Índice

- [Descrição](#descrição)
- [Links Úteis](#links-úteis)
- [Versões do Java](#versões-do-java)
- [Exemplos Básicos de Código Java](#exemplos-básicos-de-código-java)

## Versões do Java

O Java passou por várias atualizações desde seu lançamento inicial. Algumas versões chave incluem:

- **Java 1.0**  
  A primeira versão do Java, lançada em 1996, estabeleceu o Java como uma linguagem revolucionária projetada para a internet.

- **Java 5 (J2SE 5.0)**  
  Lançado em 2004, essa versão introduziu recursos importantes como generics, anotações de metadados, tipos enumerados e o loop "enhanced for".

- **Java 8**  
  Lançado em 2014, o Java 8 trouxe mudanças significativas, incluindo lambdas, streams e a introdução da API `java.time` para manipulação de datas e horas.

- **Java 11**  
  Lançado em 2018, o Java 11 é uma versão de suporte de longo prazo (LTS) e trouxe vários novos recursos, incluindo a palavra-chave `var` para variáveis locais, além de melhorias em segurança.

- **Java 17**  
  Lançado em 2021, o Java 17 também é uma versão LTS e trouxe uma variedade de melhorias em desempenho, segurança e novos recursos da linguagem.

Para uma lista completa de versões do Java, consulte as [Notas de Lançamento do Java](https://www.oracle.com/java/technologies/javase-downloads.html).

## Exemplos Básicos de Código Java

Aqui estão alguns exemplos básicos de código Java para ajudar você a começar:

**Programa "Hello World"**  
O programa Java mais simples para imprimir "Hello, World!" no console.

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

**Exemplo de Classe e Objeto**  
Um exemplo simples para demonstrar a criação de classes e objetos em Java.

```java
class Carro {
    String modelo;
    int ano;

    // Construtor
    public Carro(String modelo, int ano) {
        this.modelo = modelo;
        this.ano = ano;
    }

    // Método
    public void exibirInfo() {
        System.out.println("Modelo: " + modelo + ", Ano: " + ano);
    }
}

public class Main {
    public static void main(String[] args) {
        Carro carro = new Carro("Toyota", 2020);
        carro.exibirInfo();
    }
}
```

**Exemplo de Loop For-Each**  
Demonstrando o uso do loop for-each em Java.

```java
public class Main {
    public static void main(String[] args) {
        String[] frutas = {"Maçã", "Banana", "Cereja"};
        for (String fruta : frutas) {
            System.out.println(fruta);
        }
    }
}
```

**Exemplo de Expressão Lambda**  
Um exemplo simples de uso de uma expressão lambda para uma interface funcional.

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        List<String> nomes = Arrays.asList("Alice", "Bob", "Charlie");

        // Usando uma expressão lambda para imprimir os nomes
        nomes.forEach(nome -> System.out.println(nome));
    }
}
```

**Exemplo de Tratamento de Exceções Try-Catch**  
Demonstrando como tratar exceções em Java.

```java
public class Main {
    public static void main(String[] args) {
        try {
            int resultado = 10 / 0;
        } catch (ArithmeticException e) {
            System.out.println("Erro: " + e.getMessage());
        }
    }
}
```

**Criando e Executando um Programa Java**  
1. Escreva seu código Java em um arquivo `.java` (exemplo: `HelloWorld.java`).
2. Compile o código usando o seguinte comando:
   ```bash
   javac HelloWorld.java
   ```
3. Execute o código compilado com o comando:
   ```bash
   java HelloWorld
   ```

