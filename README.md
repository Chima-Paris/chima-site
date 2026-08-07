# Chima — Site + éditeur de contenu

Ce dossier contient le site (Accueil + Menu) et un panneau d'administration
(`/admin`) qui te permet de modifier textes, prix et photos sans toucher au code.

## Mise en ligne (à faire une seule fois, ~15 min)

### 1. Créer un dépôt GitHub
- Va sur [github.com](https://github.com), crée un compte si besoin
- Crée un nouveau dépôt (repository), par exemple `chima-site`
- Mets tout le contenu de ce dossier dedans (glisser-déposer sur github.com fonctionne,
  ou via GitHub Desktop si tu préfères une interface)

### 2. Connecter Netlify au dépôt
- Va sur [netlify.com](https://netlify.com), crée un compte gratuit (tu peux te connecter avec GitHub)
- "Add new site" → "Import an existing project" → choisis ton dépôt `chima-site`
- Pas de build command nécessaire, dossier de publication : `/` (racine)
- Clique "Deploy" — ton site est en ligne en quelques secondes sur une adresse
  type `chima-site.netlify.app`

### 3. Activer l'authentification pour l'administration
Decap CMS a besoin de savoir qui a le droit de modifier le contenu :
- Dans Netlify, va dans **Site settings → Identity** → "Enable Identity"
- Toujours dans Identity → **Registration** : mets sur "Invite only" (pour que
  seule toi puisse créer un compte)
- Va dans **Identity → Services → Git Gateway** → clique "Enable Git Gateway"
- Retourne dans l'onglet Identity (en haut du site Netlify) → "Invite users" →
  entre ton email → tu reçois un email pour créer ton mot de passe

### 4. Se connecter à l'administration
- Va sur `https://ton-site.netlify.app/admin`
- Connecte-toi avec l'email/mot de passe créés à l'étape 3
- Tu arrives sur un panneau avec deux sections : **Infos du site** et **Menu**

## Utilisation au quotidien

- **Modifier un prix, ajouter un produit** → section "Menu" → choisis la
  catégorie → ajoute/modifie/supprime un produit
- **Changer une photo** (hero, intérieur, boissons signature) → clique sur le
  champ image concerné → upload ta photo directement
- **Changer horaires, adresse, téléphone** → section "Infos du site"
- Chaque modification que tu publies dans l'admin crée automatiquement une
  mise à jour du site en ligne (via Netlify), en général en moins d'une minute

## Structure du projet

```
index.html        → page Accueil (lit data/site.json)
menu.html          → page Menu (lit data/menu.json)
data/site.json      → textes/photos/horaires de l'accueil — édité via /admin
data/menu.json     → toute la carte — édité via /admin
admin/             → l'interface d'administration (Decap CMS)
images/            → tes photos uploadées depuis /admin arrivent ici
```

## Nom de domaine personnalisé (optionnel)

Une fois le site testé, si tu veux `chima-coffee.fr` au lieu de
`chima-site.netlify.app` :
- Achète le nom de domaine chez un registrar (OVH, Namecheap, Google Domains...) — env. 10-15€/an
- Dans Netlify : **Site settings → Domain management → Add a domain**
- Suis les instructions pour pointer ton domaine vers Netlify (toujours gratuit côté Netlify)
