# PortfolioV3

Bienvenue sur mon portfolio pour le BTS SIO
---
# INSTALLATION ET CONFIG DES DOSSIERS
---

npm install-D tailwindcss
npx tailwindcdd init

---
## TAILWIND.CONFIG.JS
---
module.exports = {
  content: [
    './public/**/*.html',
    './src/**/*.js',
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}

---
## PACKAGE.JSON
---

{
  "name": "portfolio",
  "version": "1.0.0",
  "main": "index.js",
  "scripts": {
    "build:css": "npx tailwindcss -i ./src/input.css -o ./dist/css/style.css"
  },
  "dependencies": {
    "autoprefixer": "^10.4.0",
    "postcss": "^8.4.5",
    "tailwindcss": "^3.0.0"
  }
}

---
## SRC/INPUT.CSS
---
<!-- Pour que tailwind scanne tous les fichiers ayant la temrinaison voulue, ici .html et js -->

@tailwind base; /_ La directive base permet de faire un reset css _/
@tailwind components;/_ components autorise la création de nouveaux composants afin de les réutiliser _/
@tailwind utilities;/_ contient tous les utilitaires _/

---
## COMPILATION
---
npx tailwindcss -i ./src/css/input.css -o ../dist/css/style.css --watch  <!-- TOUJOURS VERIFIER LE CHEMIN DES DOSSIERS SINON ERREUR -->
-i = analyse input -o = analyse fichier output --watch permet de loop la commande a chaque enregistrement

---
## Go to > index.html
---
Ajouter l'ancre CSS
<link rel="stylesheet" href="style.css">

S'assurer que la balise h1 a une taille réduite = on sait que tailwind a effectué un reset des propriétés par défaut du HTML

---
## ERREURS POSSIBLES
---
1. Problèmes de Configuration Initiale
Manque de fichiers de configuration

    Erreur : Fichiers tailwind.config.js ou postcss.config.js manquants ou mal configurés.

    Solution : Assurez-vous de générer les fichiers de configuration nécessaires en suivant la documentation officielle de TailwindCSS.

    bash

npx tailwindcss init

Exemple de tailwind.config.js :

javascript

module.exports = {
  content: [
    './public/**/*.html',
    './src/**/*.js',
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}

Exemple de postcss.config.js :

javascript

    module.exports = {
      plugins: {
        tailwindcss: {},
        autoprefixer: {},
      }
    }

2. Problèmes de Chemins de Fichiers
Chemins incorrects dans les commandes ou les fichiers de configuration

    Erreur : Les fichiers CSS ou HTML ne sont pas trouvés car les chemins spécifiés sont incorrects.

    Solution : Vérifiez que les chemins spécifiés dans les fichiers de configuration et les commandes sont corrects.

    bash

    npx tailwindcss -i ./src/input.css -o ./dist/css/style.css --watch

    Assurez-vous que le fichier input.css existe à l'emplacement spécifié (./src/input.css).

3. Problèmes de Paquets et de Dépendances
Dépendances manquantes ou incompatibles

    Erreur : Problèmes avec les paquets npm comme tailwindcss, postcss, ou autoprefixer.

    Solution : Assurez-vous d'avoir installé toutes les dépendances nécessaires et compatibles.

    bash

    npm install tailwindcss postcss autoprefixer

    Vérifiez les versions dans package.json pour vous assurer qu'elles sont compatibles.

4. Problèmes de Génération de Fichier CSS
Le fichier CSS n'est pas généré ou n'est pas mis à jour

    Erreur : Le fichier CSS n'est pas généré ou les modifications ne sont pas reflétées.

    Solution : Assurez-vous d'exécuter les commandes de build correctement et de vérifier que le mode --watch fonctionne.

    bash

npm run build:css

ou

bash

    npx tailwindcss -i ./src/input.css -o ./dist/css/style.css --watch

5. Problèmes de Chemins Relatifs dans le HTML
Le chemin du fichier CSS dans le fichier HTML est incorrect

    Erreur : Les styles ne sont pas appliqués parce que le chemin du fichier CSS dans le fichier HTML est incorrect.

    Solution : Assurez-vous que le chemin relatif dans la balise <link> est correct.

    Exemple :

    html

    <link href="/dist/css/style.css" rel="stylesheet">

    Assurez-vous que le chemin /dist/css/style.css correspond à l'emplacement réel du fichier CSS généré.

6. Conflits avec Autres CSS ou Frameworks
Conflits avec d'autres fichiers CSS ou frameworks

    Erreur : Conflits de styles entre TailwindCSS et d'autres fichiers CSS ou frameworks.
    Solution : Assurez-vous que TailwindCSS est bien configuré et, si nécessaire, utilisez les classes utilitaires de manière à éviter les conflits.

7. Permissions et Problèmes Système
Problèmes de permissions ou de configuration système

    Erreur : Les fichiers ne sont pas accessibles ou les commandes ne s'exécutent pas correctement en raison de permissions insuffisantes.
    Solution : Assurez-vous d'avoir les permissions nécessaires pour accéder et modifier les fichiers du projet. Utilisez sudo si nécessaire (sur Linux ou macOS).

Diagnostic Général

    Vérifiez les messages d'erreur dans le terminal : Les messages d'erreur peuvent fournir des indices sur ce qui ne va pas.
    Assurez-vous que votre terminal est dans le bon répertoire : Naviguez jusqu'à la racine de votre projet avant d'exécuter des commandes.
    Consultez la documentation officielle : La documentation de TailwindCSS est une excellente ressource pour résoudre des problèmes spécifiques.



Il se peut qu'il faille rebuild le dossier dès qu'il y a un problème : npm install / npm run build:css ou alors commande tailwind / npx tailwindcss -i ./src/input.css -o ./dist/css/style.css --watch


Le powershell renvoie > npm : Impossible de charger le fichier C:\Program Files\nodejs\npm.ps1, car 
l’exécution de scripts est désactivée sur ce système. Pour plus d’informations, 
consultez about_Execution_Policies à l’adresse 
https://go.microsoft.com/fwlink/?LinkID=135170.
Au caractère Ligne:1 : 1
+ npm install -D tailwindcss
+ ~~~
    + CategoryInfo          : Erreur de sécurité : (:) [], PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess

### SOLUTION
Vérifier la politique d'exécution 
Get-ExecutionPolicy

Set-ExecutionPolicy RemoteSigned (plus sécurisé)

OU

Set-ExecutionPolicy Unrestricted (pour tous les fichiers)

Des fois, même si on est en Unrestricted par défaut c'est bien de faire un reset

### AUTRES ERREURS
Changer les éléments de package.json
Rebuild la compilation
