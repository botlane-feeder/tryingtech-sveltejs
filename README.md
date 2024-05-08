# TryingTech - SvelteJS

SvelteJS est un framework JS, qui permet de gérer les vues d'une application web.
L'intérêt et l'avantage de Svelte, c'est qu'il est simple et ne fait que créer des fichiers JS et CSS optimisés à partir des fichiers et composants Svelte.

## Initialisation du projet

Dans un premier temps, il faut créer le projet Vue-JS.  
Il y a deux options.
- Soit en installant NPM et Vue sur sa machine. Puis lancer la création du projet par VueJS.
- Soit faire ce processus, on utilisant uniquement un conteneur et en partageant le volume.

L'avantage d'utiliser Docker est l'isolation complète de votre machine, en utilisant que des conteneurs.  
L'inconvénient est la sur-utilisation de Docker et la travail supplémentaire de ne pas utiliser le terminal simplement, mais de créer un script Dockerfile pour le faire.

### Prerequis

- Docker
- NPM
- VueJS

Installation de Docker :  
Il faudra quoiqu'il arrive installer Docker. C'est un effort initial que de l'utiliser, mais cela permettra de gagner beaucoup de temps dans toutes les étapes de mise en production.
Pour cela, le mieux est de passer par le script de Docker que l'on retrouve dans sa propre documentation : 
- [Documentation Docker](https://docs.docker.com/engine/install/ubuntu/)


Installation de NPM :  
La procédure actuelle est d'installer NVM (node version manager), puis d'installer NodeJS (appelé Node), qui installera également NPM
Pour cela, le mieux est de passer par la documentation de NPM :
- [Documentation NPM](https://nodejs.org/en/download/package-manager)

Installation de SvelteJS :  
L'installation de SvelteJS, se fait en utilisant l'utilitaire NPM qui installe les dépendences Node
Pour cela, la voix classique de l'utilisation de NPM est le code suivant :
- `npm install svelte` : [Documentation Svelte](https://svelte.dev/docs/introduction)
Une fois cette ligne executée, SvelteKit est diponible sur le PC de manière à créer une application svelte.

### Création d'un projet

*Si Svelte n'est pas installé sur la machine, en créeant un projet avec `npm`, l'utilitaire vous proposera d'installer `create-svelte`*.

Pour créer un projet SvelteJS installer `npm create svelte@latest ${appName}`

Lors de la création d'un projet Svelte, vous avez 3 possibilités :
- SvelteKit demo app : une application de démo
- Skeleton project : juste ce qu'il faut pour pouvoir monter un application web SvelteJS
- Library project : juste ce qu'il faut pour pouvoir créer un "module" Svelte ?

**Attention**, la particularité avec le SvelteKit, c'est qu'il doit s'installer en tout premier niveau (toplevel) dans votre projet et propose déjà des documents GIT de base comme  : 
- README
- .gitignore
Il faut créer l'application avant le projet GIT pour éviter que Svelte ecrase ces fichiers.

Commençons par l'application démo :

#### L'achitecture de base

Plus de détails sur l'achitecture dans la [documentation](https://kit.svelte.dev/docs/project-structure)

├── package.json  
├── README.md  
├── src  
│   ├── app.d.ts  
│   ├── app.html  
│   ├── lib  
│   │   └── index.ts  
│   └── routes  
│       └── +page.svelte  
├── static  
│   └── favicon.png  
├── svelte.config.js  
├── tsconfig.json  
└── vite.config.ts  

Ce qu'il y a à retenir :
- `src/` : on retrouvera le code source pour notre développement
- `src/lib/` : on retrouvera des composants importés
- `src/routes/` : on retrouvera le routing, ainsi que nos composants pour l'application en cours de développement.
- `src/app.html` : ici que tout commence, le template général de l'application


#### Les options

On va choisir le 
- une syntaxe typescript, pour avoir une meilleure gestion JS
- additionnellement, on peut choisir des modules qui seront ajoutés dans le package.json, mais qu'on peut ajouter ensuite
  - Add ESLint for code linting
  - Add Prettier for code formatting
  - Add Playwright for browser testing
  - Add Vitest for unit testing
  - Try the Svelte 5 preview (unstable!)


#### Lancement de l'application

Les explications sont très claires dans le README.md généré par Svelte.

Une fois dans le bon dossier, 
- on installe les dépendances : `npm install`
- puis on lance `npm run dev`

Il ne reste plus qu'à aller sur le port indiqué pour ouvrir l'application demo.

## Parlons de SvelteKit

Svelte est une manière de développer, proposant son architecture, sa construction des composants et compilant les fichiers .svelte en fichiers .js .css.

SvelteKit est une évolution de Sapper, qui était le framework officiel pour le développement d'applications Svelte.  
SvelteKit est connnu pour simplifier et améliorer le processus de développement des applications Web avec Svelte.  
Il fournit une architecture plus flexible et plus moderne, ainsi qu'une prise en charge améliorée des fonctionnalités telles que le routage, le rendu côté serveur (SSR), la génération de pages statiques (SSG), et les API routables.  
SvelteKit facilite également le déploiement d'applications Svelte en prenant en charge plusieurs options de serveur et de plateformes de déploiement.

## La base d'une application SvelteJS

Dans la documentation de SvelteJS, il existe un [tutoriel](https://learn.svelte.dev/tutorial/welcome-to-svelte).  
Ce tutoriel reprend la base pour créer une application et surtout me place un bac à sable qui permet d'avoir un environnement en ligne tester et s'entrainer tout en étant guidé.
Cet tutoriel s'appuie sur un REPL (Read–eval–print loop) pour permettre un environnement bac à sable.

SvelteKit étant le framework pour développer, on s'intéressera d'abord à étudier sa documentation pour développer notre première application.  
Puis dans un second on poussera notre connaissance sur Svelte pour mieux maitriser la syntaxe Svelte et l'écriture des composants.

Comme expliqué plus haut, une fois le projet créé et les dépendances installées (`npm install`), vous pouvez lancer le projet (une fois dans le bon dossier) : `npm run dev`

### Maitrisons la création d'une application avec SvelteKit

Notre premier pas arrive sur 2 piliers de ce framework : 
- Chaque page de notre application est un composant Svelte
- Pour créer une page, il faut ajouter un fichier dans le dossier `src/routes/`

### Créer un composant d'après Svelte

Un composant Svelte est composé de 3 parties, comme tous les frameworks JS récents :
- une partie Script
- une partie DOM
- une partie Style

La partie script sera la partie dynamique, JS et ne sera appliqué uniquement sur le spectre du composant.  
La partie DOM sera l'ensemble des balises en utilisant le script et le style.  
La partie Style sera la partie graphique, CSS ne sera appliquée que sur le spectre du composant.  

### L'architecture de notre application


***TODO***
- Faire une interface graphique d'exemple : 
  - Un tableau de tâche
  - un (+) qui crée une tâche
  - au clic d'une tâche on édite la tâche et son contenu
  - un drag&drop de la tâche
- Comment faire un composant ?
  - La composition
  - Les bonnes pratiques
  - Faire du jolie
- Comment faire une interface
  - L'arborecense d'une interface
  - L'architecture des composants d'une interface