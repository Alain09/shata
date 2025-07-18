# 🔧 Mini Issue Tracker API avec Interface Admin

Un système de suivi d'incidents moderne développé avec Next.js 15, permettant aux utilisateurs de soumettre des problèmes et aux administrateurs de les gérer via une interface dédiée.

## 🚀 Fonctionnalités

- **Soumission d'incidents** : Interface simple pour soumettre des problèmes (titre, description)
- **Authentification Admin** : Système de connexion sécurisé avec création de compte
- **Dashboard Admin** : Interface de gestion avec liste des incidents et marquage comme résolu
- **Protection des routes** : Middleware de sécurité pour les pages administrateur
- **API REST** : Endpoints complets pour la gestion des incidents

## 🛠️ Stack Technique

### Frontend
- **Next.js 15** - Framework React avec App Router
- **TypeScript** - Typage statique
- **Tailwind CSS** - Framework CSS utilitaire
- **shadcn/ui** - Composants UI modernes
- **React Hook Form** - Gestion des formulaires
- **Zod** - Validation des schémas

### Backend
- **Next.js API Routes** - Endpoints API intégrés
- **Prisma** - ORM et gestion de base de données
- **SQLite** - Base de données locale
- **Better-Auth** - Authentification par identifiants

## 📁 Structure du Projet

```
mini-issue-tracker/
├── src/
│   ├── app/
│   │   ├── api/
│   │   │   ├── issues/
│   │   │   │   ├── route.ts          # GET /api/issues
│   │   │   │   └── [id]/route.ts     # PATCH /api/issues/:id
│   │   │   └── auth/
│   │   │       └── [...all]/route.ts # POST /auth/[...all]
│   │   ├── login_admin/
│   │   │   └── page.tsx              # Page de connexion admin
│   │   ├── signUp_admin/
│   │   │   └── page.tsx              # Page de création compte admin
│   │   ├── dash_admin/
│   │   │   └── page.tsx              # Dashboard admin (protégé)
│   │   └── page.tsx                  # Page de soumission d'incidents
│   ├── components/                   # Composants UI réutilisables
│   ├── lib/                          # Utilitaires et configurations
│   └── middleware.ts                 # Protection des routes admin
├── prisma/
│   └── schema.prisma                 # Schéma de base de données
└── README.md
```

## 🌐 Pages et Routes

### Pages Frontend
- **`/`** - Page de soumission d'incidents
- **`/login_admin`** - Connexion administrateur
- **`/signUp_admin`** - Création de compte administrateur
- **`/dash_admin`** - Dashboard admin (accès protégé)

### Endpoints API
- **`POST /api/issues`** - Soumettre un nouvel incident
- **`GET /api/issues`** - Lister tous les incidents
- **`PATCH /api/issues/:id`** - Marquer un incident comme résolu
- **`POST /auth/[...all]`** - Authentification administrateur

## 🚀 Installation et Démarrage

### Prérequis
- Node.js 18+ 
- npm, yarn, pnpm ou bun

### Installation

1. **Cloner le repository**
```bash
git clone <repository-url>
cd mini-issue-tracker
```

2. **Installer les dépendances**
```bash
npm install
# ou
yarn install
# ou
pnpm install
# ou
bun install
```

3. **Configurer la base de données**
```bash
# Générer le client Prisma
npx prisma generate

# Créer et migrer la base de données
npx prisma db push
```

4. **Configurer les variables d'environnement**
```bash
# Créer un fichier .env.local
cp .env.example .env.local
```

### Démarrage du serveur de développement

```bash
npm run dev
# ou
yarn dev
# ou
pnpm dev
# ou
bun dev
```

Ouvrez [http://localhost:3000](http://localhost:3000) dans votre navigateur pour voir l'application.

## 📊 Utilisation

### Pour les utilisateurs
1. Accédez à `http://localhost:3000`
2. Remplissez le formulaire avec le titre et la description de votre incident
3. Cliquez sur "Soumettre" pour créer l'incident

### Pour les administrateurs
1. **Créer un compte** : Allez sur `http://localhost:3000/signUp_admin`
2. **Se connecter** : Utilisez `http://localhost:3000/login_admin`
3. **Gérer les incidents** : Accédez au dashboard `http://localhost:3000/dash_admin`
   - Visualiser tous les incidents
   - Marquer les incidents comme résolus
   - Filtrer par statut

## 🔐 Sécurité

- **Middleware de protection** : Les routes admin sont protégées par un middleware
- **Authentification** : Système d'authentification avec Better-Auth
- **Validation** : Validation des données avec Zod côté client et serveur
- **TypeScript** : Typage strict pour éviter les erreurs

## 🗄️ Base de Données

Le projet utilise SQLite avec Prisma ORM. Le schéma comprend :

- **Issues** : Stockage des incidents (titre, description, statut, date)
- **Users** : Gestion des comptes administrateurs
- **Sessions** : Gestion des sessions d'authentification

## 🎯 Fonctionnalités Techniques

- **App Router** : Utilisation du nouveau système de routage de Next.js 15
- **Server Components** : Rendu côté serveur optimisé
- **API Routes** : Endpoints intégrés dans Next.js
- **Middleware** : Protection automatique des routes sensibles
- **Responsive Design** : Interface adaptée à tous les écrans

## 🔧 Scripts Disponibles

```bash
npm run dev          # Démarrer le serveur de développement
npm run build        # Construire l'application pour la production
npm run start        # Démarrer l'application en production
npm run lint         # Linter le code
npm run db:push      # Pousser le schéma vers la base de données
npm run db:studio    # Ouvrir Prisma Studio
```

## 📝 Hypothèses et Décisions Techniques

- **SQLite** : Choix pour la simplicité et l'absence de configuration serveur
- **Better-Auth** : Solution moderne et sécurisée pour l'authentification
- **shadcn/ui** : Composants UI cohérents et accessibles
- **Middleware Next.js** : Protection native des routes sans configuration complexe

## 🚀 Améliorations Possibles

- Dockerisation de l'application
- Tests unitaires et d'intégration
- Système de notifications
- Assignation d'incidents
- Historique des modifications
- API de recherche et filtrage avancé

## 📞 Support

Pour toute question ou problème, n'hésitez pas à ouvrir une issue sur le repository.

---

**Développé avec ❤️ using Next.js 15 et TypeScript**
