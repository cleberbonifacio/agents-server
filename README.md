# NLW Agents

Projeto desenvolvendo uma API robusta e eficiente utilizando tecnologias modernas, durante um evento da **Rocketseat**.

## ?? Tecnologias

- **Node.js** com TypeScript nativo (experimental strip types)
- **Fastify** - Framework web r�pido e eficiente
- **PostgreSQL** com extens�o **pgvector** para vetores
- **Drizzle ORM** - Type-safe database operations
- **Zod** - Schema validation
- **Docker** - Containeriza��o do banco de dados
- **Biome** - Linting e formata��o de c�digo

## ??? Arquitetura

O projeto segue uma arquitetura modular com:

- **Separa��o de responsabilidades** entre rotas, schemas e conex�o com banco
- **Valida��o de schemas** com Zod para type safety
- **ORM type-safe** com Drizzle para opera��es de banco de dados
- **Valida��o de vari�veis de ambiente** centralizadas

## ?? Setup e Configura��o

### Pr�-requisitos

- Node.js (vers�o com suporte a `--experimental-strip-types`)
- Docker e Docker Compose

### 1. Clone o reposit�rio
```bash
git clone <url-do-repositorio>
cd server
```

### 2. Configure o banco de dados
```bash
docker-compose up -d
```

### 3. Configure as vari�veis de ambiente

Crie um arquivo `.env` na raiz do projeto:

```env
PORT=3333
DATABASE_URL=postgresql://docker:docker@localhost:5432/agents
```

### 4. Instale as depend�ncias
```bash
npm install
```

### 5. Execute as migra��es do banco
```bash
npx drizzle-kit migrate
```

### 6. (Opcional) Popule o banco com dados de exemplo
```bash
npm run db:seed
```

### 7. Execute o projeto

**Desenvolvimento:**
```bash
npm run dev
```

**Produ��o:**
```bash
npm start
```

## ?? Scripts Dispon�veis

- `npm run dev` - Executa o servidor em modo de desenvolvimento com hot reload
- `npm start` - Executa o servidor em modo de produ��o
- `npm run db:seed` - Popula o banco de dados com dados de exemplo

## ?? Endpoints 

A API estar� dispon�vel em `http://localhost:3333`

- `GET /health` - Health check da aplica��o
- `GET /rooms` - Lista as salas dispon�veis
