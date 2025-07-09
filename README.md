# NLW Agents

Backend API para o projeto NLW Agents, construído com Fastify e TypeScript.

## 🛠️ Tecnologias

- **Runtime**: Node.js com TypeScript
- **Framework**: Fastify
- **Database**: PostgreSQL com pgvector
- **ORM**: Drizzle ORM
- **Validação**: Zod
- **Linting/Formatting**: Biome
- **Containerização**: Docker

## 📁 Estrutura do Projeto

```
src/
├── db/
│   ├── connection.ts
│   ├── migrations/
│   ├── schema/
│   └── seed.ts
├── http/
│   └── routes/
├── env.ts
└── server.ts
```

## 🚀 Setup e Configuração

### Pré-requisitos

- Node.js 22+
- Docker e Docker Compose
- PostgreSQL (via Docker)

### Instalação

1. **Clone o repositório**
   ```bash
   git clone <repository-url>
   cd nlw-agents/server
   ```

2. **Instale as dependências**
   ```bash
   npm install
   ```

3. **Configure as variáveis de ambiente**
   Crie um arquivo `.env` na raiz do projeto:
   ```env
   PORT=3333
   DATABASE_URL=postgres://docker:docker@localhost:5432/agents
   ```

4. **Inicie o banco de dados**
   ```bash
   docker-compose up -d
   ```

5. **Execute as migrações**
   ```bash
   npx drizzle-kit migrate
   ```

6. **Inicie o servidor**
   ```bash
   # Desenvolvimento
   npm run dev
   
   # Produção
   npm start
   ```

## 📋 Scripts Disponíveis

- `npm run dev` - Inicia o servidor em modo desenvolvimento com hot reload
- `npm start` - Inicia o servidor em modo produção
- `npm run db:seed` - Executa o seed do banco de dados

## 🔧 Padrões de Projeto

- **Arquitetura**: Clean Architecture com separação de responsabilidades
- **Validação**: Schema validation com Zod
- **Database**: Migrations automáticas com Drizzle
- **API**: RESTful com Fastify e TypeScript
- **Code Style**: Biome para linting e formatação

## 🌐 Endpoints

- `GET /health` - Health check da API
- `GET /rooms` - Lista de salas disponíveis

## 📊 Banco de Dados

O projeto utiliza PostgreSQL com extensão pgvector para operações com embeddings vetoriais, ideal para aplicações de IA e processamento de linguagem natural. 