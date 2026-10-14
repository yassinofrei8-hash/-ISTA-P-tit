# ISTA'Pétit
Application de commande de repas pour les stagiaires de l'OFPPT. Clique. Récupère. Mange.

- `www/index.html` : l'application (photos intégrées).
- `.github/workflows/apk.yml` : construit l'APK à chaque push (Actions > dernier run > Artifacts > istapetit-apk).

## Synchronisation des commandes entre appareils (Firebase, gratuit)
Sans serveur, les commandes ne restent que sur l'appareil qui les crée. Pour que l'admin reçoive les commandes d'autres téléphones :
1. Créez un projet sur https://console.firebase.google.com puis « Realtime Database » > « Créer une base de données ».
2. Onglet « Règles », collez (prototype uniquement : accès public) :
   {"rules":{"orders":{".read":true,".write":true}}}
3. Copiez l'URL de la base (ex. https://xxxx-default-rtdb.europe-west1.firebasedatabase.app).
4. Dans `www/index.html`, remplacez `var CLOUD_URL="";` par `var CLOUD_URL="VOTRE_URL";` (sans / final), puis faites un commit.
L'admin affiche alors « cloud » et les commandes se synchronisent toutes les 3 secondes.

## Vraie connexion Google (optionnel)
Par défaut, le choix du compte Google est simulé (aucun mot de passe, rien n'est envoyé à Google).
Pour une vraie connexion avec nom, e-mail et photo du compte :
1. Console Google Cloud > « API et services » > « Identifiants » > « Créer des identifiants » > « ID client OAuth » > type « Application Web ».
2. Dans « Origines JavaScript autorisées », ajoutez l'adresse où l'app est hébergée (ex. https://votre-nom.github.io).
3. Dans `www/index.html`, remplacez `var GOOGLE_CLIENT_ID="";` par votre ID client, puis faites un commit.
Le bouton officiel Google s'affiche alors à la place du bouton de démonstration. Dans l'APK (WebView), Google peut refuser la connexion : utilisez le mode démonstration ou un plugin natif.
