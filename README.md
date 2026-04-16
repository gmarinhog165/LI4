# Leilões Monet — Plataforma de Leilões de Arte

![.NET](https://img.shields.io/badge/Backend-ASP.NET_Core_8.0-512BD4?logo=dotnet)
![C#](https://img.shields.io/badge/Language-C%23-239120?logo=csharp)
![SQL Server](https://img.shields.io/badge/Database-SQL_Server-CC2927?logo=microsoftsqlserver)
![License](https://img.shields.io/badge/License-MIT-green)

Este projeto consiste no desenvolvimento de uma **plataforma web de leilões de obras de arte**, onde utilizadores podem criar leilões para quadros, licitar em leilões ativos e gerir pagamentos. A aplicação foi desenvolvida no âmbito da unidade curricular **LI4** da Universidade do Minho.

---

## Objetivo

Criar uma aplicação web onde os utilizadores podem:
- Registar-se e autenticar-se na plataforma;
- Consultar e pesquisar leilões de quadros disponíveis;
- Criar leilões para obras de arte próprias;
- Licitar em leilões ativos e acompanhar o estado das suas licitações;
- Gerir o seu perfil pessoal e histórico de participações;
- Processar pagamentos associados a leilões ganhos.

---

## Tech Stack

**Backend:**
- C# com .NET 8.0
- ASP.NET Core MVC
- Camada de Acesso a Dados (DAL) com interfaces (`IUser`, `ILeilao`)
- Autenticação via sessões

**Frontend:**
- Razor Views (`.cshtml`)
- Bootstrap
- jQuery & jQuery Validation
- JavaScript para validações client-side

**Base de Dados:**
- SQL Server (MSSQL)
- Schema: `Li4`

---

## Instruções de Instalação

### Pré-requisitos

- [.NET 8.0 SDK](https://dotnet.microsoft.com/download/dotnet/8.0)
- SQL Server (local ou remoto)
- Visual Studio 2022+ ou Visual Studio Code

### 1. Clonar o repositório

```bash
git clone <url-do-repositorio>
cd LI4
```

### 2. Configurar a base de dados

Execute os scripts SQL na seguinte ordem:

```sql
-- 1. Criar schema e tabelas
basedados/dbCreation.sql

-- 2. (Opcional) Popular com dados de exemplo
basedados/populate.sql
```

### 3. Configurar a ligação à base de dados

Edite o ficheiro [DALConfig.cs](leiloes_monet/leiloes_monet/Models/DAL/DALConfig.cs) e atualize a connection string:

```csharp
Data Source = [SEU_SERVIDOR]; Initial Catalog = Li4; Integrated Security = True;
```

### 4. Executar a aplicação

**Via CLI:**
```bash
cd leiloes_monet/leiloes_monet
dotnet run
```

**Via Visual Studio:**
- Abra `leiloes_monet/leiloes_monet.sln`
- Build a solução (`Ctrl+Shift+B`)
- Execute com `F5`

---

## URL da Aplicação

Após iniciar, a aplicação fica disponível em:

- [https://localhost:7042](https://localhost:7042)
- [http://localhost:5177](http://localhost:5177)

---

## Estrutura de Diretórios

```
.
├── leiloes_monet/          # Aplicação principal (.NET 8.0)
│   └── leiloes_monet/
│       ├── Controllers/    # Controladores MVC (Login, Leilão, Perfil, Pagamento, ...)
│       ├── Models/         # Modelos de dados e camada DAL
│       │   └── DAL/        # Acesso à base de dados (UserDAL, LeilaoDAL)
│       ├── Views/          # Templates Razor por controlador
│       └── wwwroot/        # Ficheiros estáticos (CSS, JS, libs)
├── basedados/              # Scripts SQL (criação e populate)
└── modelos/                # Diagramas e documentação (domínio, casos de uso, modelo lógico)
```

---

## Contribuidores

Este projeto foi desenvolvido por estudantes da Universidade do Minho no âmbito da unidade curricular **LI4** (Laboratório de Informática 4), inserida no percurso de **Engenharia de Aplicações**.

| Nome | ID Universitário |
|------|-----------------|
| [Gonçalo Marinho](https://github.com/gmarinhog165) | A90969 |
| [Henrique Vaz](https://github.com/Vaz7) | A95533 |

---

## Licença

Este projeto está licenciado sob a **MIT License**.
