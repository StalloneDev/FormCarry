# Formcarry - E-commerce Platform

Une plateforme e-commerce moderne construite avec React, Express et Prisma.

## Prérequis

- Node.js (v14 ou supérieur)
- npm ou yarn
- PostgreSQL

## Installation

1. Cloner le projet :
```bash
git clone [url-du-repo]
cd formcarry
```

2. Installer les dépendances du frontend :
```bash
npm install
```

3. Installer les dépendances du backend :
```bash
cd server
npm install
```

4. Configurer les variables d'environnement :

Créer un fichier `.env` à la racine du projet backend (dossier server) :
```env
DATABASE_URL="postgresql://user:password@localhost:5432/formcarry"
JWT_SECRET="votre-secret-jwt"
```
NB: Pour genere la cle JWT utilise la commande
  node -e console.log(require('crypto').randomBytes(64).toString('hex'))

5. Initialiser la base de données :
```bash
cd server
npx prisma migrate dev
```

## Démarrage

1. Démarrer le backend :
```bash
cd server
npm run dev
```

2. Dans un autre terminal, démarrer le frontend :
```bash
cd ..
npm run dev
```

L'application sera accessible à l'adresse : http://localhost:5173
Le backends sera accessible à l'adresse : http://localhost:5000

## Fonctionnalités

### Pour les Vendeurs
- Création de compte vendeur
- Gestion des produits (ajout, modification, suppression)
- Configuration du compte KKiapay pour les paiements

### Pour les Clients
- Parcourir les produits
- Ajouter des produits au panier
- Passer des commandes
- Paiement sécurisé via KKiapay

## Structure du Projet

```
formcarry/
├── src/                    # Code source frontend
│   ├── components/         # Composants React réutilisables
│   ├── context/           # Contextes React (Auth, Cart)
│   ├── pages/             # Pages de l'application
│   └── services/          # Services API
├── server/                # Code source backend
│   ├── prisma/           # Schéma et migrations Prisma
│   └── src/              # Code source Express
└── public/               # Fichiers statiques
```

## Technologies Utilisées

### Frontend
- React avec TypeScript
- Chakra UI pour l'interface
- React Router pour la navigation
- Axios pour les requêtes API
- Context API pour la gestion d'état

### Backend
- Express.js
- Prisma ORM
- PostgreSQL
- JWT pour l'authentification

## Paiement

L'application utilise KKiapay pour le traitement des paiements. Les vendeurs doivent configurer leur clé API KKiapay dans les paramètres de leur compte.

## Contribution

1. Fork le projet
2. Créer une branche pour votre fonctionnalité (`git checkout -b feature/ma-fonctionnalite`)
3. Commit vos changements (`git commit -m 'Ajout de ma fonctionnalité'`)
4. Push vers la branche (`git push origin feature/ma-fonctionnalite`)
5. Ouvrir une Pull Request

## Support

Pour toute question ou problème, veuillez ouvrir une issue sur le repository.
