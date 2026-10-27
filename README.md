<div align="center">
# 📚 Sistema de Biblioteca
 
Sistema web para gerenciar **livros**, **usuários** e **empréstimos**, feito com HTML, CSS, JavaScript e Supabase.
 
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=for-the-badge&logo=supabase&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![Vercel](https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white)
 
🔗 **[Acessar o sistema online](https://sistema-biblioteca-supabase.vercel.app)**
 
</div>
---
 
## 📖 Sobre o projeto
 
Projeto acadêmico que demonstra como construir um sistema web completo, do front-end ao banco de dados, e publicá-lo na internet. O front-end (HTML, CSS e JavaScript) conversa diretamente com a API do Supabase, que armazena os dados em um banco PostgreSQL.
 
## ✨ Funcionalidades
 
**Livros**
- Cadastrar, listar e excluir
- Verificar disponibilidade (Disponível / Emprestado)
**Usuários**
- Cadastrar, listar e excluir
**Empréstimos**
- Registrar empréstimo
- Impedir o empréstimo de livro indisponível
- Registrar devolução e atualizar a disponibilidade do livro
- Listar o histórico de empréstimos
## 🛠️ Tecnologias
 
| Camada | Tecnologia |
|---|---|
| Estrutura | HTML5 |
| Estilo | CSS3 |
| Comportamento | JavaScript (vanilla) |
| Banco de dados | PostgreSQL (via Supabase) |
| API / Back-end | Supabase |
| Hospedagem | Vercel |
 
## 🏗️ Arquitetura
 
```
Navegador
   │
   ▼
Vercel  ──►  HTML / CSS / JavaScript
                    │
                    ▼
             Supabase (API)
                    │
                    ▼
               PostgreSQL
```
 
A Vercel hospeda os arquivos estáticos. O Supabase mantém o banco de dados e a API.
 
## 🗂️ Estrutura do projeto
 
```
sistema-biblioteca-supabase/
├── index.html   # estrutura da página
├── style.css    # estilização
└── app.js       # lógica e integração com o Supabase
```
 
## 🗄️ Modelo de dados
 
```
USUARIOS ──< EMPRESTIMOS >── LIVROS
   1:N                         N:1
```
 
| Tabela | Campos principais |
|---|---|
| `usuarios` | `id`, `nome`, `email`, `criado_em` |
| `livros` | `id`, `titulo`, `autor`, `ano`, `disponivel`, `criado_em` |
| `emprestimos` | `id`, `livro_id`, `usuario_id`, `data_emprestimo`, `data_devolucao`, `devolvido` |
 
## 🚀 Como executar
 
### 1. Clonar o repositório
 
```bash
git clone https://github.com/lawanemoraes/sistema-biblioteca-supabase.git
cd sistema-biblioteca-supabase
```
 
### 2. Criar o banco no Supabase
 
1. Crie um projeto em [supabase.com](https://supabase.com/).
2. No **SQL Editor**, crie as tabelas `usuarios`, `livros` e `emprestimos`.
3. Ative o **Row Level Security (RLS)** e crie as políticas de acesso.
### 3. Configurar as chaves
 
No arquivo `app.js`, preencha com os dados do seu projeto (**Project Settings → API Keys / Data API**):
 
```js
const SUPABASE_URL = "https://SEU-PROJETO.supabase.co";
const SUPABASE_ANON_KEY = "SUA_CHAVE_PUBLICA";
```
 
> ⚠️ Use apenas a chave **pública** (publishable/anon). Nunca coloque a `service_role` ou a `secret` no código.
 
### 4. Rodar localmente
 
Abra a pasta no VS Code e use a extensão **Live Server** no `index.html`.
 
## ☁️ Deploy
 
1. Envie o projeto para um repositório no GitHub.
2. Na [Vercel](https://vercel.com/), clique em **Add New → Project** e importe o repositório.
3. Em **Application Preset**, escolha **Other** e deixe o **Root Directory** como `./`. Não é necessário build.
4. Clique em **Deploy**.
A cada novo `commit` na branch `main`, a Vercel publica a atualização automaticamente.
 
## 🔒 Segurança
 
As políticas de RLS deste projeto são abertas e servem **apenas para fins didáticos**. Em uma aplicação real, o acesso deve ser restringido com autenticação e regras de autorização.
 
## 👩‍💻 Autora
 
**Lawane Moraes**
[![GitHub](https://img.shields.io/badge/GitHub-lawanemoraes-181717?style=flat&logo=github)](https://github.com/lawanemoraes)
 
---
 
<div align="center">
Feito com 💙 para fins acadêmicos
</div>
 
Claude terminou a resposta
