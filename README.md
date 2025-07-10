LOCKER API – Gestion de logins et mots de passe

DESCRIPTION

Cette API REST permet de stocker des identifiants de connexion à des sites web : login, password, url.

Développée avec Symfony, elle expose trois routes :
- GET /api/items : liste tous les items
- POST /api/items : ajoute un item
- DELETE /api/items/{id} : supprime un item

INSTALLATION

1. Cloner le projet :

git clone https://github.com/ton-utilisateur/locker-api.git
cd locker-api

2. Installer les dépendances :

composer install

3. Configuration de la base de données :

Par défaut, l'application utilise SQLite.

Dans le fichier .env, vérifier ou modifier la ligne :

DATABASE_URL="sqlite:///%kernel.project_dir%/var/data.db"

4. Créer la base et lancer les migrations :

php bin/console doctrine:database:create
php bin/console doctrine:migrations:migrate

LANCER LE SERVEUR

Si tu as Symfony CLI :

symfony server:start

Sinon :

php -S localhost:8000 -t public

ENDPOINTS DISPONIBLES

GET /api/items
→ Récupère tous les identifiants enregistrés

POST /api/items
→ Ajoute un nouvel identifiant
Body JSON attendu :
{
  "login": "monlogin",
  "password": "motdepasse123",
  "url": "https://monsite.com"
}

DELETE /api/items/{id}
→ Supprime un identifiant par son id

Difficultés avec Postman, j'ai été dans l'impossibilité d'exporter ma collection.
