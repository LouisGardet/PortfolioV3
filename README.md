# PortfolioV3

Bienvenue sur mon portfolio pour le BTS SIO.

## Installation et configuration

### Installation des dépendances

Pour installer les dépendances nécessaires, exécutez la commande suivante dans votre CLI :

```bash
npm install -D tailwindcss autoprefixer postcss
```
Pas obligé de mettre l'autoprefixer postcss, ça sert à la rétrocompatibilité des navigateurs.

### Initialisation de Tailwind

Pour initialiser TailwindCSS avec un fichier de configuration, utilisez :
```bash
npx tailwindcss init
```
Ce fichier peut être modifié pour personnaliser votre configuration Tailwind.

## Configuration


### Tailwind.config.js
Votre configuration Tailwind devrait ressembler à ceci :

```bash
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
```

### Package.json
```bash
{
  "name": "portfolio",
  "version": "1.0.0",
  "main": "index.js",
  "scripts": {
    "build:css": "npx tailwindcss -i tailwind.css -o src/assets/css/style.css --watch"
  },
  "dependencies": {
    "autoprefixer": "^10.4.0",
    "postcss": "^8.4.5",
    "tailwindcss": "^3.0.0"
  }
}
```

## Input.css

Créer un fichier input.css dans le dossier src/css

```bash
@tailwind base; /_ La directive base permet de faire un reset css _/
@tailwind components;/_ components autorise la création de nouveaux composants afin de les réutiliser _/
@tailwind utilities;/_ contient tous les utilitaires _/
```

### Compilation CSS

```bash
npx tailwindcss -i tailwind.css -o src/assets/css/style.css --watch
```
Changer le nom de dossier d'output et sa destination si vous suivez d'autres normes que les miennes.

### Intégration dans HTML

```bash
<link rel="stylesheet" href="./dist/css/style.css">
```

## Résolution des problèmes courants

### Problèmes de Permissions

Si vous rencontrez des problèmes de permissions lors de l’exécution des commandes Tailwind, vous pouvez essayer de modifier les permissions du fichier :

```bash
chmod +x /chemin/vers/le/fichier
```

Si le problème persiste, envisagez d’utiliser sudo :

```bash
npx tailwindcss -i tailwind.css -o src/assets/css/style.css --watch
```

### Mise à jour de Browserslist

Pour assurer la compatibilité avec les navigateurs les plus récents, mettez à jour votre base de données Browserslist :

```bash
npx update-browserslist-db@latest
```
## Méthodologie d'analyse et de résolution des erreurs

1. Problèmes de Configuration Initiale
Manque de fichiers de configuration

    Erreur : Fichiers tailwind.config.js ou postcss.config.js manquants ou mal configurés.

    Solution : Assurez-vous de générer les fichiers de configuration nécessaires en suivant la documentation officielle de TailwindCSS.

    ```bash 
    npx tailwindcss init
    ```


Exemple de tailwind.config.js :

javascript
```bash
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
```
Exemple de postcss.config.js :
```bash
javascript

    module.exports = {
      plugins: {
        tailwindcss: {},
        autoprefixer: {},
      }
    }
```

2. Problèmes de Chemins de Fichiers
Chemins incorrects dans les commandes ou les fichiers de configuration

    Erreur : Les fichiers CSS ou HTML ne sont pas trouvés car les chemins spécifiés sont incorrects.

    Solution : Vérifiez que les chemins spécifiés dans les fichiers de configuration et les commandes sont corrects.

    ```bash

    npx tailwindcss -i tailwind.css -o src/assets/css/style.css --watch
    ```

    Assurez-vous que le fichier input.css existe à l'emplacement spécifié (./src/input.css).

3. Problèmes de Paquets et de Dépendances
Dépendances manquantes ou incompatibles

    Erreur : Problèmes avec les paquets npm comme tailwindcss, postcss, ou autoprefixer.

    Solution : Assurez-vous d'avoir installé toutes les dépendances nécessaires et compatibles.

    ```bash

    npm install tailwindcss postcss autoprefixer
    ```
    Vérifiez les versions dans package.json pour vous assurer qu'elles sont compatibles.

4. Problèmes de Génération de Fichier CSS
Le fichier CSS n'est pas généré ou n'est pas mis à jour

    Erreur : Le fichier CSS n'est pas généré ou les modifications ne sont pas reflétées.

    Solution : Assurez-vous d'exécuter les commandes de build correctement et de vérifier que le mode --watch fonctionne.

    ```bash

npm run build:css
```

ou

```bash

    npx tailwindcss -i tailwind.css -o src/assets/css/style.css --watch
```

5. Problèmes de Chemins Relatifs dans le HTML
Le chemin du fichier CSS dans le fichier HTML est incorrect

    Erreur : Les styles ne sont pas appliqués parce que le chemin du fichier CSS dans le fichier HTML est incorrect.

    Solution : Assurez-vous que le chemin relatif dans la balise <link> est correct.

    Exemple :

    html

    ```bash
    <link href="/dist/css/style.css" rel="stylesheet">
    ```
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


8. Le powershell renvoie > npm : Impossible de charger le fichier C:\Program Files\nodejs\npm.ps1, car 
    l’exécution de scripts est désactivée sur ce système. Pour plus d’informations, 
    consultez about_Execution_Policies à l’adresse 
    https://go.microsoft.com/fwlink/?LinkID=135170.
  Au caractère Ligne:1 : 1
    + npm install -D tailwindcss
    + ~~~
      + CategoryInfo          : Erreur de sécurité : (:) [], PSSecurityException
      + FullyQualifiedErrorId : UnauthorizedAccess

  # Vérifier la politique d'exécution 
    Get-ExecutionPolicy

    Set-ExecutionPolicy RemoteSigned (plus sécurisé)

    OU

    Set-ExecutionPolicy Unrestricted (pour tous les fichiers)

    Des fois, même si on est en Unrestricted par défaut c'est bien de faire un reset



## Ajouts dans le gitignore

Pas obligé d'en mettre autant. Ce sont les fichiers qu'on ne veut en général pas suivre dans git et ça dépend de votre configuration.
J'ai un doute sur ma config, gitignore n'est pas intégré de base dans VsCode et je crois que ça ne marche pas très bien. Je fixerai ça plus tard si j'y pense

# Node.js
node_modules/
npm-debug.log*
yarn-debug.log*
yarn-error.log*

# Logs
logs/
*.log
npm-debug.log*
yarn-debug.log*
yarn-error.log*

# Runtime data
pids/
*.pid
*.seed
*.pid.lock

# Directory for instrumented libs generated by jscoverage/JSCover
lib-cov/

# Coverage directory used by tools like istanbul
coverage/

# nyc test coverage
.nyc_output/

# Grunt intermediate storage (http://gruntjs.com/creating-plugins#storing-task-files)
.grunt/

# Bower dependency directory (https://bower.io/)
bower_components/

# Typescript v1 declaration files
typings/

# Optional npm cache directory
.npm/

# Optional eslint cache
.eslintcache

# Optional REPL history
.node_repl_history

# Output of 'npm pack'
*.tgz

# Yarn Integrity file
.yarn-integrity

# dotenv environment variables file
.env

# Tailwind CSS output (if you are generating a CSS file)
dist/
public/

# MacOS files
.DS_Store

# Visual Studio Code files
.vscode/

# IDE specific files (JetBrains, IntelliJ IDEA, etc.)
.idea/

# SASS cache
.sass-cache/

# Compiled source
lib/
lib-esm/
lib-umd/

# Coverage output
coverage/

# Firebase cache
.firebase/
