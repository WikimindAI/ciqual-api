# CIQUAL API — Wikimind

API nutritionnelle gratuite basée sur la base de données **CIQUAL 2025** de l'ANSES.  
Hébergée statiquement sur GitHub Pages. Aucun serveur requis.

🌐 **Live** : https://wikimindai.github.io/ciqual-api  
📦 **Données** : 3 484 aliments · Format JSON · Source ANSES CIQUAL 2025

---

## Démarrage rapide

```js
const res = await fetch('https://wikimindai.github.io/ciqual-api/data.json');
const aliments = await res.json();

// Recherche par nom
const pommes = aliments.filter(a =>
  a.names.fr.toLowerCase().includes('pomme')
);
```

## Endpoints

| Méthode | URL | Description |
|---------|-----|-------------|
| GET | `/data.json` | Tous les aliments (3 484) |
| GET | `/data.json` + filtre client | Recherche, catégorie, id |

## Structure d'un aliment

```json
{
  "id": "2001",
  "names": { "fr": "Pomme, pulpe et peau, crue" },
  "categories": {
    "group_code": "2",
    "group_name": "fruits, légumes, légumineuses et oléagineux"
  },
  "nutrition": {
    "energy": {},
    "carbohydrates": {},
    "fats": {}
  },
  "minerals": {},
  "vitamins": {},
  "source": "CIQUAL 2025",
  "language": "fr"
}
```

## Clé API

Créez une clé gratuite sur [wikimindai.github.io/ciqual-api](https://wikimindai.github.io/ciqual-api).  
Format : `wm-fd` + 8 chiffres uniques (ex: `wm-fd47291830`).

## Fichiers du repo

```
ciqual-api/
├── index.html        ← Interface complète (auth, dashboard, playground, docs)
├── data.json         ← Base de données CIQUAL 2025 (3 484 aliments)
├── database.rules.json ← Règles Firebase Realtime Database
└── README.md
```

## Limites

Les données étant statiques (GitHub Pages), les requêtes sur `/data.json` sont **illimitées**.  
La clé API sert à l'identification pour les futurs endpoints avancés.

## Source

Données issues de la table CIQUAL 2025 — ANSES (Agence nationale de sécurité sanitaire de l'alimentation).  
https://ciqual.anses.fr

---

Made with ❤️ by [Wikimind](https://wikimind.fr)
