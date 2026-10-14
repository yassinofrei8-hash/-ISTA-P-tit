# ISTA'Pétit 🍊

Application mobile-first de commande de repas destinée aux stagiaires OFPPT. Interface en français, prix en dirhams marocains (DH), style crème/orange/noir, données stockées dans le navigateur de démonstration.

## Tester l'application sur le web

Ouvre le dossier `www` puis le fichier `index.html` dans un navigateur. Les photos/illustrations principales sont des emojis pour que le menu reste visible sans connexion à un service d'images. La police Poppins est chargée en ligne si une connexion est disponible.

## Fonctionnalités

- Menu de 9 produits, catégories, recherche et détails du plat.
- Extras payants, quantités, panier et code `BIENVENUE` (-50 % sur la première commande).
- Créneaux de retrait à capacité simulée et paiement au comptoir (espèces ou carte).
- Confirmation `CMD-XXXX`, code de retrait à 4 chiffres et reçu téléchargeable en .txt.
- Suivi/ historique des commandes et carte fidélité.
- Espace Admin de démonstration : statistiques, changements de statut, annulations et journal d'événements.
- Ouverture de Gmail avec un brouillon prérempli pour le journal ou une commande.
- Compilation Android automatique par GitHub Actions.

## Récupérer l'APK Android

1. Ouvre l'onglet **Actions** de ce dépôt : https://github.com/yassinofrei8-hash/-ISTA-P-tit/actions
2. Choisis l'exécution la plus récente **Build ISTA'Pétit APK**.
3. Attends qu'elle affiche **Success** (✓), puis ouvre l'exécution.
4. En bas, dans **Artifacts**, télécharge **istapetit-debug-apk**. Le ZIP contient `app-debug.apk`.
5. Transfère l'APK sur ton téléphone Android et ouvre-le pour tester. Selon les réglages du téléphone, il faudra autoriser l'installation d'une application provenant de cette source.

Chaque mise à jour envoyée sur `main` relance le workflow. Le build est basé sur Capacitor 8. La documentation officielle précise les prérequis Node.js 22+ et Android SDK : https://capacitorjs.com/docs/getting-started/environment-setup

## Accès Admin de démonstration

Le code visible sur la page de connexion est `admin123`. Utilise une adresse Gmail pour préremplir les e-mails de démonstration.

## Limites à connaître

- **Prototype sans backend** : commandes, panier, fidélité et journal sont stockés localement; un autre appareil ne voit pas les mêmes données.
- **Admin non sécurisé** : le code est dans l'interface côté client; ne pas utiliser pour des données privées ou de vraies ventes.
- **E-mail** : l'application ouvre Gmail avec un brouillon; il faut confirmer l'envoi dans Gmail.
- **Paiement** : aucun paiement en ligne n'est réalisé.
- Créneaux, remises et fidélité sont simulés pour une présentation scolaire. Valider les tarifs, disponibilités, hygiène et règles avec l'établissement avant tout usage réel.
