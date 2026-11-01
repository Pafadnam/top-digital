# TOP Digital — site web

Site vitrine de l'agence **TOP Digital** (sites internet, identité visuelle, création graphique, motion design).

## Contenu

| Fichier | Rôle |
|---|---|
| `index.html` | Le site complet (7 pages, intro animée, emblème 3D, devis, WhatsApp) |
| `audio/presentation.mp3` | Présentation audio (voix + musique, 1 min 44) |
| `og-image.jpg` | Image d'aperçu quand le lien est partagé (WhatsApp, Facebook, LinkedIn) |
| `favicon.*`, `icon-*.png`, `site.webmanifest` | Icônes du site et de l'écran d'accueil mobile |
| `robots.txt`, `sitemap.xml` | Référencement Google |
| `netlify.toml` | Réglages d'hébergement Netlify |

## Hébergement

Hébergé gratuitement sur Netlify, relié à ce dépôt : chaque modification envoyée sur la branche `main` est mise en ligne automatiquement (1 mise en ligne = 15 crédits sur les 300 crédits gratuits par mois — regrouper les modifications).

Les inscriptions et demandes de devis avec e-mail arrivent dans Netlify → **Forms** (formulaires `inscription` et `devis`).

## Sécurité

- **En-têtes de sécurité** (`netlify.toml`) : politique de sécurité du contenu (CSP) qui n'autorise que le script du site (par empreinte) et Three.js depuis cdnjs, HTTPS forcé (HSTS), interdiction d'afficher le site dans un cadre (anti-clickjacking), capteurs et caméra désactivés.
- **Three.js** est chargé avec une empreinte d'intégrité (SRI) : s'il était modifié sur le CDN, il serait refusé.
- **Limitation des requêtes** : 240 requêtes par minute et par adresse IP, au-delà Netlify répond 429.
- **Formulaires** : champ piège invisible pour les robots, délai minimum, détection d'une vraie saisie humaine, 3 envois maximum par appareil toutes les 10 minutes (8 par jour), doublons ignorés, longueur des champs limitée, caractères dangereux retirés ; Netlify filtre aussi le spam (Akismet).
- **Anti-clics en rafale** : plus de 14 clics en 2 secondes bloquent les interactions pendant 4 secondes ; les actions lourdes (animation 3D, audio, thème) ont un délai minimal entre deux déclenchements.
- `/.well-known/security.txt` indique comment signaler une faille.

Important : le fichier `netlify.toml` est généré. Si `index.html` est modifié à la main, l'empreinte du script dans la CSP doit être recalculée, sinon le site cesse de fonctionner.

Contact : topdigital226@gmail.com · WhatsApp +226 01 21 71 81
