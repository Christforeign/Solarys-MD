# MR SOLARYS MD

Bot WhatsApp — Owner : **MR SOLARYS-Dev.cl** — Contact : +50940008268

## Variables d'environnement
`SESSION_ID`, `OWNER_NUMBER=50940008268`, `OWNER_NAME=MR SOLARYS-Dev.cl`, `BOT_NAME=MR SOLARYS MD`, `PREFIX=.`

## Déploiement
- **Koyeb** : New Service → GitHub (ou Docker) → Builder *Dockerfile* → type **Worker** (ou Web, port 8000) → ajoute les variables ci-dessus.
- **Katabump** : crée un serveur Node.js, upload le dossier `bot/` (ou clone ton repo), commande de démarrage `npm start`, ajoute `SESSION_ID` dans les variables.
- **Heroku** : `app.json` + `Procfile` inclus.
- **Render / Railway / VPS** : `Dockerfile` ou `render.yaml` inclus (`npm install && npm start`).
- **Termux / VPS** : `npm install && npm start`.

## Premier démarrage (jumelage)
Sans `SESSION_ID`, le bot demande un code de jumelage pour `PAIR_NUMBER` (50940008268) et l'affiche dans la console. Dans WhatsApp : Paramètres → Appareils connectés → Connecter un appareil → Connecter avec le numéro de téléphone.

## Nouveautés (v2)
- **.insulte / .insult** : vannes drôles en français (tag ou réponds à quelqu'un pour le viser).
- **.compliment** : compliment aléatoire (tag, réponse, ou la personne du chat privé).
- **.love** (tout le monde, sans API) : phrases d'amour, citations et poèmes en français, créole et anglais.
  - `.love` (au hasard), `.love phrase`, `.love citation`, `.love poeme`, `.love ai [sujet]` (généré par API, texte local en secours)
  - Réponds au message de quelqu'un ou tague-le pour lui dédier le message. Ajoute tes propres textes dans `lib/lovedata.js`.
- **.chatbot** (sans API) : répond automatiquement aux gens qui t'écrivent, que tu sois en ligne ou hors ligne (tant que le bot tourne).
  - Activé par défaut pour les messages privés. `.chatbot dm on/off`, `.chatbot group on/off`, `.chatbot chat on/off`, `.chatbot status`
  - Modifie les réponses dans `lib/chatbotlocal.js`. Si aucun mot-clé ne correspond, une API IA répond (secours local si elle échoue). Pour ta propre API : `AI_URL`, `AI_KEY`, `AI_MODEL` dans `.env`.
- **Animation vidéo** : `database/menu.mp4` (menu) et `database/anim.mp4` (chaque commande du propriétaire). `.anim all|menu|off`.
- **Antilink réparé** : détecte aussi `chat.whatsapp.com/...`, `wa.me/...`, `www....`, reconnaît les admins même avec les identifiants LID, et le kick fonctionne même si la suppression du message échoue. Le bot doit être admin du groupe.
