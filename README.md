Backend do sistema **Bingo Driven**, responsável pelo gerenciamento do bingo.

 

## Deploy 

**API em produção (Render)**
```
https://bingo-backend-deploy.onrender.com

https://bingo-backend-deploy.onrender.com/health (Rota de saúde)
``` 

## STACK
<ul>
  <li>Node.js</li>
  <li>Express</li>
  <li>TypeScript</li>
  <li>Prisma ORM</li>
  <li>PostegreSQL</li>
  <li>Jest + SuperTest</li>
  <li>Docker</li>
  <li>Github Actions</li>
</ul>

## Variáveis de ambiente

Crie um arquivo .env com:
```
PORT=5000 
DATABASE_URL=postgresql://user:password@host:5432/database
```

## Executando sem Docker

```
npm install
npm run dev
``` 

## Executando com Docker
```
docker build -t bingo-backend .
docker run -p 5000:5000 --env-file .env bingo-backend
```

## Executando com Docker Compose
```
docker compose up -d
```

Compose sobre o banco de dados Postegres com volume persistente e o backend com healthCheck dependente do banco


## Testes 

```
npm run test:ci
```

## CI / CD 

**CI** 
<li>Executa testes de integração</li>
<li>Utiliza banco PostgreSQL</li>
<li>Bloqueia deploy em caso de falha</li>

**CD**
<li>Deploy automático no RENDER</li>
<li>Build e Push da imagem no DOCKERHUB</li>
<li>Utilização de GitHub Secrets</li>

