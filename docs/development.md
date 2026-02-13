# Programação de Funcionalidades

Esta seção descreve a implementação do sistema de Timer de Estudos, relacionando os requisitos funcionais e não funcionais com os artefatos criados (código fonte) e as estruturas de dados utilizadas. O sistema será desenvolvido com front-end em HTML, CSS e JavaScript, back-end em C# (ASP.NET Core API) e banco de dados MySQL.

## Requisitos Atendidos

As tabelas que se seguem apresentam os requisitos funcionais e não-funcionais que relacionam o escopo do projeto com os artefatos criados:

### Requisitos Funcionais

| ID     | Descrição do Requisito | Responsável | Artefato Criado |
|--------|------------------------|-------------|-----------------|
| RF-001 | A aplicação deve permitir que o usuário se registre fornecendo nome, e-mail e senha. | Desenvolvedor | `registro.html` + `AuthController.cs` |
| RF-002 | A aplicação deve permitir que o usuário faça login com e-mail e senha, recebendo um token JWT. | Desenvolvedor | `login.html` + `AuthController.cs` |
| RF-003 | A aplicação deve exibir um timer interativo (iniciar, pausar, reiniciar, finalizar). | Desenvolvedor | `dashboard.html` + `timer.js` |
| RF-004 | O sistema deve permitir que o usuário visualize a lista das suas sessões de estudo anteriores. | Desenvolvedor | `dashboard.html` + `sessoes.js` + `StudySessionsController.cs` |
| RF-005 | A aplicação deve exibir estatísticas de progresso (total de horas no dia, semana e mês). | Desenvolvedor | `dashboard.html` + `estatisticas.js` + `StudySessionsController.cs` |
| RF-006 | O usuário deve poder adicionar uma matéria ou descrição à sessão de estudo antes de finalizá-la. | Desenvolvedor | `dashboard.html` + `timer.js` |
| RF-007 | O sistema deve permitir que administradores acessem um painel com lista de usuários e estatísticas gerais. | Desenvolvedor | `admin.html` + `admin.js` + `AdminController.cs` |
| RF-008 | A aplicação deve validar se o usuário está autenticado antes de permitir o acesso às páginas protegidas. | Desenvolvedor | `auth.js` + middleware JWT |

### Requisitos Não Funcionais

| ID      | Descrição do Requisito | Responsável | Artefato Criado |
|---------|------------------------|-------------|-----------------|
| RNF-001 | O sistema deve utilizar HTTPS em todas as comunicações. | Desenvolvedor | Configuração do servidor (IIS/Azure/outro) |
| RNF-002 | As senhas devem ser armazenadas com hash (bcrypt/PBKDF2). | Desenvolvedor | `AuthController.cs` + `User.cs` (propriedade SenhaHash) |
| RNF-003 | O back-end deve ser desenvolvido em C# com ASP.NET Core (RESTful). | Desenvolvedor | Estrutura do projeto back-end |
| RNF-004 | O front-end deve ser responsivo (desktop, tablet, smartphone). | Desenvolvedor | `style.css` (media queries) |
| RNF-005 | O tempo de resposta das APIs não deve ultrapassar 500 ms. | Desenvolvedor | Otimização de consultas + índices no banco |
| RNF-006 | O código deve ser versionado com Git (commits semânticos). | Desenvolvedor | Repositório GitHub |
| RNF-007 | O sistema deve tratar erros e exibir mensagens amigáveis. | Desenvolvedor | `tratamentoErros.js` + middleware de erro no back-end |
| RNF-008 | O banco de dados MySQL deve ser normalizado até a 3FN. | Desenvolvedor | Scripts de criação das tabelas |

## Descrição das estruturas de dados

### Usuário (User)

| **Nome**      | **Tipo**          | **Descrição**                             | **Exemplo**                                    |
|:-------------:|-------------------|-------------------------------------------|------------------------------------------------|
| Id            | Número (Inteiro)  | Identificador único do usuário            | 1                                              |
| Nome          | Texto (100)       | Nome completo do usuário                  | João da Silva                                  |
| Email         | Texto (100)       | E-mail do usuário (único)                 | joao@email.com                                 |
| SenhaHash     | Texto (255)       | Hash da senha (bcrypt)                    | $2a$11$9KjY...snip...                          |
| Role          | Texto (Enum)      | Papel do usuário: 'user' ou 'admin'       | user                                           |
| CreatedAt     | Data/Hora         | Data e hora do registro                   | 2025-02-13 20:30:00                            |

### Sessão de Estudo (StudySession)

| **Nome**      | **Tipo**          | **Descrição**                             | **Exemplo**                                    |
|:-------------:|-------------------|-------------------------------------------|------------------------------------------------|
| Id            | Número (Inteiro)  | Identificador único da sessão             | 101                                            |
| UserId        | Número (Inteiro)  | ID do usuário que realizou a sessão (FK)  | 1                                              |
| StartTime     | Data/Hora         | Data e hora de início                     | 2025-02-13 14:00:00                            |
| EndTime       | Data/Hora         | Data e hora de término (pode ser nulo)    | 2025-02-13 15:30:00                            |
| DurationSeconds| Número (Inteiro) | Duração total em segundos                 | 5400                                           |
| Subject       | Texto (100)       | Matéria ou assunto estudado (opcional)    | Matemática - Cálculo I                         |
| CreatedAt     | Data/Hora         | Data e hora do registro da sessão         | 2025-02-13 15:30:05                            |

---


