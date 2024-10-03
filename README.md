# Pokemon Project

Cette application a étè créer en [Angular CLI](https://github.com/angular/angular-cli) version 18.2.5.

## Création du projet avec la commande suivante : 
```
ng new pokemon --routing --style=scss
```
## Installation de tailwind en deux étapes avec les commandes suivantes : 
```
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init
```
## Configuration du tailwind dans le fichier tailwind.config.js comme ceci : 
``` java script
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    "./src/**/*.{html,ts}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```
## Configuration du fichier styles.sccs comme ceci : 
``` java script
@tailwind base;
@tailwind components;
@tailwind utilities;
```
## Configuration du fichier tsconfig.json comme ceci : 
``` java script
/* To learn more about this file see: https://angular.io/config/tsconfig. */
{
  "compileOnSave": false,
  "compilerOptions": {
    "outDir": "./dist/out-tsc",
    "forceConsistentCasingInFileNames": true,
    "noImplicitOverride": true,
    "noPropertyAccessFromIndexSignature": true,
    "noImplicitReturns": true,
    "noFallthroughCasesInSwitch": true,
    "esModuleInterop": true,
    "sourceMap": true,
    "declaration": false,
    "experimentalDecorators": true,
    "moduleResolution": "node",
    "importHelpers": true,
    "target": "ES2022",
    "module": "ES2022",
    "useDefineForClassFields": false,
    "lib": ["ES2022", "dom"],
    "noUnusedLocals": true,
    "noUnusedParameters": true
  },
  "angularCompilerOptions": {
    "enableI18nLegacyMessageIdFormat": false,
    "strictInjectionParameters": true,
    "strictInputAccessModifiers": true,
    "strictTemplates": true
  }
}
```
## génerer un dossier avec component'auth' services/auth/auth avec la commande suivante : 
```
ng g s services/auth/auth
```
### Important ! 
A chaque fois qu'on veut génerer un nouveau service dans le dossier services on utilise la commande suivante : 
```
ng g s services/../..
```
### Petite explication : 
Un service est une classe qui contient de la logique de traitement de données, des appels à des APIs, ou tout autre code qui n'est pas directement lié à l'interface utilisateur.

## Création des composants avec les commandes suivantes : 
```
ng generate component ou ng g c
```
+ /pages/login :
  ```
  ng g c pages/login
  ```
+ /pages/home :
  ```
  ng g c pages/home
  ```
+ /components/login-form
  ```
  ng g c /components/login-form
  ```
+ /components/pokemon-card
  ```
  ng g c /components/pokemon-card
  ```
### Petite explication : 
La commande ng g c (ou ng generate component) est utilisée pour générer un composant Angular. Un composant est une partie de l'interface utilisateur (UI) dans une application Angular. Chaque composant a une logique associée (un fichier TypeScript), un modèle (HTML), et des styles (CSS).
## Les fichiers " app.component.ts ", " app.component.html " :
### 1 Dans le fichier " app.component.ts ", j'ai supprimer le 'title' 
### 2 Dans le fichier " app.component.html ", j'ai supprimer tout le code qui a éte mis en place automatiquement par 'angular'
### Petite explication : 
Ces deux fichiers je les considére comme les composants parents principaux ou la base de l'application angular. 
 + Le fichier app.component.ts est la classe TypeScript du composant racine,Ce composant parent va généralement contenir l'ensemble des composants enfants.
 + Le fichier app.component.html est le template associé à app.component.ts, Le template contient l'interface utilisateur de base, comme le header, le footer, une navigation, et il intègre des composants enfants via leurs sélecteurs personnalisés.
##
Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The application will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via a platform of your choice. To use this command, you need to first add a package that implements end-to-end testing capabilities.

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI Overview and Command Reference](https://angular.dev/tools/cli) page.
