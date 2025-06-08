
# SavePlaceAPI

## 👥 Integrantes

- **Celso Canaveze Teixeira Pinto — RM556118**  
- **Sofia Domingues Gonçalves — RM554920**  
- **Thiago Moreno Matheus — RM554507**  


## 📜 Descrição

O SavePlaceAPI é uma API RESTful desenvolvida em .NET 8, que faz parte da solução SafePlace, uma plataforma voltada para ajudar comunidades em situações de emergência, desastres naturais e crises, oferecendo informações sobre abrigos e suporte emergencial. A API fornece segurança, robustez e escalabilidade, sendo base para um sistema multiplataforma.

## 📹 Videos

Pitch do Projeto: https://www.youtube.com/watch?v=DNxab_41oIo&ab_channel=SofiaDominguesgoncalves
Demonstração do Sistema em Funcionamento: https://www.youtube.com/watch?v=pO8aTz4dxlA&ab_channel=ThiagoMatheus

## 🚀 Tecnologias Utilizadas

- [.NET 8](https://dotnet.microsoft.com/)
- ASP.NET Core Web API
- Entity Framework Core
- SQL Server
- JWT (JSON Web Token)
- Swagger
- Visual Studio 2022


## 📂 Estrutura Principal de Pastas

SavePlaceAPI/
├── Controllers/
│   ├── AbrigoController.cs
│   ├── UsuarioController.cs
│   └── AlertaController.cs
│
├── Models/
│   ├── Abrigo.cs
│   ├── Usuario.cs
│   └── Alerta.cs
│
├── Data/
│   └── AppDbContext.cs
│
├── DTOs/
│   └── UsuarioLoginDTO.cs
│
├── Services/
│   └── TokenService.cs
│
├── Migrations/
│
├── Properties/
│
├── Program.cs
├── appsettings.json
├── SavePlaceAPI.csproj
└── README.md

## 🔐 Funcionalidades da API

- 🔑 Autenticação com JWT
- 🏠 Gerenciamento de Abrigos
- 🎁 Gerenciamento de Pontos de Doação
- 👥 Cadastro e Login de Usuários
- 🚨 Botão de Emergência (Simulado - IoT)



## 📑 Endpoints Disponíveis

### 🔐 Autenticação
- POST `/api/usuarios/register` — Registro de usuário
- POST `/api/usuarios/login` — Login e geração de token JWT

### 🏠 Abrigos
- GET `/api/abrigos` — Lista todos os abrigos
- GET `/api/abrigos/{id}` — Detalha um abrigo específico
- POST `/api/abrigos` — Cria um abrigo
- PUT `/api/abrigos/{id}` — Atualiza um abrigo
- DELETE `/api/abrigos/{id}` — Remove um abrigo


### 🚨 Alerta
- POST `/api/alerta` — Aciona um alerta de emergência


## 🧠 Autenticação JWT

Após fazer login (`POST /api/usuarios/login`), o retorno é um token:

json
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
}

Use o token no cabeçalho das requisições protegidas:


Authorization: Bearer {seu_token}

## 🔧 Configuração do `appsettings.json`

json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=localhost;Database=SavePlaceDB;User Id=usuario;Password=senha;"
  },
  "Jwt": {
    "Key": "sua-chave-super-secreta",
    "Issuer": "SavePlaceAPI",
    "Audience": "SavePlaceAPI"
  },
  "Logging": {
    "LogLevel": {
      "Default": "Information"
    }
  },
  "AllowedHosts": "*"
}


## ▶️ Como Executar Localmente

### ✅ Pré-requisitos
- .NET 8 instalado
- SQL Server ativo (ou alterar para outro banco)
- Visual Studio 2022

### 🚀 Passos

bash
dotnet restore
dotnet build
dotnet ef database update  # (Cria o banco a partir das migrations)
dotnet run


Acesse:  
🔗 [`https://localhost:5001/swagger`](https://localhost:5001/swagger) para testar os endpoints.



## 🗺️ Banco de Dados

- O banco é gerenciado pelo Entity Framework Core, com migrations.
- Entidades principais:
  - Abrigo
  - Usuario
  - Alerta

### 🔥 Comandos úteis EF Core

bash
dotnet ef migrations add InitialCreate
dotnet ef database update
dotnet ef migrations remove
