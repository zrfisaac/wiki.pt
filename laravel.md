# Laravel

---

### **Índice**  
1. [Introdução ao Laravel](#introdução-ao-laravel)  
2. [Instalação do Laravel](#instalação-do-laravel)  
3. [Estrutura de Arquivos do Laravel](#estrutura-de-arquivos-do-laravel)  
4. [Rotas no Laravel](#rotas-no-laravel)  
5. [Controladores e Views](#controladores-e-views)  
6. [Configuração do Banco de Dados](#configuração-do-banco-de-dados)  
7. [Comandos Úteis do Artisan](#comandos-úteis-do-artisan)  
8. [Recursos e Links Adicionais](#recursos-e-links-adicionais)  

---

### **Introdução ao Laravel**  

Laravel é um framework PHP moderno, conhecido por sua sintaxe expressiva e ferramentas poderosas para o desenvolvimento de aplicações web. Ele facilita tarefas comuns, como roteamento, autenticação, sessões e cache, permitindo que desenvolvedores criem aplicações robustas com eficiência.  

---

### **Instalação do Laravel**  

#### Requisitos  
- PHP >= 8.1  
- Composer (gerenciador de pacotes para PHP)  
- Um servidor HTTP, como Apache ou Nginx  

#### Instalação  
1. **Instale Laravel com Composer:**  
   ```bash
   composer create-project --prefer-dist laravel/laravel my_laravel_project
   cd my_laravel_project
   ```

2. **Configuração Inicial:**  
   Gere a chave da aplicação:  
   ```bash
   php artisan key:generate
   ```  

3. **Servidor de Desenvolvimento:**  
   Inicie o servidor de desenvolvimento:  
   ```bash
   php artisan serve
   ```  
   Acesse o aplicativo em [http://127.0.0.1:8000](http://127.0.0.1:8000).  

---

### **Estrutura de Arquivos do Laravel**  

O Laravel organiza arquivos e pastas de maneira estruturada. Aqui estão as principais:  

- **`app/`**  
  Contém o código principal da aplicação.  
  - **`Models/`**: Classes que representam tabelas no banco de dados.  
  - **`Http/Controllers/`**: Controladores que gerenciam lógica de requisição e resposta.  

- **`routes/`**  
  Define as rotas da aplicação:  
  - **`web.php`**: Rotas para a interface web.  
  - **`api.php`**: Rotas para APIs.  

- **`resources/views/`**  
  Contém os arquivos Blade (templates HTML).  

- **`database/`**  
  Gerencia migrações, seeds e factories.  

- **`config/`**  
  Configurações do sistema, como banco de dados, cache, e-mail, etc.  

- **`.env`**  
  Arquivo para configurar variáveis de ambiente, como conexão de banco de dados.  

---

### **Rotas no Laravel**  

As rotas definem os pontos de entrada para a aplicação.  

#### Exemplo de Rota Simples  
No arquivo `routes/web.php`:  
```php
Route::get('/', function () {
    return "Bem-vindo ao Laravel!";
});
```

#### Rota com Parâmetros  
```php
Route::get('/user/{id}', function ($id) {
    return "Usuário ID: " . $id;
});
```

#### Rota com Controlador  
```php
Route::get('/products', [ProductController::class, 'index']);
```

---

### **Controladores e Views**  

#### Criando um Controlador  
```bash
php artisan make:controller PageController
```

No arquivo `PageController.php`:  
```php
namespace App\Http\Controllers;

use Illuminate\Http\Request;

class PageController extends Controller
{
    public function home()
    {
        return view('home');
    }
}
```

#### Criando uma View  
No arquivo `resources/views/home.blade.php`:  
```html
<!DOCTYPE html>
<html>
<head>
    <title>Home</title>
</head>
<body>
    <h1>Bem-vindo ao Laravel!</h1>
</body>
</html>
```

#### Vinculando a Rota ao Controlador  
No arquivo `routes/web.php`:  
```php
Route::get('/', [PageController::class, 'home']);
```

---

### **Configuração do Banco de Dados**  

1. **Configuração no `.env`:**  
   Configure as variáveis de ambiente para o banco de dados:  
   ```env
   DB_CONNECTION=mysql
   DB_HOST=127.0.0.1
   DB_PORT=3306
   DB_DATABASE=nome_do_banco
   DB_USERNAME=usuario
   DB_PASSWORD=senha
   ```

2. **Criar uma Migração:**  
   ```bash
   php artisan make:migration create_users_table
   ```

3. **Executar Migrações:**  
   ```bash
   php artisan migrate
   ```

---

### **Comandos Úteis do Artisan**  

1. **Criar Model:**  
   ```bash
   php artisan make:model NomeDoModel
   ```

2. **Criar Controller:**  
   ```bash
   php artisan make:controller NomeDoController
   ```

3. **Rodar Servidor de Desenvolvimento:**  
   ```bash
   php artisan serve
   ```

4. **Limpar Cache:**  
   ```bash
   php artisan cache:clear
   ```

5. **Listar Rotas:**  
   ```bash
   php artisan route:list
   ```
