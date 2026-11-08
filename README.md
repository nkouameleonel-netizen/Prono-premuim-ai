# PRONO PREMIUM AI — première version

Cette version affiche les matchs d'une date via API-Football. Elle ne produit pas encore de pronostics : le moteur statistique et l'historique seront ajoutés après validation de la connexion aux données.

## Fichiers
- `public/` : interface du site
- `src/worker.js` : passerelle serveur sécurisée vers API-Football
- `wrangler.toml` : configuration Cloudflare Workers

## Sécurité
Ne mets jamais la clé API dans `public/app.js`, `index.html`, GitHub ou un message public.

## Déploiement Cloudflare
1. Crée un Worker Cloudflare et relie-le au dépôt GitHub.
2. Configure le secret `API_FOOTBALL_KEY` dans les paramètres du Worker.
3. Déploie le projet avec la configuration Wrangler.
4. Ouvre l'adresse du Worker et vérifie `/api/fixtures`.

Le code demande les matchs du jour en fuseau `Africa/Abidjan` et met les réponses en cache pendant 15 minutes.
