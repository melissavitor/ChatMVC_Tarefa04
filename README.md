# ChatMVC

Aplicação de chat multitela desenvolvida em C# com ASP.NET Core MVC, com armazenamento das mensagens em arquivo JSON no backend.

Projeto desenvolvido como atividade da disciplina de Desenvolvimento Web Back-End, no curso de Sistemas de Informação (PUC Minas).

## Funcionalidades

- Login simples por nome de usuário e sala
- Múltiplas salas de chat, isoladas entre si
- Envio e listagem de mensagens em tempo quase real (atualização automática a cada 5 segundos)
- Persistência das mensagens em arquivo JSON no servidor, sem uso de banco de dados

## Tecnologias

- C# / .NET
- ASP.NET Core MVC
- Razor Views
- JavaScript (auto-refresh)
- JSON (persistência de dados)

## Arquitetura

```
ChatMVC/
├── Controllers/
│   ├── ChatController.cs
│   └── HomeController.cs
├── Models/
│   ├── Message.cs
│   └── ChatViewModel.cs
├── Services/
│   └── JsonChatService.cs
├── Views/
│   ├── Home/
│   └── Chat/
│       ├── Index.cshtml
│       └── Room.cshtml
├── Data/
│   └── messages.json
├── wwwroot/
│   ├── css/
│   └── js/
│       └── chat.js
└── Program.cs
```

O projeto segue o padrão MVC, separando responsabilidades entre:

- **Controllers**: recebem as requisições e orquestram o fluxo
- **Models**: representam os dados (mensagem e o view model da sala)
- **Services**: concentram a lógica de leitura e escrita do arquivo JSON
- **Views**: telas de login e de sala de chat

## Como executar

Pré-requisito: [.NET SDK](https://dotnet.microsoft.com/download) instalado (versão compatível com o `TargetFramework` definido no `ChatMVC.csproj`).

```bash
git clone https://github.com/melissavitor/ChatMVC.git
cd ChatMVC
dotnet run
```

Depois, acesse `http://localhost:5190` (ou a porta indicada no terminal) no navegador.

## Como usar

1. Na tela inicial, informe seu nome e o nome da sala
2. Envie mensagens na sala — elas ficam salvas em `Data/messages.json`
3. Abra a mesma sala em outra aba para ver as mensagens sincronizando automaticamente
