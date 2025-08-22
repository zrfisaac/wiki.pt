# <img src="icon/vstudio.png" alt="Ícone" width="24"> Visual Studio

> *Última atualização: 2025-08-09*

- [📦 Visual Studio Community 2022](https://c2rsetup.officeapps.live.com/c2r/downloadVS.aspx?sku=community&channel=Release&version=VS2022&source=VSLandingPage&cid=2030:baf2f972e3cd43cb9f5e647b1da597f7)

## 🗂️ Estrutura

```cpp
Projeto/
│
├── Binaries/                     // Binários gerados (.exe, .dll)
│   ├── Debug/
│   └── Release/
│
├── Controllers/                  // Lógica que conecta Model e View
│   ├── ClienteController.cs      // Classe: ClienteController
│   ├── PedidoController.cs       // Classe: PedidoController
│   └── ProdutoController.cs      // Classe: ProdutoController
│
├── Data/                         // Classes de acesso a dados / DB
│   └── MainDataModule.cs         // Classe: MainDataModule
│
├── Forms/                        // Formulários principais
│   ├── SplashForm.cs             // Classe: SplashForm
│   ├── ClienteForm.cs            // Classe: ClienteForm
│   ├── MainForm.cs               // Classe: MainForm
│   ├── PedidoForm.cs             // Classe: PedidoForm
│   └── ProdutoForm.cs            // Classe: ProdutoForm
│
├── Libraries/                    // Bibliotecas externas (NuGet ou DLLs)
│   └── Newtonsoft.Json/          // Exemplo de biblioteca externa
│
├── Models/                       // Camada de dados e regras de negócio
│   ├── Cliente.cs                // Classe: Cliente
│   ├── Pedido.cs                 // Classe: Pedido
│   └── Produto.cs                // Classe: Produto
│
├── Objects/                      // Arquivos intermediários do compilador (.obj, .pdb)
│
├── Tests/                        // Testes unitários
│   ├── ClienteTest.cs            // Classe de teste: ClienteTest
│   ├── PedidoTest.cs             // Classe de teste: PedidoTest
│   └── ProdutoTest.cs            // Classe de teste: ProdutoTest
│
├── Views/                        // Arquivos XAML (WPF) ou UserControls
│   ├── ClienteView.xaml          // Classe parcial: ClienteView
│   ├── MainView.xaml             // Classe parcial: MainView
│   ├── PedidoView.xaml           // Classe parcial: PedidoView
│   └── ProdutoView.xaml          // Classe parcial: ProdutoView
│
├── ProjetoVisualStudio.sln       // Solução do Visual Studio
└── ProjetoVisualStudio.csproj    // Projeto principal C#
```
