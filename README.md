API para gerenciamento de salas, desenvolvida com Fastify, Drizzle ORM e TypeScript.

## Principais Tecnologias
- **Fastify**: Framework web rápido e eficiente
- **Drizzle ORM**: ORM moderno para TypeScript
- **PostgreSQL**: Banco de dados relacional
- **Zod**: Validação de esquemas
- **TypeScript**: Tipagem estática
- **@fastify/cors**: Suporte a CORS
- **drizzle-seed**: Seed para banco de dados
- **Biome**: Lint e formatter

## Estrutura e Padrões
- Arquitetura modular (rotas, banco, config separados)
- Validação de dados com Zod
- Migrations e seeds com Drizzle
- Configuração por variáveis de ambiente

## Setup e Configuração

### 1. Clone o repositório e instale as dependências
```bash
npm install
```

### 2. Configure o banco de dados
O projeto usa PostgreSQL. Você pode subir um container local com Docker:
```bash
docker-compose up -d
```

Isso criará um banco chamado `agents` na porta 5432, usuário e senha: `docker`.

### 3. Variáveis de ambiente
Crie um arquivo `.env` na raiz com:
```
DATABASE_URL=postgresql://docker:docker@localhost:5432/agents
PORT=3333
```

### 4. Rode as migrations e seeds
```bash
# (As migrations são aplicadas automaticamente pelo Drizzle ao rodar a aplicação)

# Para popular o banco com dados fake:
npm run db:seed
```

### 5. Inicie o servidor
```bash
npm run dev
```

A API estará disponível em `http://localhost:3333`.

## Endpoints principais
- `GET /health` — Health check
- `GET /rooms` — Lista todas as salas (campos: id, name)

Exemplo de requisição:
```http
GET http://localhost:3333/rooms
```

## Lint e formatação
O projeto utiliza [Biome](https://biomejs.dev/) para lint e format. Para rodar:
```bash
npx biome check .
npx biome format .
```

---

> Projeto para fins educacionais — NLW Agents 
