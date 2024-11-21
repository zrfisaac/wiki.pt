# Ruby

---

### **Índice**  
1. [Introdução ao Ruby](#introdução-ao-ruby)  
2. [Instalação do Ruby](#instalação-do-ruby)  
3. [Configuração do Ambiente](#configuração-do-ambiente)  
4. [Exemplos de Código](#exemplos-de-código)  
5. [Comandos Úteis do Ruby](#comandos-úteis-do-ruby)  
6. [Recursos e Links Adicionais](#recursos-e-links-adicionais)  

---

### **Introdução ao Ruby**  

Ruby é uma linguagem de programação de alto nível, interpretada e dinâmica, conhecida por sua simplicidade e legibilidade. Desenvolvida em meados dos anos 1990, Ruby é frequentemente usada em aplicações web (graças ao framework Ruby on Rails), scripts de automação, desenvolvimento de APIs e muito mais.  

---

### **Instalação do Ruby**  

#### Usando um Gerenciador de Versionamento (Recomendado)  
O `rbenv` ou o `RVM` são ferramentas populares para gerenciar versões do Ruby.  

- **Instalar com `rbenv`:**  
  ```bash
  curl -fsSL https://github.com/rbenv/rbenv-installer/raw/main/bin/rbenv-installer | bash
  rbenv install 3.2.2
  rbenv global 3.2.2
  ruby -v
  ```

- **Instalar com `RVM`:**  
  ```bash
  curl -sSL https://get.rvm.io | bash -s stable
  rvm install 3.2.2
  rvm use 3.2.2 --default
  ruby -v
  ```  

#### Instalação Direta  
Para sistemas baseados em Debian/Ubuntu:  
```bash
sudo apt update
sudo apt install ruby-full
ruby -v
```  

---

### **Configuração do Ambiente**  

1. **Criando um Projeto Ruby:**  
   Crie um diretório para seu projeto e inicialize um arquivo Ruby.  
   ```bash
   mkdir my_ruby_project
   cd my_ruby_project
   touch app.rb
   ```

2. **Instalando Gems (Bibliotecas):**  
   Utilize o gerenciador de pacotes `bundler` para gerenciar dependências.  
   ```bash
   gem install bundler
   bundler init
   ```

3. **Estrutura do Projeto Ruby:**  
   ```
   my_ruby_project/
   ├── app.rb
   ├── Gemfile
   ├── lib/
   └── spec/
   ```

---

### **Exemplos de Código**  

#### Hello World  
```ruby
puts "Hello, Ruby!"
```

#### Funções e Classes  
```ruby
class Person
  attr_accessor :name, :age

  def initialize(name, age)
    @name = name
    @age = age
  end

  def greet
    "Hi, I'm #{@name} and I'm #{@age} years old."
  end
end

person = Person.new("Alice", 30)
puts person.greet
```

#### Manipulação de Arrays e Hashes  
```ruby
# Arrays
numbers = [1, 2, 3, 4, 5]
squared = numbers.map { |n| n**2 }
puts squared.inspect

# Hashes
person = { name: "Bob", age: 25 }
puts "Name: #{person[:name]}, Age: #{person[:age]}"
```

#### Manipulação de Arquivos  
```ruby
File.open("example.txt", "w") { |file| file.write("Hello, File!") }

content = File.read("example.txt")
puts content
```

#### Requests HTTP com `Net::HTTP`  
```ruby
require 'net/http'
require 'json'

url = URI("https://jsonplaceholder.typicode.com/posts/1")
response = Net::HTTP.get(url)
data = JSON.parse(response)

puts "Title: #{data['title']}"
```

---

### **Comandos Úteis do Ruby**  

1. **Executar um Arquivo Ruby:**  
   ```bash
   ruby app.rb
   ```

2. **Interagir com o Ruby no Console (`irb`):**  
   ```bash
   irb
   > puts "Hello, Console!"
   ```

3. **Gerenciar Dependências com Bundler:**  
   Instale as dependências listadas no `Gemfile`:  
   ```bash
   bundle install
   ```

4. **Criar Testes com `RSpec`:**  
   Instale o `RSpec` e inicialize:  
   ```bash
   gem install rspec
   rspec --init
   rspec
   ```

