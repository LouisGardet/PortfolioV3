# PortfolioV3

Bienvenue sur mon portfolio pour le BTS SIO

######### INSTALLATION ET CONFIG DES DOSSIERS

npm install-D tailwindcss
npxtailwindcdd init

## Go to > tail.config.js >>>>> content: ["./src/**/*.{html,js}l"],
Pour que tailwind scanne tous les fichiers ayant la temrinaison voulue, ici .html et js

@tailwind base; /* La directive base permet de faire un reset css */
@tailwind components;/* components autorise la création de nouveaux composants afin de les réutiliser */
@tailwind utilities;/* contient tous les utilitaires */


######### COMPILATION

npx tailwindcss -i ./src/input.css -o ./public/style.css --watch
-i = analyse input -o = analyse fichier output --watch permet de loop la commande a chaque enregistrement

## Go to > index.html
Ajouter l'ancre CSS
<link rel="stylesheet" href="style.css">


S'assurer que la balise h1 a une taille réduite = on sait que tailwind a effectué un reset des propriétés par défaut du HTML
