# PortfolioV3

Bienvenue sur mon portfolio pour le BTS SIO

######### INSTALLATION ET CONFIG DES DOSSIERS

npm install-D tailwindcss
npx tailwindcdd init

## Go to > tail.config.js >>>>> content: ["./src/**/*.{html,js}l"],

Pour que tailwind scanne tous les fichiers ayant la temrinaison voulue, ici .html et js

@tailwind base; /_ La directive base permet de faire un reset css _/
@tailwind components;/_ components autorise la création de nouveaux composants afin de les réutiliser _/
@tailwind utilities;/_ contient tous les utilitaires _/

######### COMPILATION

npx tailwindcss -i ./src/input.css -o ./public/style.css --watch  <!-- Vérifier que le fichier que l'on veut scope soit bien défini dans le chemin, ici ./src/input n'est pas bon dans ma config, j'utilise ./src/css (j'ai changé pour plus d'homogénéité dans le code) -->
-i = analyse input -o = analyse fichier output --watch permet de loop la commande a chaque enregistrement

## Go to > index.html

Ajouter l'ancre CSS

<link rel="stylesheet" href="style.css">

S'assurer que la balise h1 a une taille réduite = on sait que tailwind a effectué un reset des propriétés par défaut du HTML

# ERREURS POSSIBLES
Le powershell renvoie > npm : Impossible de charger le fichier C:\Program Files\nodejs\npm.ps1, car 
l’exécution de scripts est désactivée sur ce système. Pour plus d’informations, 
consultez about_Execution_Policies à l’adresse 
https://go.microsoft.com/fwlink/?LinkID=135170.
Au caractère Ligne:1 : 1
+ npm install -D tailwindcss
+ ~~~
    + CategoryInfo          : Erreur de sécurité : (:) [], PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess

## SOLUTION
Vérifier la politique d'exécution 
Get-ExecutionPolicy

Set-ExecutionPolicy RemoteSigned (plus sécurisé)

OU

Set-ExecutionPolicy Unrestricted (pour tous les fichiers)

Des fois, même si on est en Unrestricted par défaut c'est bien de faire un reset

# AUTRES ERREURS
Changer les éléments de package.json
Rebuild la compilation
