## Setup

Make sure to install dependencies:

```bash
# install bun
npm install -g bun
   
bun install
```

## Development Server

Start the development server on `http://localhost:3000`:

```bash
# bun
bun run dev
```


## Extensions

Install `https://nuxtr.com/`


## Prisma 

`https://www.prisma.io/docs/getting-started/setup-prisma/start-from-scratch/relational-databases/connect-your-database-typescript-postgresql`

Install `bun install prisma -D`
Prisma client : `bun install @prisma/client`

Datasource provider `bunx prisma init --datasource-provider postgresql`

Install postgresql : `https://www.pgadmin.org/download`

Modify `.env` : 
`DATABASE_URL=postgresql://USER:PASSWORD@HOST:PORT/DATABASE?schema=SCHEMA`
`DATABASE_URL=postgresql://postgres:admin@localhost:5432/gobelins?schema=public`

Create your schema in schema.prisma

Finally, run : bunx prisma migrate dev --name init