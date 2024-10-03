# Pokemon Angular Project

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
#### 1 Dans le fichier " app.component.ts ", j'ai supprimer le 'title' 
#### 2 Dans le fichier " app.component.html ", j'ai supprimer tout le code qui a éte mis en place automatiquement par 'angular' car je vais mettre mon propre code de base, j'ai importer ceci <router-outlet> </router-outlet>
  ``` html
  <router-outlet> </router-outlet>
  <!-- <router-outlet> est une balise Angular qui sert de conteneur pour afficher dynamiquement les composants en fonction de la route (URL) active. Lorsque l'utilisateur navigue entre différentes pages, Angular injecte le composant correspondant à l'intérieur de <router-outlet>. Il est généralement placé dans app.component.html pour gérer la navigation entre les pages tout en maintenant des éléments fixes comme un header ou un footer. -->
</html>
```
### Petite explication : 
Ces deux fichiers je les considére comme les composants parents principaux ou la base de l'application angular. 
 + Le fichier app.component.ts est la classe TypeScript du composant racine,Ce composant parent va généralement contenir l'ensemble des composants enfants.
 + Le fichier app.component.html est le template associé à app.component.ts, Le template contient l'interface utilisateur de base, comme le header, le footer, une navigation, et il intègre des composants enfants via leurs sélecteurs personnalisés donc Le fichier contient la structure générale.

## Dans le fichier "app.routes.ts" j'ai importer les routes comme ceci : 
```
import { Routes } from '@angular/router';
import { HomeComponent } from './pages/home/home.component';
import { LoginComponent } from './pages/login/login.component';
import { authGuard } from './guards/auth/auth.guard';

export const routes: Routes = [
    {path: '',canActivate:[authGuard],component: HomeComponent}, 

    {path:'connexion',component:LoginComponent},
    {path: '**', redirectTo:''}

];
```
## Dans le fichier "app.component.html" j'ai mis le router dans une <div class= "container" , ce qui va me permettre d'avoir tout le 'contenu' de ma page dans un 'container' comme ceci : 
``` html
<div class=" container mx-auto h-full"> 
<router-outlet></router-outlet>
</div>
```
