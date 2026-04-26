# ⚡ Allcoms FTTH Terrain

Application mobile PWA pour techniciens fibre optique — **Allcoms Technologies**.

## 📱 Installation sur téléphone

### Android (Chrome)
1. Ouvre l'URL de ton GitHub Pages dans **Chrome**
2. Menu ⋮ → **"Ajouter à l'écran d'accueil"**
3. L'icône apparaît → l'app s'ouvre en plein écran

### iPhone / iOS (Safari)
1. Ouvre l'URL dans **Safari** (pas Chrome)
2. Bouton Partager 📤 → **"Sur l'écran d'accueil"**

---

## 🚀 Déploiement sur GitHub Pages

1. **Fork** ou clone ce dépôt sur ton compte GitHub
2. Va dans **Settings → Pages**
3. Source : `Deploy from a branch` → `main` → `/ (root)`
4. Clique **Save**
5. Ton app sera accessible à `https://TON-USERNAME.github.io/NOM-DU-REPO/`

---

## 🔄 Mise à jour de l'app

Pour mettre à jour l'application :
1. Remplace le fichier `index.html` par la nouvelle version
2. **Important** : incrémente le numéro de version dans `sw.js` :
   ```js
   const CACHE_NAME = 'ftth-terrain-v2'; // v1 → v2 → v3...
   ```
3. Push sur GitHub → GitHub Pages se met à jour automatiquement
4. Sur le téléphone : ferme et rouvre l'app (ou vide le cache)

---

## 📋 Fonctionnalités

| Module | Description | PDF |
|--------|-------------|-----|
| 🔍 **Expertise FTTH** | Compte rendu contradictoire PTO/PBO/PM | ✅ Local A4 portrait |
| 📋 **Fiche EDL** | Reprise référentiel technique | ✅ Local A4 paysage |
| 💶 **Devis Maintenance** | Devis intervention SIEA + CGV | ✅ Local 2 pages |
| 📁 **Historique** | Tous les rapports sauvegardés | — |

### Fonctionnalités clés
- ✅ **100% hors ligne** après premier chargement (Service Worker)
- ✅ **Signatures numériques** au doigt (OC, OI, Client)
- ✅ **Export PDF** direct depuis l'app (impression native)
- ✅ **Sauvegarde locale** (localStorage) — données persistées sur le téléphone
- ✅ **Logos officiels** : Eiffage Énergie / SIEA Liain / Allcoms
- ✅ **8 forfaits SIEA** avec calcul automatique HT/TTC
- ✅ **Étages et lignes** dynamiques (ajout/suppression)

---

## 📁 Structure du projet

```
/
├── index.html          # Application complète (React vanilla)
├── manifest.json       # Manifest PWA (icône, nom, couleurs)
├── sw.js               # Service Worker (cache offline)
├── icons/
│   ├── icon-192.png    # Icône app 192x192
│   └── icon-512.png    # Icône app 512x512
└── README.md           # Ce fichier
```

---

## 🛠️ Stack technique

- **React 18** (vanilla, sans JSX ni Babel) — chargé depuis CDN
- **CSS-in-JS** inline — zéro dépendance build
- **localStorage** — persistance données
- **Canvas API** — signatures numériques
- **Service Worker** — mode hors ligne
- **Web App Manifest** — installable comme app native

---

*Développé pour Allcoms Technologies - Travaux Publics*
