# Configuração do Replit - Be Fluent School

## Variáveis de Ambiente Necessárias

Para que o sistema funcione corretamente no Replit, você precisa configurar as seguintes variáveis de ambiente:

### 1. Acesse a aba "Secrets" no Replit

1. No painel lateral esquerdo, clique em "Secrets" (ícone de cadeado)
2. Adicione as seguintes variáveis:

### 2. Variáveis Obrigatórias

```
NODE_ENV=production
JWT_SECRET=sua-chave-secreta-jwt-super-forte-de-pelo-menos-32-caracteres
DATABASE_URL=sua-url-do-banco-de-dados-postgresql
```

### 3. Como Gerar JWT_SECRET

Execute este comando no terminal do Replit para gerar uma chave segura:

```bash
node -e "console.log(require('crypto').randomBytes(32).toString('hex'))"
```

### 4. Configuração do Banco de Dados

Se você estiver usando Neon (recomendado):
1. Acesse [neon.tech](https://neon.tech)
2. Crie um novo projeto
3. Copie a string de conexão
4. Cole no campo `DATABASE_URL` nas Secrets

### 5. Deploy

Após configurar as variáveis:
1. Clique em "Run" para iniciar o servidor
2. O sistema irá:
   - Fazer o build automaticamente
   - Iniciar o servidor na porta 5000
   - Configurar o banco de dados
   - Criar usuários padrão

### 6. Acesso

- **URL**: `https://seu-projeto.replit.dev`
- **Admin padrão**: 
  - Email: `admin@befluentschool.com`
  - Senha: `admin123`

### 7. Solução de Problemas

Se aparecer "Serviço não disponível":
1. Verifique se todas as variáveis de ambiente estão configuradas
2. Verifique os logs no console
3. Certifique-se de que o banco de dados está acessível
4. Execute `npm run build` manualmente se necessário

### 8. Estrutura do Projeto

```
├── client/          # Frontend React
├── server/          # Backend Node.js
├── shared/          # Tipos compartilhados
├── dist/            # Build de produção
└── public/          # Arquivos estáticos
```
