# 🏬 Loja Monolítica com .NET 6/8

## 🚀 Descrição

Este repositório demonstra a implementação de uma **Store** (Loja) utilizando uma **arquitetura monolítica** com **.NET 6/8**. A aplicação abrange as principais funcionalidades de uma loja online, incluindo o gerenciamento de produtos, autenticação de usuários, carrinho de compras, pedidos, e sistema de pagamento.

Embora as arquiteturas modernas estejam frequentemente adotando microsserviços, o **monolito** ainda é uma escolha válida para muitas empresas, especialmente no início de um projeto ou para aplicações que não requerem grande escalabilidade.

---

## ⚙️ Arquitetura

A arquitetura do sistema é **monolítica**, o que significa que toda a lógica do sistema está contida em um único aplicativo. Em vez de dividir o sistema em vários serviços independentes, todas as funcionalidades da loja (frontend, backend, banco de dados) estão integradas.

- **Frontend**: A interface de usuário é gerada a partir de **Razor Pages** ou **MVC**.
- **Backend**: A lógica de negócios é centralizada e acessada por APIs internas ou através de chamadas diretas.
- **Banco de Dados**: Utiliza um banco de dados **relacional** como **SQL Server** ou **PostgreSQL** para armazenar dados de produtos, usuários, pedidos e transações.

---

## 💡 Funcionalidades

A aplicação implementa os seguintes módulos:

### 1. **Autenticação e Autorização**
   - Sistema de login e registro de usuários.
   - Proteção de rotas através de **Identity** para gerenciar usuários e roles (papéis).
   - Controle de acesso a áreas restritas, como painel de administração.

### 2. **Gerenciamento de Produtos**
   - Adição, edição e exclusão de produtos.
   - Visualização dos produtos disponíveis para os clientes.
   - Gerenciamento de categorias e tags para facilitar a organização dos produtos.

### 3. **Carrinho de Compras**
   - Adicionar, remover e atualizar produtos no carrinho.
   - Exibição de preços e totais de compras.

### 4. **Pedidos e Pagamentos**
   - Processamento de pedidos após a finalização da compra.
   - Integração com gateways de pagamento (como **Stripe** ou **PayPal**) para processar transações.
   - Geração de faturas e confirmação de pagamento.

### 5. **Administração**
   - Visualização e gerenciamento de pedidos.
   - Painel de administração para gerenciar produtos, categorias e usuários.

---

## 🛠️ Tecnologias Utilizadas

A aplicação foi construída com as seguintes tecnologias:

- **.NET 6/8**: Framework para desenvolvimento da aplicação.
- **ASP.NET Core MVC/Razor Pages**: Para construção de interfaces web dinâmicas e estrutura de backend.
- **Entity Framework Core**: ORM para interação com o banco de dados.
- **SQL Server** ou **PostgreSQL**: Banco de dados relacional para armazenar dados da loja.
- **Identity**: Para gerenciamento de autenticação e autorização de usuários.
- **Stripe/PayPal**: Para integração com sistemas de pagamento.
- **Swagger**: Para documentação da API e testes.

---

## 🔑 Padrões de Projeto

A arquitetura do monolito foi construída com base em boas práticas de design para garantir que o código seja modular e de fácil manutenção. Os principais padrões de projeto aplicados incluem:

- **Repository Pattern**: Para abstrair o acesso aos dados, promovendo desacoplamento entre a lógica de negócios e a camada de dados.
- **Unit of Work**: Para gerenciar transações em conjunto com o padrão Repository, garantindo a consistência dos dados.
- **Dependency Injection**: Para facilitar a injeção de dependências e promover a testabilidade.
- **Service Layer**: Para encapsular a lógica de negócios e promover um design mais organizado.

---

## 🚀 Como Rodar a Aplicação

Para executar a aplicação em um ambiente de desenvolvimento, siga os passos abaixo:

### 1. Clonar o Repositório

```
git clone https://github.com/seu-usuario/store-monolito-dotnet.git
cd store-monolito-dotnet
```

### 2. Configurar o Banco de Dados
Certifique-se de que o SQL Server ou PostgreSQL esteja configurado corretamente. Você pode usar o SQL Server Express local ou uma instância na nuvem.

Crie o banco de dados e configure a string de conexão no arquivo appsettings.json.

```
"ConnectionStrings": {
  "DefaultConnection": "Server=localhost;Database=StoreDb;User Id=sa;Password=SenhaForte!"
}
```

### 3. Executar as Migrations
Para criar o banco de dados e as tabelas necessárias, execute os comandos de migração do Entity Framework Core.

```
dotnet ef database update
```

### 4. Executar a Aplicação

Após a configuração do banco de dados, execute o seguinte comando para rodar a aplicação localmente.

```
dotnet run
A aplicação estará disponível em http://localhost:5000.
```

## ⚙️ Estrutura do Projeto
A estrutura do projeto foi organizada da seguinte maneira para promover a clareza e a modularização:

```
StoreMonolito/  
│  
├── Controllers/           # Controladores de MVC para gerenciar a lógica de navegação  
├── Models/                # Entidades de dados, como Produto, Pedido, Usuário  
├── Services/              # Camada de lógica de negócios (ex.: pagamento, envio)  
├── Repositories/          # Padrão Repository para acesso a dados  
├── Data/                  # Contexto do banco de dados e migrations  
├── Views/                 # Arquivos de Razor Views para renderização  
├── wwwroot/               # Arquivos estáticos (CSS, JS, imagens)  
└── appsettings.json       # Arquivo de configuração da aplicação  
```

## 🛠️ Ferramentas de Desenvolvimento

Visual Studio ou Visual Studio Code: Para desenvolvimento da aplicação.
SQL Server Management Studio (SSMS) ou pgAdmin: Para gerenciar o banco de dados.
Postman ou Swagger UI: Para testar as APIs.
Stripe ou PayPal Developer: Para criar credenciais de pagamento para integração.

## 🎯 Possíveis Melhorias
Embora o sistema monolítico seja uma escolha inicial sólida, ao longo do tempo, pode ser necessário evoluir a arquitetura para uma abordagem mais escalável. Algumas melhorias possíveis incluem:

Desacoplamento por Microsserviços: À medida que o sistema cresce, você pode começar a dividir funcionalidades em microsserviços.
Dockerização: Criar contêineres Docker para isolar os componentes da aplicação, facilitando a implantação em diferentes ambientes.
Testes Automatizados: Implementação de Testes de Unidade e Testes de Integração para garantir a qualidade do código.

## 📝 Licença

Este projeto está licenciado sob a MIT License - veja o arquivo LICENSE.

**Conclusão**
Neste repositório, você aprendeu como criar uma loja online simples utilizando uma arquitetura monolítica com .NET 6/8. A aplicação inclui funcionalidades essenciais de uma loja, como autenticação de usuários, gerenciamento de produtos, pedidos e pagamentos. Esse projeto serve como base para lojas de pequeno a médio porte e pode ser expandido ou evoluído conforme o crescimento das necessidades de negócios.

Se você tiver dúvidas ou sugestões, sinta-se à vontade para abrir um issue ou fazer um pull request.

### Explicação:

- **Arquitetura Monolítica**: Nesse tipo de arquitetura, todos os módulos e componentes da aplicação (backend, frontend e banco de dados) estão em uma única base de código e deploy.
  
- **Funcionalidades da Loja**: A explicação de cada funcionalidade (autenticação, gerenciamento de produtos, pedidos e pagamentos) foi detalhada para mostrar o que a aplicação implementa.

- **Tecnologias**: O projeto usa **ASP.NET Core** para a parte web, **Entity Framework Core** para acesso a dados, e um banco de dados **relacional** (SQL Server ou PostgreSQL). A integração com **Stripe** ou **PayPal** para pagamentos foi mencionada como parte da arquitetura de pagamentos.

- **Estrutura do Projeto**: Uma estrutura recomendada foi fornecida para tornar o código modular e organizado, o que é importante mesmo em uma aplicação monolítica.

- **Melhorias Possíveis**: Como o sistema cresce, uma migração para **microsserviços** ou o uso de **Docker** pode ser uma opção de escalabilidade.
