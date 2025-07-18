# Structure Complète du Repository H8Pharma

## 📁 Arborescence Recommandée

```
h8pharma-frontend/
├── .github/
│   ├── workflows/
│   │   ├── ci.yml                    # Pipeline CI/CD principal
│   │   ├── security-audit.yml        # Audit de sécurité automatique
│   │   └── preview.yml               # Déploiement preview branches
│   ├── ISSUE_TEMPLATE/
│   │   ├── bug_report.md
│   │   ├── feature_request.md
│   │   └── security_report.md
│   ├── pull_request_template.md
│   └── dependabot.yml               # Configuration Dependabot
├── docs/
│   ├── api-schema.md                # Documentation OpenAPI
│   ├── architecture.md              # Architecture technique
│   ├── components.md                # Guide des composants
│   ├── accessibility.md             # Guide WCAG 2.2 AA
│   ├── style-guide.md               # Guide de style
│   └── deployment.md                # Guide de déploiement
├── public/
│   ├── icons/
│   │   ├── pilulo-avatar.svg        # Avatar de Pilulo
│   │   └── h8pharma-logo.svg        # Logo H8Pharma
│   ├── favicon.ico
│   └── manifest.json
├── src/
│   ├── app/                         # Next.js App Router
│   │   ├── (auth)/                  # Routes avec authentification
│   │   │   ├── login/
│   │   │   └── layout.tsx
│   │   ├── api/                     # API Routes
│   │   │   ├── webhook/
│   │   │   ├── auth/
│   │   │   └── health/
│   │   ├── globals.css
│   │   ├── layout.tsx
│   │   ├── page.tsx
│   │   ├── loading.tsx
│   │   ├── error.tsx
│   │   └── not-found.tsx
│   ├── components/
│   │   ├── ui/                      # Composants UI de base
│   │   │   ├── button.tsx
│   │   │   ├── input.tsx
│   │   │   ├── card.tsx
│   │   │   ├── modal.tsx
│   │   │   ├── toast.tsx
│   │   │   └── index.ts
│   │   ├── chat/                    # Interface conversationnelle
│   │   │   ├── chat-window.tsx
│   │   │   ├── message-bubble.tsx
│   │   │   ├── typing-indicator.tsx
│   │   │   ├── message-input.tsx
│   │   │   └── chat-history.tsx
│   │   ├── layout/                  # Layout et navigation
│   │   │   ├── header.tsx
│   │   │   ├── sidebar.tsx
│   │   │   ├── footer.tsx
│   │   │   └── theme-toggle.tsx
│   │   ├── pharmacie/               # Composants H8Pharma
│   │   │   ├── calculator.tsx
│   │   │   ├── drug-search.tsx
│   │   │   ├── user-profile.tsx
│   │   │   ├── pilulo-avatar.tsx
│   │   │   └── quick-actions.tsx
│   │   └── providers/               # Context providers
│   │       ├── theme-provider.tsx
│   │       ├── auth-provider.tsx
│   │       └── toast-provider.tsx
│   ├── hooks/                       # Hooks personnalisés
│   │   ├── use-chat.ts
│   │   ├── use-webhook.ts
│   │   ├── use-calculator.ts
│   │   ├── use-local-storage.ts
│   │   └── use-auth.ts
│   ├── stores/                      # Zustand stores
│   │   ├── chat-store.ts
│   │   ├── user-store.ts
│   │   ├── theme-store.ts
│   │   └── calculator-store.ts
│   ├── utils/                       # Utilitaires
│   │   ├── api.ts
│   │   ├── constants.ts
│   │   ├── validators.ts
│   │   ├── formatters.ts
│   │   └── security.ts
│   ├── types/                       # Types TypeScript
│   │   ├── api.ts
│   │   ├── chat.ts
│   │   ├── user.ts
│   │   ├── calculator.ts
│   │   └── index.ts
│   └── styles/                      # Styles supplémentaires
│       ├── globals.css
│       └── components.css
├── __tests__/                       # Tests
│   ├── components/
│   │   ├── chat/
│   │   ├── ui/
│   │   └── pharmacie/
│   ├── hooks/
│   ├── utils/
│   ├── stores/
│   └── e2e/                         # Tests Cypress
│       ├── integration/
│       ├── fixtures/
│       └── support/
├── .env.example                     # Template variables d'environnement
├── .env.local                       # Variables locales (gitignored)
├── .gitignore
├── .eslintrc.json                   # Configuration ESLint
├── .prettierrc                      # Configuration Prettier
├── cypress.config.ts                # Configuration Cypress
├── jest.config.js                   # Configuration Jest
├── next.config.js                   # Configuration Next.js
├── package.json
├── tailwind.config.js               # Configuration Tailwind
├── tsconfig.json                    # Configuration TypeScript
├── README.md                        # Documentation principale
├── CHANGELOG.md                     # Journal des versions
├── CONTRIBUTING.md                  # Guide de contribution
├── LICENSE                          # Licence
└── vercel.json                      # Configuration Vercel
```

## 📋 Fichiers de Configuration Essentiels

### .gitignore
```gitignore
# Dependencies
node_modules/
.pnp
.pnp.js

# Testing
coverage/
.nyc_output

# Next.js
.next/
out/

# Production
build/
dist/

# Environment variables
.env
.env.local
.env.development.local
.env.test.local
.env.production.local

# Logs
npm-debug.log*
yarn-debug.log*
yarn-error.log*

# IDE
.vscode/
.idea/
*.swp
*.swo

# OS
.DS_Store
Thumbs.db

# Vercel
.vercel

# Cypress
cypress/videos/
cypress/screenshots/
```

### .env.example
```env
# Application
NEXT_PUBLIC_APP_NAME=H8Pharma
NEXT_PUBLIC_APP_VERSION=1.0.0
NEXT_PUBLIC_APP_ENV=development

# Webhook n8n
NEXT_PUBLIC_WEBHOOK_URL=https://your-n8n.domain.com/webhook/pilulo
WEBHOOK_SECRET=your-webhook-secret-key

# Authentification
AUTH_SECRET=your-auth-secret-key
AUTH_PROVIDER=simple

# Base URL
NEXT_PUBLIC_BASE_URL=http://localhost:3000

# Features flags
NEXT_PUBLIC_ENABLE_CALCULATOR=true
NEXT_PUBLIC_ENABLE_DRUG_SEARCH=true
NEXT_PUBLIC_ENABLE_ANALYTICS=false

# Logging
LOG_LEVEL=info
ENABLE_REQUEST_LOGGING=true
```

### package.json (scripts essentiels)
```json
{
  "scripts": {
    "dev": "next dev",
    "build": "next build",
    "start": "next start",
    "lint": "next lint",
    "lint:fix": "next lint --fix",
    "type-check": "tsc --noEmit",
    "test": "jest",
    "test:watch": "jest --watch",
    "test:coverage": "jest --coverage",
    "test:e2e": "cypress run",
    "test:e2e:open": "cypress open",
    "format": "prettier --write .",
    "format:check": "prettier --check .",
    "pre-commit": "lint-staged",
    "prepare": "husky install",
    "analyze": "cross-env ANALYZE=true next build",
    "security:audit": "npm audit",
    "security:fix": "npm audit fix"
  }
}
```

## 🔧 Fichiers de Métadonnées

### CONTRIBUTING.md
```markdown
# Guide de Contribution H8Pharma

## Standards de Code
- TypeScript strict
- ESLint + Prettier
- Tests obligatoires
- Documentation JSDoc

## Workflow Git
- Conventional Commits
- Feature branches
- Pull Request reviews
- Tests automatiques

## Tests
- Couverture minimale 80%
- Tests unitaires + E2E
- Pas de régression

## Déploiement
- Staging automatique
- Review avant production
- Rollback possible
```

### CHANGELOG.md
```markdown
# Changelog H8Pharma Frontend

## [1.0.0] - 2025-01-20

### Ajouté
- Interface de chat avec Pilulo
- Calculatrice médicale intégrée
- Authentification équipe H8Pharma
- Mode sombre/clair
- Tests automatisés
- Pipeline CI/CD

### Sécurité
- Audit de dépendances
- Validation des entrées
- Journalisation des accès
```

