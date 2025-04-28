# Un blog en symfony

## Procédure d'installation

### 1. Prérecquis
- php >= 8.2
- Mysql ou Maria DB
- Apache
- Composer
- Git
- Nodejs

### 2. Clonage du repertoire
- En local, à l'emplacement choisi puis dans le terminal:
    - git clone https://github.com/jc-aziaha/dwwm20_symfony_blog.git

### 3. Installation des dépendances
- composer install
    - Pour installer les dépendances de php
- npm install
    - Pour installer les dépendances de javascript
- npm run dev
    - Pour compiler le code généré via Webpack Encore

### 4. Création de la base de données
- Dupliquer et renommer le .env en .env.dev.local
- Récupérer le code secret du .env.dev et mettre à jour le .env.dev.local
- Configurer les pilotes pour se connecter à la base de données (DATABASE_URL)
- Créer concrètement la base de données:
    - symfony console doctrine:database:create
- Créer les tables
    - Créer les entités (si besoin)
        - symfony console make Entity EntityName
    - Se baser sur l'entité pour générer le code sql correspondant (Faire une migration)
        - symfony console make:migration
    - Exécuter le code sql généré
        - symfony console doctrine:migrations:migrate

### 5. Mise à jour des identifiants de connexion au serveur d'envoi d'email
- Dans le fichier .env.dev.local: 
    - MAILER_DSN="..."
        

### 6. Démarrer le serveur
    - symfony serve
    - symfony server:start
    - php -S localhost:8000 -t public

### 7. Pour stopper le serveur
    - symfony server:stop