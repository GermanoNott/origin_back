# NLW Agents - Server

Este é o backend da aplicação NLW Agents, desenvolvido em Node.js com TypeScript. A API é construída utilizando o framework Fastify e se conecta a um banco de dados PostgreSQL através do Drizzle ORM.

## Tecnologias Utilizadas

-   **Framework:** [Fastify](https://www.fastify.io/)
-   **Linguagem:** [TypeScript](https://www.typescriptlang.org/)
-   **ORM:** [Drizzle ORM](https://orm.drizzle.team/)
-   **Banco de Dados:** [PostgreSQL](https://www.postgresql.org/)
-   **Validação de Esquemas:** [Zod](https://zod.dev/)
-   **Linter/Formatter:** [Biome](https://biomejs.dev/)

## Padrões e Arquitetura

O projeto utiliza o `fastify-type-provider-zod` para integrar o Zod com o Fastify, garantindo a tipagem e validação automática de rotas (payloads, query strings, etc.), o que aumenta a segurança e a robustez da API.

O Drizzle ORM é utilizado para a comunicação com o banco de dados, permitindo a criação de schemas e queries de forma type-safe.

## Setup e Configuração do Projeto

Siga os passos abaixo para configurar e executar o projeto localmente.

### 1. Instalação de Dependências

```bash
npm install
```

### 2. Configuração do Banco de Dados

Crie um arquivo `.env` na raiz do projeto e adicione a sua string de conexão com o PostgreSQL:

```env
DATABASE_URL="postgresql://USER:PASSWORD@HOST:PORT/DATABASE"
```

### 3. Migrations do Banco de Dados

Para aplicar as migrations e criar as tabelas no banco de dados, execute o seguinte comando. (Assumindo que você tenha um script `db:migrate` no seu `package.json`).

```bash
# Exemplo de script em package.json: "db:migrate": "drizzle-kit migrate"
npm run db:migrate
```

### 4. Executando o Servidor

Para iniciar o servidor em modo de desenvolvimento, execute:

```bash
npm run dev
```

O servidor estará disponível em `http://localhost:3333`.

## Scripts Úteis

-   `dev`: Inicia o servidor de desenvolvimento com hot-reload.
-   `db:migrate`: Aplica as migrações pendentes no banco de dados.
-   `db:generate`: Gera um novo arquivo de migração com base nas alterações do schema do Drizzle.
-   `lint`: Executa o Biome para verificar erros de lint no código.
-   `format`: Formata todo o código do projeto com o Biome.

## Testando a API

Os endpoints da API estão documentados no arquivo `client.http`. Você pode utilizar uma extensão como a REST Client no VS Code para testar as rotas facilmente.
