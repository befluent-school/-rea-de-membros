# 🚀 Guia de Deploy - Be Fluent School

## Deploy via GitHub

### 1. Preparação do Repositório

```bash
# Clone o repositório
git clone https://github.com/seu-usuario/be-fluent-school.git
cd be-fluent-school

# Configure o Git
git config user.name "Seu Nome"
git config user.email "seu@email.com"

# Adicione todos os arquivos
git add .
git commit -m "Initial commit: Sistema completo Be Fluent School"
git push origin main
```

### 2. Configuração de Variáveis de Ambiente

#### No GitHub (Secrets):
1. Vá para Settings > Secrets and variables > Actions
2. Adicione as seguintes secrets:

```
NODE_ENV=production
JWT_SECRET=sua-chave-secreta-jwt-super-forte-de-pelo-menos-32-caracteres
DATABASE_URL=postgresql://usuario:senha@host:porta/banco
```

#### Para Deploy Manual:
Crie um arquivo `.env` na raiz:

```env
NODE_ENV=production
JWT_SECRET=sua-chave-secreta-jwt-super-forte-de-pelo-menos-32-caracteres
DATABASE_URL=postgresql://usuario:senha@host:porta/banco
```

### 3. Deploy Automático via GitHub Actions

O sistema já está configurado para deploy automático:

1. **Push para main**: Deploy automático
2. **Pull Request**: Validação e build de teste

### 4. Deploy Manual

```bash
# Build completo
npm run build

# Deploy para GitHub
npm run deploy:github

# Ou deploy específico para plataforma
npm run deploy:vercel
npm run deploy:railway
npm run deploy:replit
```

## Deploy em Plataformas Específicas

### Vercel

1. **Conecte o repositório**:
   - Acesse [vercel.com](https://vercel.com)
   - Importe o repositório GitHub
   - Configure as variáveis de ambiente

2. **Configuração automática**:
   - O arquivo `vercel.json` já está configurado
   - Deploy automático a cada push

3. **Deploy manual**:
```bash
npm install -g vercel
vercel login
vercel --prod
```

### Railway

1. **Conecte o repositório**:
   - Acesse [railway.app](https://railway.app)
   - Importe o repositório GitHub
   - Configure as variáveis de ambiente

2. **Configuração automática**:
   - O arquivo `railway.toml` já está configurado
   - Deploy automático a cada push

3. **Deploy manual**:
```bash
npm install -g @railway/cli
railway login
railway up
```

### Replit

1. **Importe o repositório**:
   - Acesse [replit.com](https://replit.com)
   - Crie novo Repl
   - Importe do GitHub

2. **Configure as Secrets**:
   - Vá para Secrets (ícone de cadeado)
   - Adicione JWT_SECRET e DATABASE_URL

3. **Execute**:
```bash
npm start
```

### Heroku

1. **Instale Heroku CLI**:
```bash
npm install -g heroku
heroku login
```

2. **Crie a aplicação**:
```bash
heroku create be-fluent-school
```

3. **Configure variáveis**:
```bash
heroku config:set NODE_ENV=production
heroku config:set JWT_SECRET=sua-chave-secreta
heroku config:set DATABASE_URL=sua-url-do-banco
```

4. **Deploy**:
```bash
git push heroku main
```

## Configuração do Banco de Dados

### Neon (Recomendado)

1. Acesse [neon.tech](https://neon.tech)
2. Crie um novo projeto
3. Copie a string de conexão
4. Use no DATABASE_URL

### PostgreSQL Local

```bash
# Instalar PostgreSQL
# Ubuntu/Debian
sudo apt install postgresql postgresql-contrib

# macOS
brew install postgresql

# Windows
# Baixe do site oficial

# Criar banco
createdb befluentschool
```

### Docker

```bash
# Usar o docker-compose incluído
docker-compose up -d

# O banco estará disponível em localhost:5432
```

## Validação do Deploy

### 1. Verificar Build
```bash
npm run build
ls -la dist/
```

### 2. Testar Localmente
```bash
npm start
curl http://localhost:5000/api/status
```

### 3. Verificar Logs
```bash
# Em produção, verifique os logs da plataforma
# Vercel: Dashboard > Functions > Logs
# Railway: Dashboard > Deployments > Logs
# Heroku: heroku logs --tail
```

## Solução de Problemas

### Erro de Build
```bash
# Limpar e reinstalar
npm run clean
rm -rf node_modules package-lock.json
npm install
npm run build
```

### Erro de Banco de Dados
```bash
# Verificar conexão
npm run db:push
npm run db:seed
```

### Erro de Variáveis de Ambiente
- Verifique se todas as variáveis estão configuradas
- Confirme se os valores estão corretos
- Teste localmente com .env

### Erro de Porta
- Verifique se a porta 5000 está disponível
- Configure PORT nas variáveis de ambiente se necessário

## Monitoramento

### Health Checks
- `GET /api/status` - Status da API
- `GET /api/health` - Health check completo
- `GET /api` - Informações básicas

### Logs Importantes
- Erros de autenticação
- Falhas de banco de dados
- Rate limiting
- Build errors

## Backup e Restore

### Backup do Banco
```bash
pg_dump $DATABASE_URL > backup.sql
```

### Restore do Banco
```bash
psql $DATABASE_URL < backup.sql
```

## Atualizações

### Deploy de Atualizações
```bash
git pull origin main
npm run build
npm run deploy:github
```

### Rollback
```bash
git revert <commit-hash>
git push origin main
```

---

**Sistema pronto para deploy! 🚀**
