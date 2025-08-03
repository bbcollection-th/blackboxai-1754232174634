# Architecture du Projet AboutSlots Clone

## 🏗️ Structure Modulaire

Ce projet a été refactorisé pour suivre les bonnes pratiques Next.js/React avec une architecture modulaire et réutilisable.

## 📁 Structure des Dossiers

```
src/
├── app/                    # App Router de Next.js
│   ├── layout.tsx         # Layout principal
│   └── page.tsx           # Page d'accueil (utilise HomePage)
├── components/            # Composants réutilisables
│   ├── ui/               # Composants UI de base
│   │   ├── Button.tsx    # Composant bouton réutilisable
│   │   ├── Card.tsx      # Composant carte de base
│   │   ├── Section.tsx   # Wrapper de section standardisé
│   │   ├── CasinoCard.tsx # Carte spécifique aux casinos
│   │   ├── SlotCard.tsx  # Carte spécifique aux slots
│   │   ├── BigWinCard.tsx # Carte pour les gros gains
│   │   ├── NewsCard.tsx  # Carte pour les actualités
│   │   └── index.ts      # Exports centralisés
│   ├── sections/         # Sections de page
│   │   ├── Header.tsx
│   │   ├── PromotionalBanner.tsx
│   │   ├── HeroSection.tsx
│   │   ├── TournamentsSection.tsx
│   │   ├── CasinoBonusSection.tsx
│   │   ├── NavigationCards.tsx
│   │   ├── TopRecommendedCasinos.tsx
│   │   ├── F1CompetitionBanner.tsx
│   │   ├── OnlineSlots.tsx
│   │   ├── BigWins.tsx
│   │   ├── CasinoDaddySection.tsx
│   │   ├── ForumAndProviders.tsx
│   │   ├── NewsSection.tsx
│   │   ├── Footer.tsx
│   │   └── index.ts      # Exports centralisés
│   ├── HomePage.tsx      # Composant page principale
│   └── index.ts          # Exports centralisés
├── hooks/                # Hooks personnalisés
│   └── useMobileMenu.ts  # Gestion du menu mobile
├── types/                # Définitions TypeScript
│   └── index.ts          # Types pour Casino, SlotGame, etc.
└── data/                 # Données statiques
    └── index.ts          # Données des casinos, slots, news, etc.
```

## 🧩 Composants UI Réutilisables

### Button
Composant bouton avec variants (primary, secondary, outline) et tailles (sm, md, lg).

```tsx
<Button variant="primary" size="lg">
  Click me
</Button>
```

### Card
Composant carte de base avec support hover et onClick.

```tsx
<Card hover onClick={() => console.log('clicked')}>
  <div>Contenu de la carte</div>
</Card>
```

### Section
Wrapper standardisé pour les sections avec backgrounds prédéfinis.

```tsx
<Section background="dark" padding="lg">
  <div>Contenu de la section</div>
</Section>
```

## 🎯 Composants Spécialisés

### CasinoCard
Affiche les informations d'un casino (bonus, pourcentage, etc.).

### SlotCard
Affiche les informations d'un jeu de slot avec image et provider.

### BigWinCard
Affiche les informations d'un gros gain avec thumbnail vidéo.

### NewsCard
Affiche un article de news avec image et date.

## 🔧 Hooks Personnalisés

### useMobileMenu
Gère l'état d'ouverture/fermeture du menu mobile.

```tsx
const { isOpen, toggle, close, open } = useMobileMenu();
```

## 📊 Types TypeScript

Définitions strictes pour tous les objets de données :

- `Casino` : Informations des casinos
- `SlotGame` : Informations des jeux de slots
- `BigWin` : Informations des gros gains
- `NewsArticle` : Informations des articles
- `NavigationCard` : Cartes de navigation

## 📦 Données Statiques

Toutes les données sont centralisées dans `src/data/index.ts` :

- `navigationCards` : Cartes de navigation
- `casinos` : Liste des casinos recommandés
- `slotGames` : Liste des jeux de slots
- `bigWins` : Liste des gros gains
- `newsArticles` : Liste des articles

## 🚀 Avantages de cette Architecture

### 1. **Réutilisabilité**
- Composants UI réutilisables dans tout le projet
- Logique métier séparée de la présentation

### 2. **Maintenabilité**
- Code organisé et facile à naviguer
- Séparation claire des responsabilités
- Types TypeScript pour la sécurité

### 3. **Scalabilité**
- Facile d'ajouter de nouvelles sections
- Composants modulaires et indépendants
- Structure extensible

### 4. **Performance**
- Composants optimisés pour React
- Imports sélectifs grâce aux fichiers d'index
- Code splitting naturel

### 5. **Developer Experience**
- Auto-complétion TypeScript
- Imports organisés et propres
- Structure intuitive

## 🔄 Migration depuis l'Ancienne Version

L'ancienne version monolithique (`page-old.tsx`) a été décomposée en :

1. **14 sections modulaires** dans `components/sections/`
2. **7 composants UI réutilisables** dans `components/ui/`
3. **1 hook personnalisé** dans `hooks/`
4. **Types TypeScript** pour la sécurité
5. **Données centralisées** pour la maintenance

## 🛠️ Utilisation

Pour ajouter une nouvelle section :

1. Créer le composant dans `src/components/sections/`
2. L'ajouter aux exports dans `src/components/sections/index.ts`
3. L'importer et l'utiliser dans `HomePage.tsx`

Pour ajouter un nouveau composant UI :

1. Créer le composant dans `src/components/ui/`
2. L'ajouter aux exports dans `src/components/ui/index.ts`
3. L'utiliser dans les sections qui en ont besoin

## 📝 Bonnes Pratiques Appliquées

- ✅ Composants fonctionnels avec TypeScript
- ✅ Props typées strictement
- ✅ Séparation des préoccupations
- ✅ Réutilisabilité maximale
- ✅ Code DRY (Don't Repeat Yourself)
- ✅ Imports organisés avec des fichiers d'index
- ✅ Hooks personnalisés pour la logique métier
- ✅ Données centralisées et typées
- ✅ Architecture scalable et maintenable
