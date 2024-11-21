# TypeScript

---

### **Índice**  
1. [Introdução ao TypeScript](#introdução-ao-typescript)  
2. [Instalação do TypeScript](#instalação-do-typescript)  
3. [Configuração do Ambiente](#configuração-do-ambiente)  
4. [Exemplos de Código](#exemplos-de-código)  
5. [Comandos Úteis do TypeScript](#comandos-úteis-do-typescript)  
6. [Recursos e Links Adicionais](#recursos-e-links-adicionais)  

---

### **Introdução ao TypeScript**  

TypeScript é um superconjunto do JavaScript que adiciona tipagem estática opcional e outros recursos avançados ao JavaScript, facilitando o desenvolvimento de aplicações escaláveis e menos propensas a erros. Ele é amplamente utilizado em projetos de médio e grande porte e é especialmente útil ao trabalhar com bibliotecas modernas e frameworks como React, Angular e Vue.js.  

---

### **Instalação do TypeScript**  

Para instalar o TypeScript globalmente no seu ambiente de desenvolvimento, use o **npm** (Node Package Manager):  
```bash
npm install -g typescript
```  

Para verificar se a instalação foi bem-sucedida:  
```bash
tsc --version
```  

---

### **Configuração do Ambiente**  

1. **Iniciando um Projeto TypeScript:**  
   Use o comando abaixo para criar o arquivo de configuração `tsconfig.json`:  
   ```bash
   tsc --init
   ```  

2. **Exemplo de `tsconfig.json`:**  
   ```json
   {
     "compilerOptions": {
       "target": "es6",
       "module": "commonjs",
       "strict": true,
       "outDir": "./dist",
       "rootDir": "./src"
     },
     "include": ["src/**/*"],
     "exclude": ["node_modules"]
   }
   ```  

3. **Estrutura de Arquivos do Projeto:**  
   ```
   my-typescript-project/
   ├── src/
   │   ├── index.ts
   ├── dist/
   ├── tsconfig.json
   ├── package.json
   ```

---

### **Exemplos de Código**  

#### Tipagem Básica  
```typescript
let message: string = "Hello, TypeScript!";
console.log(message);
```

#### Funções  
```typescript
function add(a: number, b: number): number {
  return a + b;
}
console.log(add(5, 10));
```

#### Interfaces e Classes  
```typescript
interface Person {
  name: string;
  age: number;
}

class Student implements Person {
  constructor(public name: string, public age: number, public course: string) {}

  introduce(): string {
    return `Hi, I'm ${this.name}, and I study ${this.course}.`;
  }
}

const student = new Student("Alice", 22, "Computer Science");
console.log(student.introduce());
```

#### Generics  
```typescript
function identity<T>(arg: T): T {
  return arg;
}

console.log(identity<number>(42));
console.log(identity<string>("TypeScript is great!"));
```

#### Manipulação de Promises e Async/Await  
```typescript
async function fetchData(url: string): Promise<string> {
  const response = await fetch(url);
  return response.text();
}

fetchData("https://jsonplaceholder.typicode.com/posts/1").then(data => console.log(data));
```

---

### **Comandos Úteis do TypeScript**  

1. **Compilar Arquivos TypeScript:**  
   ```bash
   tsc
   ```  

2. **Assistir Mudanças no Código:**  
   ```bash
   tsc --watch
   ```  

3. **Executar Arquivos TypeScript com `ts-node`:**  
   Instale o `ts-node`:  
   ```bash
   npm install -g ts-node
   ```  
   Execute o arquivo diretamente:  
   ```bash
   ts-node src/index.ts
   ```  
