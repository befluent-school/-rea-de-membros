# 🎓 Be Fluent School - Plataforma de Ensino de Inglês

Uma plataforma completa de ensino de inglês online com sistema de agendamento de aulas, progresso do aluno e gerenciamento de professores.

## 🚀 Características Principais

- **Sistema de Autenticação Seguro** - JWT com cookies httpOnly
- **Agendamento de Aulas** - Sistema completo de booking com professores
- **Dashboard Interativo** - Para alunos, professores e administradores
- **Sistema de Progresso** - Acompanhamento de atividades e módulos
- **Gerenciamento de Disponibilidade** - Professores podem definir horários
- **Sistema de Reagendamento** - Solicitações e aprovações
- **Interface Responsiva** - Otimizada para mobile e desktop
- **Proteção CSRF** - Segurança avançada contra ataques

## 🛠️ Tecnologias Utilizadas

### Frontend
- **React 18** - Interface de usuário
- **TypeScript** - Tipagem estática
- **Vite** - Build tool e dev server
- **Tailwind CSS** - Estilização
- **Radix UI** - Componentes acessíveis
- **React Query** - Gerenciamento de estado do servidor
- **React Router** - Roteamento

### Backend
- **Node.js** - Runtime JavaScript
- **Express** - Framework web
- **TypeScript** - Tipagem estática
- **Drizzle ORM** - ORM para banco de dados
- **PostgreSQL** - Banco de dados principal
- **JWT** - Autenticação
- **bcryptjs** - Hash de senhas

## 📦 Instalação e Configuração

### Pré-requisitos
- Node.js 18+ 
- PostgreSQL (ou Neon para cloud)
- npm ou yarn

### 1. Clone o repositório
```bash
git clone https://github.com/seu-usuario/be-fluent-school.git
cd be-fluent-school
```

### 2. Instale as dependências
```bash
npm install
```

### 3. Configure as variáveis de ambiente
Crie um arquivo `.env` na raiz do projeto:

```env
NODE_ENV=production
JWT_SECRET=ab6a1c81bd69bb00fe0b635fea366a8695892845511c74aeffecc6a161418118d8827db1910b2450115c87cbcac2e26e38aee589acd98d19a6b5f4368603c405
DATABASE_URL=postgresql://usuario:senha@host:porta/banco
```

### 4. Configure o banco de dados
```bash
# Push do schema para o banco
npm run db:push

# Seed inicial (usuários padrão)
npm run db:seed
```

### 5. Build e execução
```bash
# Build completo
npm run build

# Iniciar servidor
npm start

# Desenvolvimento
npm run dev
```

## 🚀 Deploy

### GitHub Actions
O projeto inclui configuração automática para GitHub Actions. Apenas faça push para a branch `main`:

```bash
git add .
git commit -m "Deploy: Sistema completo"
git push origin main
```

### Vercel
1. Conecte seu repositório ao Vercel
2. Configure as variáveis de ambiente
3. Deploy automático

### Railway
1. Conecte seu repositório ao Railway
2. Configure as variáveis de ambiente
3. Deploy automático

### Replit
1. Importe o repositório no Replit
2. Configure as Secrets (JWT_SECRET, DATABASE_URL)
3. Execute `npm start`

## 📁 Estrutura do Projeto

```
├── client/                 # Frontend React
│   ├── src/
│   │   ├── components/     # Componentes reutilizáveis
│   │   ├── pages/         # Páginas da aplicação
│   │   ├── hooks/         # Custom hooks
│   │   └── lib/           # Utilitários
├── server/                # Backend Node.js
│   ├── routes.ts          # Rotas da API
│   ├── auth.ts            # Autenticação e autorização
│   ├── storage.ts         # Camada de dados
│   └── db.ts              # Configuração do banco
├── shared/                # Tipos compartilhados
│   ├── schema.ts          # Schema do banco
│   └── types.ts           # Tipos TypeScript
├── scripts/               # Scripts de build
├── dist/                  # Build de produção
└── public/                # Arquivos estáticos
```

## 🔧 Scripts Disponíveis

```bash
# Desenvolvimento
npm run dev              # Servidor de desenvolvimento
npm run start:dev        # Iniciar em modo dev

# Build
npm run build            # Build completo otimizado
npm run build:fast       # Build rápido
npm run build:client     # Build apenas frontend
npm run build:server     # Build apenas backend

# Validação
npm run check            # Verificação de tipos
npm run check:watch      # Verificação contínua
npm run validate         # Validação completa

# Banco de dados
npm run db:push          # Push do schema
npm run db:seed          # Seed inicial

# Utilitários
npm run clean            # Limpar build
npm run deploy:replit    # Deploy no Replit
```

## 👥 Usuários Padrão

Após o seed inicial, você terá acesso com:

**Administrador:**
- Email: `admin@befluent.com`
- Senha: `demo123456`

**Professor:**
- Email: `teacher@befluent.com`
- Senha: `demo123456`

**Aluno:**
- Email: `student@teste.com`
- Senha: `demo123456`

## 🔒 Segurança

- **JWT com cookies httpOnly** - Tokens seguros
- **CSRF Protection** - Double-submit cookie pattern
- **Rate Limiting** - Proteção contra ataques
- **Validação de entrada** - Zod schemas
- **Hash de senhas** - bcryptjs com salt
- **Sanitização** - Proteção contra XSS

## 📊 Funcionalidades

### Para Alunos
- ✅ Dashboard com progresso
- ✅ Agendamento de aulas
- ✅ Acompanhamento de atividades
- ✅ Histórico de aulas
- ✅ Solicitação de reagendamento

### Para Professores
- ✅ Dashboard com métricas
- ✅ Gerenciamento de disponibilidade
- ✅ Visualização de aulas
- ✅ Aprovação de reagendamentos
- ✅ Acompanhamento de alunos

### Para Administradores
- ✅ Dashboard completo
- ✅ Gerenciamento de usuários
- ✅ Relatórios e métricas
- ✅ Configurações do sistema
- ✅ Monitoramento de atividades

## 🐛 Solução de Problemas

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
```

### Erro de Porta
- Windows: O sistema usa `localhost` automaticamente
- Linux/Mac: Usa `0.0.0.0` para acesso externo

## 📝 Licença

MIT License - veja o arquivo [LICENSE](LICENSE) para detalhes.

## 🤝 Contribuição

1. Fork o projeto
2. Crie uma branch para sua feature (`git checkout -b feature/AmazingFeature`)
3. Commit suas mudanças (`git commit -m 'Add some AmazingFeature'`)
4. Push para a branch (`git push origin feature/AmazingFeature`)
5. Abra um Pull Request

## 📞 Suporte

Para suporte, abra uma issue no GitHub ou entre em contato.

---

**Desenvolvido com ❤️ para o ensino de inglês online**

