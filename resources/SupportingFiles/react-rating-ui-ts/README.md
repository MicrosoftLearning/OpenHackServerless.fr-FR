---
ms.openlocfilehash: b8fb61f78cffb27cea5f313a39494fc0dfcdf7b3
ms.sourcegitcommit: 27a4afc732f8733e6022af2a58d01af5ae83545b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2022
ms.locfileid: "140813654"
---
Ce projet a été amorcé avec [Create React App](https://github.com/facebookincubator/create-react-app).

Vous trouverez ci-dessous des informations sur la façon d’effectuer des tâches courantes.<br>
Vous trouverez la version la plus récente de ce guide [ici](https://github.com/facebookincubator/create-react-app/blob/master/packages/react-scripts/template/README.md).

## <a name="table-of-contents"></a>Sommaire

- [Mise à jour vers les nouvelles versions](#updating-to-new-releases)
- [Envoi de commentaires](#sending-feedback)
- [Structure de dossiers](#folder-structure)
- [Scripts disponibles](#available-scripts)
  - [npm start](#npm-start)
  - [npm test](#npm-test)
  - [npm run build](#npm-run-build)
  - [npm run eject](#npm-run-eject)
- [Navigateurs pris en charge](#supported-browsers)
- [Polyfills et fonctionnalités de langage pris en charge](#supported-language-features-and-polyfills)
- [Mise en surbrillance de la syntaxe dans l’éditeur](#syntax-highlighting-in-the-editor)
- [Affichage de sortie Lint dans l’éditeur](#displaying-lint-output-in-the-editor)
- [Débogage dans l’éditeur](#debugging-in-the-editor)
- [Mise en forme automatique du code](#formatting-code-automatically)
- [Modification de la page `<title>`](#changing-the-page-title)
- [Installation d’une dépendance](#installing-a-dependency)
- [Importation d’un composant](#importing-a-component)
- [Fractionnement du code](#code-splitting)
- [Ajout d’une feuille de style](#adding-a-stylesheet)
- [Post-traitement CSS](#post-processing-css)
- [Ajout d’un préprocesseur CSS (Sass, Less, etc.)](#adding-a-css-preprocessor-sass-less-etc)
- [Ajout d’images, de polices et de fichiers](#adding-images-fonts-and-files)
- [Utilisation du dossier `public`](#using-the-public-folder)
  - [Modification du code HTML](#changing-the-html)
  - [Ajout de ressources en dehors du système de module](#adding-assets-outside-of-the-module-system)
  - [Quand utiliser le dossier `public`](#when-to-use-the-public-folder)
- [Utilisation de variables globales](#using-global-variables)
- [Ajout de Bootstrap](#adding-bootstrap)
  - [Utilisation d’un thème personnalisé](#using-a-custom-theme)
- [Ajout d’un flux](#adding-flow)
- [Ajout d’un routeur](#adding-a-router)
- [Ajout de variables d’environnement personnalisées](#adding-custom-environment-variables)
  - [Référencement des variables d’environnement dans le code HTML](#referencing-environment-variables-in-the-html)
  - [Ajout de variables d’environnement temporaires dans votre interpréteur de commandes](#adding-temporary-environment-variables-in-your-shell)
  - [Ajout de variables d’environnement de développement dans `.env`](#adding-development-environment-variables-in-env)
- [Puis-je utiliser des éléments décoratifs ?](#can-i-use-decorators)
- [Récupération de données avec des demandes AJAX](#fetching-data-with-ajax-requests)
- [Intégration avec un backend d’API](#integrating-with-an-api-backend)
  - [Nœud](#node)
  - [Ruby on rails](#ruby-on-rails)
- [Envoi par proxy de demandes d’API en développement](#proxying-api-requests-in-development)
  - [Erreurs d’en-tête d’hôte non valide après la configuration du proxy](#invalid-host-header-errors-after-configuring-proxy)
  - [Configuration manuelle du proxy](#configuring-the-proxy-manually)
  - [Configuration d’un proxy WebSocket](#configuring-a-websocket-proxy)
- [Utilisation du protocole HTTPS dans le développement](#using-https-in-development)
- [Génération de balises dynamiques `<meta>` sur le serveur](#generating-dynamic-meta-tags-on-the-server)
- [Prérendu dans des fichiers HTML statiques](#pre-rendering-into-static-html-files)
- [Injection de données à partir du serveur dans la page](#injecting-data-from-the-server-into-the-page)
- [Exécution de tests](#running-tests)
  - [Conventions de nom de fichier](#filename-conventions)
  - [Interface de ligne de commande](#command-line-interface)
  - [Intégration de la gestion de version](#version-control-integration)
  - [Écriture des tests](#writing-tests)
  - [Test des composants](#testing-components)
  - [Utilisation de bibliothèques d’assertion tierces](#using-third-party-assertion-libraries)
  - [Initialisation de l’environnement de test](#initializing-test-environment)
  - [Focus et exclusion de tests](#focusing-and-excluding-tests)
  - [Rapports de couverture](#coverage-reporting)
  - [Intégration continue](#continuous-integration)
  - [Désactivation de jsdom](#disabling-jsdom)
  - [Test d’instantané](#snapshot-testing)
  - [Intégration de l’éditeur](#editor-integration)
- [Débogage des tests](#debugging-tests)
  - [Débogage de tests dans Chrome](#debugging-tests-in-chrome)
  - [Débogage de tests dans Visual Studio Code](#debugging-tests-in-visual-studio-code)
- [Développement de composants dans Isolation](#developing-components-in-isolation)
  - [Prise en main de Storybook](#getting-started-with-storybook)
  - [Prise en main de Styleguidist](#getting-started-with-styleguidist)
- [Publication de composants sur npm](#publishing-components-to-npm)
- [Création d’une application web progressive](#making-a-progressive-web-app)
  - [Désactivation de la mise en cache](#opting-out-of-caching)
  - [Considérations relatives au « hors ligne avant tout »](#offline-first-considerations)
  - [Métadonnées de l’application web progressive](#progressive-web-app-metadata)
- [Analyse de la taille du bundle](#analyzing-the-bundle-size)
- [Déploiement](#deployment)
  - [Serveur statique](#static-server)
  - [Autres solutions](#other-solutions)
  - [Gérer des applications avec le routage côté client](#serving-apps-with-client-side-routing)
  - [Génération de chemins d’accès relatifs](#building-for-relative-paths)
  - [Microsoft Azure](#azure)
  - [Firebase](#firebase)
  - [GitHub Pages](#github-pages)
  - [Heroku](#heroku)
  - [Netlify](#netlify)
  - [Now](#now)
  - [S3 et CloudFront](#s3-and-cloudfront)
  - [Surge](#surge)
- [Configuration avancée](#advanced-configuration)
- [Dépannage](#troubleshooting)
  - [`npm start` ne détecte pas les modifications](#npm-start-doesnt-detect-changes)
  - [ `npm test` se bloque sur macOS Sierra](#npm-test-hangs-on-macos-sierra)
  - [ `npm run build` s’arrête trop tôt](#npm-run-build-exits-too-early)
  - [ `npm run build` échoue sur Heroku](#npm-run-build-fails-on-heroku)
  - [ `npm run build` ne peut pas minifier](#npm-run-build-fails-to-minify)
  - [Des paramètres régionaux Moment.js sont manquants](#momentjs-locales-are-missing)
- [Alternatives à l’éjection](#alternatives-to-ejecting)
- [Des éléments sont manquants ?](#something-missing)

## <a name="updating-to-new-releases"></a>Mise à jour vers les nouvelles versions

Create React App est divisée en deux packages :

* `create-react-app` est un utilitaire de ligne de commande global que vous utilisez pour créer des projets.
* `react-scripts` est une dépendance de développement dans les projets générés (y compris celui-ci).

Vous n’avez presque jamais besoin de la mise à jour `create-react-app` elle-même : elle délègue toute la configuration à `react-scripts`.

Lorsque vous exécutez `create-react-app`, il crée toujours le projet avec la dernière version de `react-scripts` afin que vous obteniez toutes les nouvelles fonctionnalités et améliorations apportées automatiquement aux applications nouvellement créées.

Pour mettre à jour un projet existant vers une nouvelle version de `react-scripts`, [ouvrez journal des modifications](https://github.com/facebookincubator/create-react-app/blob/master/CHANGELOG.md), recherchez la version dans laquelle vous êtes actuellement (archivez `package.json` dans ce dossier si vous n’en êtes pas sûr) et appliquez les instructions de migration pour les versions plus récentes.

Dans la plupart des cas, la version `react-scripts` dans `package.json` et exécutant `npm install` dans ce dossier devrait suffire, mais il est judicieux de consulter le [journal des modifications](https://github.com/facebookincubator/create-react-app/blob/master/CHANGELOG.md) pour connaître les modifications avec rupture potentielles.

Nous nous engageons à avoir un nombre minimal de modifications avec rupture afin de pouvoir mettre à niveau `react-scripts` facilement.

## <a name="sending-feedback"></a>Envoi de commentaires

Nous apprécions toujours de recevoir [vos commentaires](https://github.com/facebookincubator/create-react-app/issues).

## <a name="folder-structure"></a>Structure des dossiers

Après la création, votre projet doit ressembler à ceci :

```
my-app/
  README.md
  node_modules/
  package.json
  public/
    index.html
    favicon.ico
  src/
    App.css
    App.js
    App.test.js
    index.css
    index.js
    logo.svg
```

Pour que le projet soit généré, **ces fichiers doivent exister avec des noms de fichiers exacts** :

* `public/index.html` est le modèle de page.
* `src/index.js` est le point d’entrée JavaScript.

Vous pouvez supprimer ou renommer les autres fichiers.

Vous pouvez créer des sous-répertoires dans `src`. Pour accélérer les régénérations, seuls les fichiers à l’intérieur de `src` sont traités par WebPack.<br>
Vous devez **placer les fichiers JS et CSS dans `src`** . Sinon, WebPack ne les verra pas.

Seuls les fichiers à l’intérieur de `public` peuvent être utilisés à partir de `public/index.html`.<br>
Lisez les instructions ci-dessous pour utiliser les ressources à partir de JavaScript et HTML.

Toutefois, vous pouvez créer davantage de répertoires de premier niveau.<br>
Ils ne seront pas inclus dans la génération de production afin que vous puissiez les utiliser pour des tâches telles que la documentation.

## <a name="available-scripts"></a>Scripts disponibles

Dans le répertoire du projet, vous pouvez exécuter :

### `npm start`

Exécute l’application en mode de développement.<br>
Ouvrez [http://localhost:3000](http://localhost:3000) pour l’afficher dans le navigateur.

La page se recharge si vous apportez des modifications.<br>
Vous verrez également toutes les erreurs lint dans la console.

### `npm test`

Lance la série de tests en mode espion interactif.<br>
Pour plus d’informations, consultez la section relative à l’[exécution des tests](#running-tests).

### `npm run build`

Génère l’application pour la production dans le dossier `build`.<br>
Regroupe correctement React en mode production et optimise la génération pour des performances optimales.

La build est minifiée et les noms de fichiers incluent les barres obliques.<br>
Votre application est prête à être déployée.

Pour plus d’informations, consultez la section relative au [déploiement](#deployment).

### `npm run eject`

**Remarque : il s’agit d’une opération unidirectionnelle. Une fois que vous `eject`, vous ne pouvez plus revenir en arrière.**

Si vous n’êtes pas satisfait de l’outil de génération et des choix de configuration, vous pouvez `eject` à tout moment. Cette commande supprime la seule dépendance de génération de votre projet.

Au lieu de cela, elle copie tous les fichiers de configuration et les dépendances transitives (WebPack, Babel, ESLint, etc.) directement dans votre projet afin que vous ayez un contrôle total sur ces fichiers. Toutes les commandes à l’exception de `eject` continuent de fonctionner, mais elles pointent vers les scripts copiés pour vous permettre de les modifier. À ce stade, vous volez de vos propres ailes.

Vous ne devez pas du tout utiliser `eject`. L’ensemble de fonctionnalités organisé est adapté aux déploiements de petite et moyenne taille, et vous ne devez pas vous sentir obligé d’utiliser cette fonctionnalité. Toutefois, nous savons que cet outil n’est pas utile si vous ne pouvez pas le personnaliser lorsque vous êtes prêt.

## <a name="supported-browsers"></a>Navigateurs pris en charge

Par défaut, le projet généré utilise la version la plus récente de React.

Vous pouvez consulter la [documentation de React](https://reactjs.org/docs/react-dom.html#browser-support) pour plus d’informations sur les navigateurs pris en charge.

## <a name="supported-language-features-and-polyfills"></a>Polyfills et fonctionnalités de langage pris en charge

Ce projet prend en charge un sur-ensemble de la norme JavaScript la plus récente.<br>
Outre les fonctionnalités de syntaxe [ES6](https://github.com/lukehoban/es6features), il prend également en charge :

* [Opérateur d’exponentiation](https://github.com/rwaldron/exponentiation-operator) (ES2016).
* [Async/await](https://github.com/tc39/ecmascript-asyncawait) (ES2017).
* [Propriétés Rest/Spread de l’objet](https://github.com/sebmarkbage/ecmascript-rest-spread) (proposition de 3e niveau).
* [Importation dynamique()](https://github.com/tc39/proposal-dynamic-import) (proposition de 3e niveau)
* [Champs de classe et propriétés statiques](https://github.com/tc39/proposal-class-public-fields) (proposition de 2e niveau).
* Syntaxe [JSX](https://facebook.github.io/react/docs/introducing-jsx.html) et [Flow](https://flowtype.org/).

Découvrez les [différentes étapes de la proposition](https://babeljs.io/docs/plugins/#presets-stage-x-experimental-presets-).

Bien que nous vous recommandions d’utiliser des propositions expérimentales avec prudence, Facebook utilise largement ces fonctionnalités dans le code du produit. Nous avons donc l’intention de fournir des [codemods](https://medium.com/@cpojer/effective-javascript-codemods-5a6686bb46fb) si l’une de ces propositions change à l’avenir.

Notez que **le projet n’inclut que quelques [polyfills](https://wikipedia.org/wiki/Polyfill) ES6** :

* [`Object.assign()`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object/assign) via [`object-assign`](https://github.com/sindresorhus/object-assign).
* [`Promise`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Promise) via [`promise`](https://github.com/then/promise).
* [`fetch()`](https://developer.mozilla.org/docs/Web/API/Fetch_API) via [`whatwg-fetch`](https://github.com/github/fetch).

Si vous utilisez d’autres fonctionnalités ES6+ qui nécessitent une **prise en charge du runtime** (telles que `Array.from()` ou `Symbol`), assurez-vous d’inclure manuellement les polyfills appropriés, ou que les navigateurs que vous ciblez les prennent déjà en charge.

Notez également qu’en utilisant des fonctionnalités de syntaxe plus récentes, comme `for...of` ou `[...nonArrayValue]`, Babel émet du code qui dépend des fonctionnalités du runtime ES6 et peut ne pas fonctionner sans polyfill. En cas de doute, utilisez [Babel REPL](https://babeljs.io/repl/) pour voir l’objet de la compilation d’une syntaxe spécifique.

## <a name="syntax-highlighting-in-the-editor"></a>Mise en surbrillance de la syntaxe dans l’éditeur

Pour configurer la mise en surbrillance de la syntaxe dans votre éditeur de texte favori, accédez à la [page de documentation Babel appropriée](https://babeljs.io/docs/editors) et suivez les instructions. Certains des éditeurs les plus populaires sont couverts.

## <a name="displaying-lint-output-in-the-editor"></a>Affichage de sortie Lint dans l’éditeur

>Remarque : cette fonctionnalité est disponible avec `react-scripts@0.2.0` et les versions ultérieures.<br>
>Elle fonctionne également uniquement avec npm 3 ou version ultérieure.

Certains éditeurs, y compris Sublime Text, Atom et Visual Studio Code, fournissent des plug-ins pour ESLint.

Ils ne sont pas requis pour le linting. Vous devez voir la sortie linter dans votre terminal, ainsi que la console du navigateur. Toutefois, si vous préférez que les résultats lint s’affichent directement dans votre éditeur, vous pouvez effectuer quelques étapes supplémentaires.

Vous devez d’abord installer un plug-in ESLint pour votre éditeur. Ensuite, ajoutez un fichier appelé `.eslintrc` à la racine du projet :

```js
{
  "extends": "react-app"
}
```

À présent, votre éditeur doit signaler les avertissements en lien avec le linting.

Notez que même si vous modifiez davantage votre fichier `.eslintrc`, ces modifications **affectent uniquement l’intégration de l’éditeur**. Elles n’affectent pas la sortie lint de terminal et au sein du navigateur. Cela est dû au fait que Create React App fournit intentionnellement un ensemble minimal de règles qui recherchent des erreurs courantes.

Si vous souhaitez appliquer un style de codage pour votre projet, envisagez d’utiliser [Prettier](https://github.com/jlongster/prettier) au lieu de règles de style ESLint.

## <a name="debugging-in-the-editor"></a>Débogage dans l’éditeur

**Actuellement, cette fonctionnalité est uniquement prise en charge par [Visual Studio Code](https://code.visualstudio.com) et [WebStorm](https://www.jetbrains.com/webstorm/).**

Visual Studio Code et WebStorm prennent en charge le débogage prêt à l’emploi avec Create React App. Cela vous permet, en tant que développeur, d’écrire et de déboguer votre code React sans quitter l’éditeur et, plus important encore, d’avoir un flux de travail de développement continu, où le changement de contexte est minime, car vous n’avez pas à basculer entre les différents outils.

### <a name="visual-studio-code"></a>Visual Studio Code

Vous devez installer la dernière version de [VS Code](https://code.visualstudio.com) et de l’[Extension de débogueur Chrome](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome) VS Code.

Ajoutez ensuite le bloc ci-dessous à votre fichier `launch.json` et placez-le à l’intérieur du dossier `.vscode` dans le répertoire racine de votre application.

```json
{
  "version": "0.2.0",
  "configurations": [{
    "name": "Chrome",
    "type": "chrome",
    "request": "launch",
    "url": "http://localhost:3000",
    "webRoot": "${workspaceRoot}/src",
    "userDataDir": "${workspaceRoot}/.vscode/chrome",
    "sourceMapPathOverrides": {
      "webpack:///src/*": "${webRoot}/*"
    }
  }]
}
```
>Remarque : l’URL peut être différente si vous avez effectué des ajustements via les [variables d’environnement HOST ou PORT](#advanced-configuration).

Démarrez votre application en exécutant `npm start`, puis démarrez le débogage dans VS Code en appuyant sur `F5` ou en cliquant sur l’icône de débogage verte. Vous pouvez maintenant écrire du code, définir des points d’arrêt, apporter des modifications au code et déboguer votre code récemment modifié, le tout à partir de votre éditeur.

### <a name="webstorm"></a>WebStorm

Vous devez avoir installé [WebStorm](https://www.jetbrains.com/webstorm/) et l’extension Chrome [JetBrains IDE Support](https://chrome.google.com/webstore/detail/jetbrains-ide-support/hmhgeddbohgjknpmjagkdomcpobmllji).

Dans le menu WebStorm `Run`, sélectionnez `Edit Configurations...`. Cliquez ensuite sur `+` et sélectionnez `JavaScript Debug`. Collez `http://localhost:3000` le champ URL et enregistrez la configuration.

>Remarque : l’URL peut être différente si vous avez effectué des ajustements via les [variables d’environnement HOST ou PORT](#advanced-configuration).

Démarrez votre application en exécutant `npm start`, puis appuyez sur `^D` sur macOS ou `F9` sur Windows et Linux, ou cliquez sur l’icône de débogage verte pour démarrer le débogage dans WebStorm.

De la même façon, vous pouvez déboguer votre application dans IntelliJ IDEA Ultimate, PhpStorm, PyCharm Pro et RubyMine. 

## <a name="formatting-code-automatically"></a>Mise en forme automatique du code

Prettier est un outil de mise en forme de code avec consignes strictes et prise en charge de JavaScript, CSS et JSON. Avec Prettier, vous pouvez mettre en forme le code que vous écrivez automatiquement pour garantir un style de code dans votre projet. Pour plus d’informations, consultez la [page GitHub sur Prettier](https://github.com/prettier/prettier) et regardez cette [page pour le voir en action](https://prettier.github.io/prettier/).

Pour mettre en forme notre code chaque fois que nous effectuons une validation dans Git, nous devons installer les dépendances suivantes :

```sh
npm install --save husky lint-staged prettier
```

Vous pouvez aussi utiliser `yarn` :

```sh
yarn add husky lint-staged prettier
```

* `husky` facilite l’utilisation de githooks comme s’il s’agissait de scripts npm.
* `lint-staged` nous permet d’exécuter des scripts sur des fichiers intermédiaires dans Git. Pour en savoir plus, consultez le [billet de blog. sur lint-stagesd](https://medium.com/@okonetchnikov/make-linting-great-again-f3890e1ad6b8).
* `prettier` est l’outil de mise en forme JavaScript que nous allons exécuter avant la validation.

À présent, nous pouvons vérifier que chaque fichier est mis en forme correctement en ajoutant quelques lignes au `package.json` dans la racine du projet.

Ajoutez la ligne suivante à la section `scripts` :

```diff
  "scripts": {
+   "precommit": "lint-staged",
    "start": "react-scripts start",
    "build": "react-scripts build",
```

Ensuite, nous ajoutons un champ « lint-staged » à `package.json`, par exemple :

```diff
  "dependencies": {
    // ...
  },
+ "lint-staged": {
+   "src/**/*.{js,jsx,json,css}": [
+     "prettier --single-quote --write",
+     "git add"
+   ]
+ },
  "scripts": {
```

Maintenant, chaque fois que vous effectuez une validation, Prettier met automatiquement en forme les fichiers modifiés. Vous pouvez également exécuter `./node_modules/.bin/prettier --single-quote --write "src/**/*.{js,jsx,json,css}"` pour mettre en forme votre projet entier pour la première fois.

Ensuite, vous souhaiterez peut-être intégrer Prettier dans votre éditeur favori. Lisez la section relative à l’intégration de l’[éditeur](https://prettier.io/docs/en/editors.html) sur la page GitHub sur Prettier.

## <a name="changing-the-page-title"></a>Modification de la page `<title>`

Vous pouvez trouver le fichier HTML source dans le dossier `public` du projet généré. vous pouvez modifier la balise `<title>` dans celui-ci pour remplacer le titre « React App » par un autre nom.

Notez que normalement, vous ne modifiez pas très souvent les fichiers dans le dossier `public`. Par exemple, l’[ajout d’une feuille de style](#adding-a-stylesheet) est effectué sans toucher au code HTML.

Si vous devez mettre à jour dynamiquement le titre de la page en fonction du contenu, vous pouvez utiliser l’API [`document.title`](https://developer.mozilla.org/docs/Web/API/Document/title) du navigateur. Pour les scénarios plus complexes lorsque vous souhaitez modifier le titre des composants React, vous pouvez utiliser [React Helmet](https://github.com/nfl/react-helmet), une bibliothèque tierce.

Si vous utilisez un serveur personnalisé pour votre application en production et que vous souhaitez modifier le titre avant qu’il ne soit envoyé au navigateur, vous pouvez suivre les conseils de [cette section](#generating-dynamic-meta-tags-on-the-server). Vous pouvez également précréer chaque page en tant que fichier HTML statique qui charge ensuite le bundle JavaScript, ce qui est abordé [ici](#pre-rendering-into-static-html-files).

## <a name="installing-a-dependency"></a>Installation d’une dépendance

Le projet généré inclut React et ReactDOM en tant que dépendances. Il inclut également un ensemble de scripts utilisés par Create React App en tant que dépendance de développement. Vous pouvez installer d’autres dépendances (par exemple, React Routeur) avec `npm` :

```sh
npm install --save react-router
```

Vous pouvez aussi utiliser `yarn` :

```sh
yarn add react-router
```

Cela fonctionne pour n’importe quelle bibliothèque, pas seulement `react-router`.

## <a name="importing-a-component"></a>Importation d’un composant

Cette configuration de projet prend en charge les modules ES6 grâce à Babel.<br>
Bien que vous puissiez toujours utiliser `require()` et `module.exports`, nous vous encourageons à utiliser [`import` et `export`](http://exploringjs.com/es6/ch_modules.html) à la place.

Par exemple :

### `Button.js`

```js
import React, { Component } from 'react';

class Button extends Component {
  render() {
    // ...
  }
}

export default Button; // Don’t forget to use export default!
```

### `DangerButton.js`


```js
import React, { Component } from 'react';
import Button from './Button'; // Import a component from another file

class DangerButton extends Component {
  render() {
    return <Button color="red" />;
  }
}

export default DangerButton;
```

Tenez compte de la [différence entre les exportations par défaut et les exportations nommées](http://stackoverflow.com/questions/36795819/react-native-es-6-when-should-i-use-curly-braces-for-import/36796281#36796281). Il s’agit d’une source d’erreurs courante.

Nous vous suggérons de vous contenter d’utiliser les importations et les exportations par défaut lorsqu’un module exporte uniquement une seule chose (par exemple, un composant). C’est ce que vous obtenez lorsque vous utilisez `export default Button` et `import Button from './Button'`.

Les exportations nommées sont utiles pour les modules utilitaires qui exportent plusieurs fonctions. Un module peut avoir au plus une exportation par défaut et autant d’exportations nommées que vous le souhaitez.

En savoir plus sur les modules ES6 :

* [Quand utiliser les accolades ?](http://stackoverflow.com/questions/36795819/react-native-es-6-when-should-i-use-curly-braces-for-import/36796281#36796281)
* [Exploration de ES6 : Modules](http://exploringjs.com/es6/ch_modules.html)
* [Présentation de ES6 : Modules](https://leanpub.com/understandinges6/read#leanpub-auto-encapsulating-code-with-modules)

## <a name="code-splitting"></a>Fractionnement du code

Au lieu de télécharger l’application entière avant que les utilisateurs puissent l’utiliser, le fractionnement de code vous permet de fractionner votre code en petits blocs que vous pouvez ensuite charger à la demande.

Cette configuration de projet prend en charge le fractionnement du code via [Dynamic `import()`](http://2ality.com/2017/01/import-operator.html#loading-code-on-demand). Sa [proposition](https://github.com/tc39/proposal-dynamic-import) se trouve à l’étape 3. Le formulaire `import()` de type fonction prend le nom du module comme argument et retourne un [`Promise`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Promise) qui résout toujours l’objet espace de noms du module.

Voici un exemple :

### `moduleA.js`

```js
const moduleA = 'Hello';

export { moduleA };
```
### `App.js`

```js
import React, { Component } from 'react';

class App extends Component {
  handleClick = () => {
    import('./moduleA')
      .then(({ moduleA }) => {
        // Use moduleA
      })
      .catch(err => {
        // Handle failure
      });
  };

  render() {
    return (
      <div>
        <button onClick={this.handleClick}>Load</button>
      </div>
    );
  }
}

export default App;
```

Cela fera de `moduleA.js` et toutes ses dépendances uniques un segment distinct qui se charge uniquement après que l’utilisateur a cliqué sur le bouton « Charger ».

Vous pouvez également l’utiliser avec la syntaxe `async` / `await` si vous le souhaitez.

### <a name="with-react-router"></a>Avec React Routeur

Si vous utilisez React Routeur, consultez [ce tutoriel](http://serverless-stack.com/chapters/code-splitting-in-create-react-app.html) pour savoir comment utiliser le fractionnement de code avec celui-ci. Le référentiel GitHub complémentaire est disponible [ici](https://github.com/AnomalyInnovations/serverless-stack-demo-client/tree/code-splitting-in-create-react-app).

Consultez également la section [Fractionnement du code](https://reactjs.org/docs/code-splitting.html) dans la documentation React.

## <a name="adding-a-stylesheet"></a>Ajout d’une feuille de style

Cette configuration de projet utilise [WebPack](https://webpack.js.org/) pour gérer toutes les ressources. WebPack offre un moyen personnalisé d’étendre le concept `import` au-delà de JavaScript. Pour exprimer qu’un fichier JavaScript dépend d’un fichier CSS, vous devez **importer le fichier CSS à partir du fichier JavaScript** :

### `Button.css`

```css
.Button {
  padding: 20px;
}
```

### `Button.js`

```js
import React, { Component } from 'react';
import './Button.css'; // Tell Webpack that Button.js uses these styles

class Button extends Component {
  render() {
    // You can use them as regular CSS styles
    return <div className="Button" />;
  }
}
```

**Cela n’est pas obligatoire pour React**  mais de nombreuses personnes trouvent cette fonctionnalité pratique. Vous pouvez en savoir plus sur les avantages de cette approche [ici](https://medium.com/seek-ui-engineering/block-element-modifying-your-javascript-components-d7f99fcab52b). Toutefois, vous devez savoir que cela rend votre code moins portable pour d’autres outils et environnements de génération que WebPack.

En cours de développement, le fait d’exprimer des dépendances de cette façon permet de recharger vos styles à la volée à mesure que vous les modifiez. En production, tous les fichiers CSS sont concaténés dans un fichier `.css` minifié dans la sortie de la génération.

Si vous êtes préoccupé par l’utilisation de la sémantique spécifique à WebPack, vous pouvez placer toutes vos CSS directement dans `src/index.css`. Elles sont toujours importées à partir de `src/index.js`, mais vous pouvez toujours supprimer cette importation si vous migrez ultérieurement vers un autre outil de génération.

## <a name="post-processing-css"></a>Post-traitement CSS

Cette configuration de projet minifie vos CSS et y ajoute automatiquement des préfixes de fournisseur par le biais du [préfixe automatique](https://github.com/postcss/autoprefixer). Vous n’avez donc pas à vous en soucier.

Par exemple, ceci :

```css
.App {
  display: flex;
  flex-direction: row;
  align-items: center;
}
```

devient cela :

```css
.App {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: horizontal;
  -webkit-box-direction: normal;
      -ms-flex-direction: row;
          flex-direction: row;
  -webkit-box-align: center;
      -ms-flex-align: center;
          align-items: center;
}
```

Si vous devez désactiver la préfixe pour une raison quelconque, [suivez cette section](https://github.com/postcss/autoprefixer#disabling).

## <a name="adding-a-css-preprocessor-sass-less-etc"></a>Ajout d’un préprocesseur CSS (Sass, Less, etc.)

En règle générale, nous vous recommandons de ne pas réutiliser les mêmes classes CSS entre différents composants. Par exemple, au lieu d’utiliser une classe CSS `.Button` dans les composants `<AcceptButton>` et `<RejectButton>`, nous vous recommandons de créer un composant `<Button>` avec ses propres `.Button` styles, que `<AcceptButton>` et `<RejectButton>` peuvent restituer (mais [pas hériter](https://facebook.github.io/react/docs/composition-vs-inheritance.html)).

Le fait de suivre cette règle rend souvent moins utiles les préprocesseurs CSS, car les fonctionnalités telles que mixins et l’imbrication sont remplacées par la composition des composants. Toutefois, vous pouvez intégrer un préprocesseur CSS si vous trouvez qu’il apporte de la valeur. Dans cette procédure pas à pas, nous utiliserons Sass, mais vous pouvez également utiliser Less ou une autre solution.

Tout d’abord, nous allons installer l’interface de ligne de commande pour Sass :

```sh
npm install --save node-sass-chokidar
```

Vous pouvez aussi utiliser `yarn` :

```sh
yarn add node-sass-chokidar
```

Ensuite, dans `package.json`, ajoutez les lignes suivantes à `scripts` :

```diff
   "scripts": {
+    "build-css": "node-sass-chokidar src/ -o src/",
+    "watch-css": "npm run build-css && node-sass-chokidar src/ -o src/ --watch --recursive",
     "start": "react-scripts start",
     "build": "react-scripts build",
     "test": "react-scripts test --env=jsdom",
```

>Remarque : pour utiliser un préprocesseur différent, remplacez les commandes `build-css` et `watch-css` en fonction de la documentation de votre préprocesseur.

Vous pouvez maintenant renommer `src/App.css` en `src/App.scss` et exécuter `npm run watch-css`. L’observateur trouve tous les fichiers Sass dans les sous-répertoires `src` et crée un fichier CSS correspondant en regard de celui-ci, dans notre cas, en remplaçant `src/App.css`. Comme `src/App.js` importe toujours `src/App.css`, les styles deviennent une partie de votre application. Vous pouvez maintenant modifier `src/App.scss` et `src/App.css` sera régénéré.

Pour partager des variables entre des fichiers Sass, vous pouvez utiliser les importations Sass. Par exemple, `src/App.scss` et d’autres fichiers de style de composant peuvent inclure `@import "./shared.scss";` avec des définitions de variables.

Pour activer l’importation de fichiers sans utiliser de chemins d’accès relatifs, vous pouvez ajouter l’option `--include-path` à la commande dans `package.json`.

```
"build-css": "node-sass-chokidar --include-path ./src --include-path ./node_modules src/ -o src/",
"watch-css": "npm run build-css && node-sass-chokidar --include-path ./src --include-path ./node_modules src/ -o src/ --watch --recursive",
```

Cela vous permettra d’effectuer des importations comme

```scss
@import 'styles/_colors.scss'; // assuming a styles directory under src/
@import 'nprogress/nprogress'; // importing a css file from the nprogress node module
```

À ce stade, vous souhaiterez peut-être supprimer tous les fichiers CSS du contrôle de code source et ajouter `src/**/*.css` à votre fichier `.gitignore`. Il est généralement conseillé de conserver les produits de génération en dehors du contrôle de code source.

En guise de dernière étape, il peut s’avérer pratique d’exécuter `watch-css` automatiquement avec `npm start` et d’exécuter `build-css` dans le cadre de `npm run build`. Vous pouvez utiliser l’opérateur `&&` pour exécuter deux scripts séquentiellement. Toutefois, comme il n’existe pas de méthode multiplateforme pour exécuter deux scripts en parallèle, nous allons installer un package pour ceci :

```sh
npm install --save npm-run-all
```

Vous pouvez aussi utiliser `yarn` :

```sh
yarn add npm-run-all
```

Ensuite, nous pouvons modifier les scripts `start` et `build` pour inclure les commandes de préprocesseur CSS :

```diff
   "scripts": {
     "build-css": "node-sass-chokidar src/ -o src/",
     "watch-css": "npm run build-css && node-sass-chokidar src/ -o src/ --watch --recursive",
-    "start": "react-scripts-ts start",
-    "build": "react-scripts-ts build",
+    "start-js": "react-scripts-ts start",
+    "start": "npm-run-all -p watch-css start-js",
+    "build": "npm run build-css && react-scripts-ts build",
     "test": "react-scripts test --env=jsdom",
     "eject": "react-scripts eject"
   }
```

L’exécution de `npm start` et `npm run build` génère également des fichiers Sass.

**Pourquoi`node-sass-chokidar` ?**

`node-sass` a été signalé comme ayant les problèmes suivants :

- `node-sass --watch` a été signalé comme ayant des *problèmes de performances* dans certaines conditions lorsqu’il est utilisé sur une machine virtuelle ou avec Docker.

- Styles infinis compilant [#1939](https://github.com/facebookincubator/create-react-app/issues/1939)

- `node-sass` a été signalé comme ayant des problèmes lors de la détection de nouveaux fichiers dans un répertoire [#1891](https://github.com/sass/node-sass/issues/1891)

 `node-sass-chokidar` est utilisé ici, car il résout ces problèmes.

## <a name="adding-images-fonts-and-files"></a>Ajout d’images, de polices et de fichiers

Avec WebPack, l’utilisation de ressources statiques comme les images et les polices fonctionne de la même façon que les CSS.

Vous pouvez **`import` un fichier directement dans un module TypeScript**. Cela indique à WebPack d’inclure ce fichier dans le bundle. Contrairement aux importations CSS, l’importation d’un fichier vous donne une valeur de chaîne. Cette valeur est le chemin final que vous pouvez référencer dans votre code, par exemple l’attribut `src` d’une image ou le `href` d’un lien vers un fichier PDF.

Pour réduire le nombre de demandes au serveur, l’importation d’images qui sont inférieures à 10 000 octets retourne un [URI de données](https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/Data_URIs) au lieu d’un chemin d’accès. Cela s’applique aux extensions de fichier suivantes : bmp, gif, jpg, jpeg et png. Les fichiers SVG sont exclus en raison de [#1153](https://github.com/facebookincubator/create-react-app/issues/1153).

Avant de commencer, vous devez définir chaque type de ressource en tant que format de module valide. Dans le cas contraire, le compilateur TypeScript génère une erreur de ce type :

>Module ./logo.png introuvable.

Pour importer des fichiers de ressources dans TypeScript, créez un fichier de définition de type dans votre projet et donnez-lui un nom comme `assets.d.ts`. Ensuite, ajoutez une ligne pour chaque type de ressource que vous devez importer :

```ts
declare module "*.gif";
declare module "*.jpg";
declare module "*.jpeg";
declare module "*.png";
declare module "*.svg";
```
Vous devrez redémarrer le compilateur pour que les modifications aient lieu.

Dans ce cas, nous avons ajouté plusieurs extensions de fichier image comme formats de module valides.

Maintenant que le compilateur est configuré, voici un exemple d’importation d’un fichier image :

```js
import React from 'react';
import logo from './logo.svg'; // Tell Webpack this JS file uses this image

console.log(logo); // /logo.84287d09.png

function Header() {
  // Import result is the URL of your image
  return <img src={logo} alt="Logo" />;
}

export default Header;
```

Cela garantit que lorsque le projet est généré, WebPack déplace correctement les images dans le dossier de build et nous fournit les chemins d’accès corrects.

Cela fonctionne également dans les CSS :

```css
.Logo {
  background-image: url(./logo.png);
}
```

WebPack localise toutes les références de module relatives dans CSS (elles commencent par `./`) et les remplace par les chemins d’accès finaux du bundle compilé. Si vous faites une faute de frappe ou si vous supprimez accidentellement un fichier important, vous verrez une erreur de compilation, tout comme lorsque vous importez un module JavaScript inexistant. Les noms de fichiers finaux du bundle compilé sont générés par WebPack à partir de hachages de contenu. Si le contenu du fichier change à l’avenir, WebPack lui attribue un nom différent en production. Vous n’avez donc pas à vous soucier de la mise en cache à long terme des ressources.

Veuillez noter qu’il s’agit également d’une fonctionnalité personnalisée de WebPack.

**Elle n’est pas nécessaire pour React**  mais de nombreuses personnes l’apprécient (et React Native utilise un mécanisme similaire pour les images).<br>
Une autre façon de gérer les ressources statiques est décrite dans la section suivante.

## <a name="using-the-public-folder"></a>Utilisation du dossier `public`

>Remarque : cette fonctionnalité est disponible avec `react-scripts@0.5.0` et les versions ultérieures.

### <a name="changing-the-html"></a>Modification du code HTML

Le dossier `public` contient le fichier HTML afin que vous puissiez le modifier, par exemple pour [définir le titre de la page](#changing-the-page-title).
La balise `<script>` avec le code compilé sera ajoutée automatiquement au cours du processus de génération.

### <a name="adding-assets-outside-of-the-module-system"></a>Ajout de ressources en dehors du système de module

Vous pouvez également ajouter d’autres ressources au dossier `public`.

Notez que nous vous encourageons normalement à `import` les ressources dans les fichiers JavaScript à la place.
Par exemple, consultez les sections sur l’[ajout d’une feuille de style](#adding-a-stylesheet) et l’[ajout d’images et de polices](#adding-images-fonts-and-files).
Ce mécanisme offre un certain nombre d’avantages :

* Les scripts et les feuilles de style sont minifiés et regroupés pour éviter les demandes de réseau supplémentaires.
* Les fichiers manquants provoquent des erreurs de compilation au lieu d’erreurs 404 pour vos utilisateurs.
* Les noms de fichiers de résultats incluent des hachages de contenu. Vous n’avez donc pas à vous soucier des navigateurs mettant en cache leurs anciennes versions.

Toutefois, il existe une **trappe d’échappement** que vous pouvez utiliser pour ajouter une ressource en dehors du système de module.

Si vous placez un fichier dans le dossier `public`, il ne sera **pas** traité par WebPack. Au lieu de cela, il sera copié dans le dossier de génération tel quel.   Pour référencer des ressources dans le dossier `public`, vous devez utiliser une variable spéciale appelée `PUBLIC_URL`.

À l’intérieur de `index.html`, vous pouvez l’utiliser comme suit :

```html
<link rel="shortcut icon" href="%PUBLIC_URL%/favicon.ico">
```

Seuls les fichiers contenus dans le dossier `public` sont accessibles par le préfixe `%PUBLIC_URL%`. Si vous devez utiliser un fichier à partir de `src` ou de `node_modules`, vous devrez le copier ici pour spécifier explicitement votre intention de faire de ce fichier une partie de la génération.

Lorsque vous exécutez `npm run build`, Creat React App remplacera `%PUBLIC_URL%` par un chemin d’accès absolu correct afin que votre projet fonctionne même si vous utilisez le routage côté client ou l’hébergez à une URL non racine.

Dans le code JavaScript, vous pouvez utiliser `process.env.PUBLIC_URL` à des fins similaires :

```js
render() {
  // Note: this is an escape hatch and should be used sparingly!
  // Normally we recommend using `import` for getting asset URLs
  // as described in “Adding Images and Fonts” above this section.
  return <img src={process.env.PUBLIC_URL + '/img/logo.png'} />;
}
```

Gardez à l’esprit les inconvénients de cette approche :

* Aucun des fichiers dans le dossier `public` n’est après post-traité ou minifié.
* Les fichiers manquants ne sont pas appelés au moment de la compilation et entraînent des erreurs 404 pour vos utilisateurs.
* Les noms de fichiers de résultats n’incluent pas les hachages de contenu. Vous devez donc ajouter des arguments de requête ou les renommer chaque fois qu’ils changent.

### <a name="when-to-use-the-public-folder"></a>Quand utiliser le dossier `public`

En règle générale, nous vous recommandons d’importer des [feuilles de style](#adding-a-stylesheet), des [images et des polices](#adding-images-fonts-and-files) à partir de JavaScript.
Le dossier `public` est utile comme solution de contournement pour un certain nombre de cas moins fréquents :

* Vous avez besoin d’un fichier portant un nom spécifique dans la sortie de la génération, par exemple [`manifest.webmanifest`](https://developer.mozilla.org/docs/Web/Manifest).
* Vous avez des milliers d’images et vous devez référencer dynamiquement leurs chemins d’accès.
* Vous souhaitez inclure un petit script comme [`pace.js`](http://github.hubspot.com/pace/docs/welcome/) en dehors du code groupé.
* Certaines bibliothèques peuvent être incompatibles avec WebPack et vous devez alors l’inclure en tant que balise `<script>`.

Notez que si vous ajoutez un `<script>` qui déclare des variables globales, vous devez également lire la section suivante sur leur utilisation.

## <a name="using-global-variables"></a>Utilisation de variables globales

Lorsque vous incluez un script dans le fichier HTML qui définit des variables globales et que vous essayez d’utiliser l’une de ces variables dans le code, le linter se plaint car il ne peut pas voir la définition de la variable.

Vous pouvez éviter cela en lisant la variable globale explicitement à partir de l’objet `window`, par exemple :

```js
const $ = window.$;
```

Cela rend évident le fait que vous utilisez une variable globale intentionnellement plutôt qu’en raison d’une faute de frappe.

Vous pouvez également forcer le linter à ignorer une ligne en ajoutant `// eslint-disable-line` après.

## <a name="adding-bootstrap"></a>Ajout de Bootstrap

Vous n’avez pas besoin d’utiliser [React Bootstrap](https://react-bootstrap.github.io) avec React mais il s’agit d’une bibliothèque populaire pour l’intégration de Bootstrap avec les applications React. Si vous en avez besoin, vous pouvez l’intégrer à Create React App en procédant comme suit :

Installez React Bootstrap et Bootstrap à partir de npm. React Bootstrap n’inclut pas de code CSS Bootstrap, qui doit également être installé :

```sh
npm install --save react-bootstrap bootstrap@3
```

Vous pouvez aussi utiliser `yarn` :

```sh
yarn add react-bootstrap bootstrap@3
```

Importez le fichier CSS Bootstrap et, éventuellement, le thème CSS au début de votre fichier ```src/index.js``` :

```js
import 'bootstrap/dist/css/bootstrap.css';
import 'bootstrap/dist/css/bootstrap-theme.css';
// Put any other imports below so that CSS from your
// components takes precedence over default styles.
```

importez les composants React Bootstrap requis dans un fichier ```src/App.js``` ou dans vos fichiers de composants personnalisés :

```js
import { Navbar, Jumbotron, Button } from 'react-bootstrap';
```

Vous êtes maintenant prêt à utiliser les composants React Bootstrap importés dans votre hiérarchie de composants définie dans la méthode de rendu. Voici un exemple [`App.js`](https://gist.githubusercontent.com/gaearon/85d8c067f6af1e56277c82d19fd4da7b/raw/6158dd991b67284e9fc8d70b9d973efe87659d72/App.js) refait à l’aide de React Bootstrap.

### <a name="using-a-custom-theme"></a>Utilisation d’un thème personnalisé

Parfois, vous devrez peut-être modifier les styles de Boostrap (ou package équivalent).<br>
Nous vous suggérons l’approche suivante :

* Créez un package qui dépend du package que vous souhaitez personnaliser, par exemple Bootstrap.
* Ajoutez les étapes de build nécessaires pour modifier le thème, puis publiez votre package sur npm.
* Installez votre propre package npm à thème en tant que dépendance de votre application.

Voici un exemple d’ajout d’un [Bootstrap personnalisé](https://medium.com/@tacomanator/customizing-create-react-app-aa9ffb88165) qui suit ces étapes.

## <a name="adding-flow"></a>Ajout de Flow

Flow est un vérificateur de type statique qui vous aide à écrire du code avec moins de bogues. Découvrez cette [introduction à l’utilisation des types statiques dans JavaScript](https://medium.com/@preethikasireddy/why-use-static-types-in-javascript-part-1-8382da1e0adb) si vous débutez avec ce concept.

Les versions récentes de [Flow](http://flowtype.org/) fonctionnent avec les projets Create React App prêts à l’emploi.

Pour ajouter Flow à un projet Create React App, procédez comme suit :

1. Exécutez `npm install --save flow-bin` (ou `yarn add flow-bin`).
2. Ajoutez `"flow": "flow"` à la section `scripts` de votre `package.json`.
3. Exécutez `npm run flow init` (ou `yarn flow init`) pour créer un [fichier `.flowconfig`](https://flowtype.org/docs/advanced-configuration.html) dans le répertoire racine.
4. Ajoutez `// @flow` à tous les fichiers dont vous souhaitez vérifier le type (par exemple, à `src/App.js`).

Vous pouvez maintenant exécuter `npm run flow` (ou `yarn flow` ) pour vérifier les erreurs de type dans les fichiers.
Vous pouvez éventuellement utiliser un IDE comme [Nuclide](https://nuclide.io/docs/languages/flow/) pour une meilleure expérience intégrée.
À l’avenir, nous prévoyons de l’intégrer à Create React App encore plus étroitement.

Pour en savoir plus sur Flow, consultez [la documentation associée](https://flowtype.org/).

## <a name="adding-a-router"></a>Ajout d’un routeur

Create React App n’impose pas une solution de routage spécifique, mais [React Routeur](https://reacttraining.com/react-router/) est la plus populaire.

Pour l’ajouter, exécutez :

```sh
npm install --save react-router-dom
```

Vous pouvez aussi utiliser `yarn` :

```sh
yarn add react-router-dom
```

Pour l’essayer, supprimez tout le code dans `src/App.js` et remplacez-le par l’un des exemples de son site web. L’[exemple de base](https://reacttraining.com/react-router/web/example/basic) est un bon point de départ.

Notez que [vous devrez peut-être configurer votre serveur de production pour prendre en charge le routage côté client](#serving-apps-with-client-side-routing) avant de déployer votre application.

## <a name="adding-custom-environment-variables"></a>Ajout de variables d’environnement personnalisées

>Remarque : cette fonctionnalité est disponible avec `react-scripts@0.2.3` et les versions ultérieures.

Votre projet peut consommer des variables déclarées dans votre environnement comme si elles étaient déclarées localement dans vos fichiers JS. Par défaut, vous avez `NODE_ENV` défini pour vous et toutes les autres variables d’environnement à partir de `REACT_APP_`.

**Les variables d’environnement sont incorporées au moment de la génération**. Comme Create React App génère un bundle HTML/CSS/JS statique, il ne peut pas les lire au moment de l’exécution. Pour les lire au moment de l’exécution, vous devez charger le code HTML en mémoire sur le serveur et remplacer les espaces réservés dans l’exécution, comme [décrit ici](#injecting-data-from-the-server-into-the-page). Vous pouvez également reconstruire l’application sur le serveur chaque fois que vous la modifiez.

>Remarque : vous devez créer des variables d’environnement personnalisées à partir de `REACT_APP_`. Toutes les autres variables, à l’exception de `NODE_ENV`, seront ignorées pour éviter d’[exposer accidentellement une clé privée sur l’ordinateur qui pourrait avoir le même nom](https://github.com/facebookincubator/create-react-app/issues/865#issuecomment-252199527). La modification des variables d’environnement nécessite que vous redémarriez le serveur de développement s’il est en cours d’exécution.

Ces variables d’environnement seront définies pour vous sur `process.env`. Par exemple, si vous avez une variable d’environnement nommée `REACT_APP_SECRET_CODE`, elle est exposée dans votre JS sous la forme `process.env.REACT_APP_SECRET_CODE`.

Il existe également une variable d’environnement intégrée spéciale appelée `NODE_ENV`. Vous pouvez la lire à partir de `process.env.NODE_ENV`. Lorsque vous exécutez `npm start`, il est toujours égal à `'development'`, lorsque vous exécutez `npm test`, il est toujours égal à `'test'` et lorsque vous exécutez `npm run build` pour créer un bundle de production, il est toujours égal à `'production'`. **Vous ne pouvez pas remplacer `NODE_ENV` manuellement.** Cela empêche les développeurs de déployer accidentellement une build de développement lente en production.

Ces variables d’environnement peuvent être utiles pour afficher les informations de manière conditionnelle en fonction de l’emplacement où le projet est déployé ou de la consommation de données sensibles qui résident en dehors de la gestion de version.

Tout d’abord, vous devez avoir défini les variables d’environnement. Supposons, par exemple, que vous souhaitiez utiliser un secret défini dans l’environnement à l’intérieur d’un `<form>` :

```jsx
render() {
  return (
    <div>
      <small>You are running this application in <b>{process.env.NODE_ENV}</b> mode.</small>
      <form>
        <input type="hidden" defaultValue={process.env.REACT_APP_SECRET_CODE} />
      </form>
    </div>
  );
}
```

Pendant la génération, `process.env.REACT_APP_SECRET_CODE` sera remplacé par la valeur actuelle de la variable d’environnement `REACT_APP_SECRET_CODE`. N’oubliez pas que la variable `NODE_ENV` sera définie automatiquement pour vous.

Lorsque vous chargez l’application dans le navigateur et inspectez le `<input>`, vous voyez que sa valeur est définie sur `abcdef` et le texte en gras indique l’environnement fourni lors de l’utilisation de `npm start` :

```html
<div>
  <small>You are running this application in <b>development</b> mode.</small>
  <form>
    <input type="hidden" value="abcdef" />
  </form>
</div>
```

Le formulaire ci-dessus recherche une variable appelée `REACT_APP_SECRET_CODE` à partir de l’environnement. Pour utiliser cette valeur, nous devons la définir dans l’environnement. Pour ce faire, vous pouvez utiliser deux méthodes : dans votre shell ou dans un fichier `.env`. Ces deux méthodes sont décrites dans les sections suivantes.

Avoir accès à `NODE_ENV` est également utile pour effectuer des actions de manière conditionnelle :

```js
if (process.env.NODE_ENV !== 'production') {
  analytics.disable();
}
```

Quand vous compilez l’application avec `npm run build`, l’étape de minimisation supprime cette condition et le bundle est plus petit.

### <a name="referencing-environment-variables-in-the-html"></a>Référencement des variables d’environnement dans le code HTML

>Remarque : cette fonctionnalité est disponible avec `react-scripts@0.9.0` et les versions ultérieures.

Vous pouvez également accéder aux variables d’environnement à partir de `REACT_APP_` dans le `public/index.html`. Par exemple :

```html
<title>%REACT_APP_WEBSITE_NAME%</title>
```

Notez que les avertissements de la section ci-dessus s’appliquent :

* Hormis quelques variables intégrées (`NODE_ENV` et `PUBLIC_URL`), les noms de variables doivent commencer par `REACT_APP_` pour fonctionner.
* Les variables d’environnement sont injectées au moment de la génération. Si vous devez les injecter au moment de l’exécution, [suivez cette approche à la place](#generating-dynamic-meta-tags-on-the-server).

### <a name="adding-temporary-environment-variables-in-your-shell"></a>Ajout de variables d’environnement temporaires dans votre interpréteur de commandes

La définition de variables d’environnement peut varier entre les systèmes d’exploitation. Il est également important de savoir que cette méthode est temporaire pendant la durée de vie de la session de l’interpréteur de commandes.

#### <a name="windows-cmdexe"></a>Windows (cmd.exe)

```cmd
set "REACT_APP_SECRET_CODE=abcdef" && npm start
```

(Remarque : les guillemets autour de l’attribution de variable sont requis pour éviter un espace blanc de fin.)

#### <a name="windows-powershell"></a>Windows (Powershell)

```Powershell
($env:REACT_APP_SECRET_CODE = "abcdef") -and (npm start)
```

#### <a name="linux-macos-bash"></a>Linux, macOS (Bash)

```bash
REACT_APP_SECRET_CODE=abcdef npm start
```

### <a name="adding-development-environment-variables-in-env"></a>Ajout de variables d’environnement de développement dans `.env`

>Remarque : cette fonctionnalité est disponible avec `react-scripts@0.5.0` et les versions ultérieures.

Pour définir des variables d’environnement permanentes, créez un fichier appelé `.env` à la racine de votre projet :

```
REACT_APP_SECRET_CODE=abcdef
```
>Remarque : vous devez créer des variables d’environnement personnalisées à partir de `REACT_APP_`. Toutes les autres variables, à l’exception de `NODE_ENV`, seront ignorées pour éviter d’[exposer accidentellement une clé privée sur l’ordinateur qui pourrait avoir le même nom](https://github.com/facebookincubator/create-react-app/issues/865#issuecomment-252199527). La modification des variables d’environnement nécessite que vous redémarriez le serveur de développement s’il est en cours d’exécution.

Les fichiers `.env` **doivent être** archivés dans le contrôle de code source (à l’exclusion de `.env*.local`).

#### <a name="what-other-env-files-are-can-be-used"></a>Quels sont les autres fichiers `.env` que vous pouvez utiliser ?

>Remarque : cette fonctionnalité est **disponible avec `react-scripts@1.0.0` et les versions ultérieures**.

* `.env` : valeur par défaut.
* `.env.local` : remplacements locaux. **Ce fichier est chargé pour tous les environnements à l’exception de l’environnement de test.**
* `.env.development`, `.env.test`, `.env.production` : paramètres spécifiques de l’environnement.
* `.env.development.local`, `.env.test.local`, `.env.production.local` : remplacements locaux des paramètres propres à l’environnement.

Les fichiers à gauche ont plus de priorité que les fichiers sur la droite :

* `npm start`: `.env.development.local`, `.env.development`, `.env.local`, `.env`
* `npm run build`: `.env.production.local`, `.env.production`, `.env.local`, `.env`
* `npm test` : `.env.test.local`, `.env.test`, `.env` (notez que `.env.local` est manquant)

Ces variables agiront comme valeurs par défaut si l’ordinateur ne les définit pas explicitement.<br>
Pour plus d’informations, reportez-vous à la [documentation dotenv](https://github.com/motdotla/dotenv).

>Remarque : si vous définissez des variables d’environnement pour le développement, votre CI et/ou votre plateforme d’hébergement auront probablement besoin que ces éléments soient également définis. Consultez leur documentation pour savoir comment faire. Par exemple, consultez la documentation de [Travis CI](https://docs.travis-ci.com/user/environment-variables/) ou [Heroku](https://devcenter.heroku.com/articles/config-vars).

#### <a name="expanding-environment-variables-in-env"></a>Développement des variables d’environnement dans `.env`

>Remarque : cette fonctionnalité est disponible avec `react-scripts@1.1.0` et les versions ultérieures.

Développez les variables déjà présentes sur votre ordinateur pour les utiliser dans votre fichier `.env` (à l’aide de [dotenv-expand](https://github.com/motdotla/dotenv-expand)).

Par exemple, pour obtenir la variable d’environnement `npm_package_version` :

```
REACT_APP_VERSION=$npm_package_version
# also works:
# REACT_APP_VERSION=${npm_package_version}
```

Ou développez les variables locales dans le fichier `.env` actuel :

```
DOMAIN=www.example.com
REACT_APP_FOO=$DOMAIN/foo
REACT_APP_BAR=$DOMAIN/bar
```

## <a name="can-i-use-decorators"></a>Puis-je utiliser des éléments décoratifs ?

De nombreuses bibliothèques populaires utilisent des [éléments décoratifs](https://medium.com/google-developers/exploring-es7-decorators-76ecb65fb841) dans leur documentation.<br>
Create React App ne prend pas en charge la syntaxe des éléments décoratifs pour le moment, car :

* C’est une proposition expérimentale qui est susceptible de changer.
* La version de la spécification actuelle n’est pas officiellement prise en charge par Babel.
* En cas de modification de la spécification, nous ne pourrons pas écrire de codemods, car nous ne les utilisons pas en interne sur Facebook.

Toutefois, dans de nombreux cas, vous pouvez très bien réécrire du code basé sur un élément décoratif sans élément décoratif.<br>
Reportez-vous à ces deux fils de discussion pour référence :

* [#214](https://github.com/facebookincubator/create-react-app/issues/214)
* [#411](https://github.com/facebookincubator/create-react-app/issues/411)

Create React App ajoute la prise en charge des éléments décoratifs lorsque la spécification passe à une phase stable.

## <a name="fetching-data-with-ajax-requests"></a>Récupération de données avec des demandes AJAX

React n’impose pas une approche spécifique de l’extraction de données, mais les utilisateurs utilisent généralement une bibliothèque comme [axios](https://github.com/axios/axios) ou l’[API `fetch()`](https://developer.mozilla.org/docs/Web/API/Fetch_API) fournie par le navigateur. En pratique, Create React App inclut un polyfill pour `fetch()` afin que vous puissiez l’utiliser sans vous soucier de la prise en charge du navigateur.

La fonction globale `fetch` permet d’effectuer facilement des demandes AJAX. Elle prend une URL comme entrée et retourne un `Promise` qui correspond à un objet `Response`. Vous y trouverez des informations supplémentaires sur `fetch` [ici](https://developer.mozilla.org/docs/Web/API/Fetch_API/Using_Fetch).

Ce projet inclut également un [polyfill Promise](https://github.com/then/promise) qui fournit une implémentation complète de Promises/A+. Une Promesse représente le résultat éventuel d’une opération asynchrone. Vous pouvez trouver des informations supplémentaires sur les promesses [ici](https://www.promisejs.org/) et [ici](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Promise). Axios et `fetch()` utilisent des promesses en coulisses. Vous pouvez également utiliser la syntaxe [`async / await`](https://davidwalsh.name/async-await) pour réduire l’imbrication des rappels.

Vous pouvez en savoir plus sur la création de requêtes AJAX à partir de composants de React dans [l’entrée FAQ sur le site web de React](https://reactjs.org/docs/faq-ajax.html).

## <a name="integrating-with-an-api-backend"></a>Intégration avec un backend d’API

Ces tutoriels vous aideront à intégrer votre application à un backend d’API exécuté sur un autre port, en utilisant `fetch()` pour y accéder.

### <a name="node"></a>Nœud
Consultez [ce tutoriel](https://www.fullstackreact.com/articles/using-create-react-app-with-a-server/).
Le référentiel GitHub complémentaire est disponible [ici](https://github.com/fullstackreact/food-lookup-demo).

### <a name="ruby-on-rails"></a>Ruby on Rails

Consultez [ce tutoriel](https://www.fullstackreact.com/articles/how-to-get-create-react-app-to-work-with-your-rails-api/).
Le référentiel GitHub complémentaire est disponible [ici](https://github.com/fullstackreact/food-lookup-demo-rails).

## <a name="proxying-api-requests-in-development"></a>Envoi par proxy de demandes d’API en développement

>Remarque : cette fonctionnalité est disponible avec `react-scripts@0.2.3` et les versions ultérieures.

Les utilisateurs traitent souvent l’application frontale React à partir du même hôte et du même port que leur implémentation principale.<br>
Par exemple, une configuration de production peut se présenter comme suit après le déploiement de l’application :

```
/             - static server returns index.html with React app
/todos        - static server returns index.html with React app
/api/todos    - server handles any /api/* requests using the backend implementation
```

Ce type d’installation n’est **pas** obligatoire. Toutefois, si vous **disposez** d’une configuration telle que celle-ci, il est pratique d’écrire des demandes comme `fetch('/api/todos')` sans vous soucier de les rediriger vers un autre hôte ou port pendant le développement.

Pour indiquer au serveur de développement de transmettre par proxy toutes les demandes inconnues à votre serveur d’API en développement, ajoutez un champ `proxy` à votre `package.json`, par exemple :

```js
  "proxy": "http://localhost:4000",
```

De cette façon, lorsque vous `fetch('/api/todos')` en cours de développement, le serveur de développement reconnaît qu’il ne s’agit pas d’une ressource statique et effectue un proxy de votre demande vers `http://localhost:4000/api/todos` en tant que secours. Le serveur de développement tente uniquement d’envoyer des requêtes sans en-tête `text/html` accept au proxy.

En pratique, cela évite les [problèmes CORS](http://stackoverflow.com/questions/21854516/understanding-ajax-cors-and-security-considerations) et les messages d’erreur de ce type lors du développement :

```
Fetch API cannot load http://localhost:4000/api/todos. No 'Access-Control-Allow-Origin' header is present on the requested resource. Origin 'http://localhost:3000' is therefore not allowed access. If an opaque response serves your needs, set the request's mode to 'no-cors' to fetch the resource with CORS disabled.
```

N’oubliez pas que `proxy` n’a d’effet que dans le développement (avec `npm start`), et c’est à vous de veiller à ce que les URL comme `/api/todos` pointent vers le bon élément en production. Vous n’avez pas à utiliser le préfixe `/api`. Toute demande non reconnue sans en-tête `text/html` accept sera redirigée vers le `proxy` spécifié.

L’option `proxy` prend en charge les connexions HTTP, HTTPS et WebSocket.<br>
Si l’option `proxy` n’est **pas** suffisamment flexible pour vous, vous pouvez également :

* [Configurer le proxy vous-même](#configuring-the-proxy-manually)
* Activez CORS sur votre serveur ([voici comment le faire pour Express](http://enable-cors.org/server_expressjs.html)).
* Utilisez des [variables d’environnement](#adding-custom-environment-variables) pour injecter l’hôte serveur et le port appropriés dans votre application.

### <a name="invalid-host-header-errors-after-configuring-proxy"></a>Erreurs d’en-tête d’hôte non valide après la configuration du proxy

Lorsque vous activez l’option `proxy`, vous optez pour un ensemble plus strict de contrôles hôtes. Cela est nécessaire car le fait de laisser le serveur principal ouvert aux hôtes distants rend votre ordinateur vulnérable aux attaques de reliaison DNS. Le problème est décrit dans [cet article](https://medium.com/webpack/webpack-dev-server-middleware-security-issues-1489d950874a) et [ce problème](https://github.com/webpack/webpack-dev-server/issues/887).

Cela ne vous affectera pas lors du développement sur `localhost`, mais si vous développez à distance comme [décrit ici](https://github.com/facebookincubator/create-react-app/issues/2271), vous verrez cette erreur dans le navigateur après l’activation de l’option `proxy` :

>En-tête d’hôte non valide

Pour contourner ce problème, vous pouvez spécifier votre hôte de développement public dans un fichier appelé `.env.development` à la racine de votre projet :

```
HOST=mypublicdevhost.com
```

Si vous redémarrez le serveur de développement maintenant et que vous chargez l’application à partir de l’hôte spécifié, elle doit fonctionner.

Si vous rencontrez toujours des problèmes ou si vous utilisez un environnement plus exotique comme un éditeur cloud, vous pouvez contourner complètement la vérification de l’hôte en ajoutant une ligne à `.env.development.local`. **Notez que cela constitue un risque et expose votre ordinateur à l’exécution de code à distance à partir de sites web malveillants :**

```
# NOTE: THIS IS DANGEROUS!
# It exposes your machine to attacks from the websites you visit.
DANGEROUSLY_DISABLE_HOST_CHECK=true
```

Nous ne recommandons pas cette approche.

### <a name="configuring-the-proxy-manually"></a>Configuration manuelle du proxy

>Remarque : cette fonctionnalité est disponible avec `react-scripts@1.0.0` et les versions ultérieures.

Si l’option `proxy` n’est **pas** suffisamment flexible pour vous, vous pouvez spécifier un objet sous la forme suivante (dans `package.json`).<br>
Vous pouvez également spécifier n’importe quelle valeur de configuration [`http-proxy-middleware`](https://github.com/chimurai/http-proxy-middleware#options) ou [`http-proxy`](https://github.com/nodejitsu/node-http-proxy#options) prise en charge.
```js
{
  // ...
  "proxy": {
    "/api": {
      "target": "<url>",
      "ws": true
      // ...
    }
  }
  // ...
}
```

Toutes les demandes correspondant à ce chemin d’accès seront des proxies, aucune exception. Cela inclut les demandes pour `text/html`, que l’option `proxy` standard ne fait pas par proxy.

Si vous devez spécifier plusieurs proxys, vous pouvez le faire en spécifiant des entrées supplémentaires.
Vous pouvez également limiter les correspondances à l’aide de `*` et/ou `**`, pour faire correspondre le chemin exactement ou n’importe quel sous-chemin.
```js
{
  // ...
  "proxy": {
    // Matches any request starting with /api
    "/api": {
      "target": "<url_1>",
      "ws": true
      // ...
    },
    // Matches any request starting with /foo
    "/foo": {
      "target": "<url_2>",
      "ssl": true,
      "pathRewrite": {
        "^/foo": "/foo/beta"
      }
      // ...
    },
    // Matches /bar/abc.html but not /bar/sub/def.html
    "/bar/*.html": {
      "target": "<url_3>",
      // ...
    },
    // Matches /baz/abc.html and /baz/sub/def.html
    "/baz/**/*.html": {
      "target": "<url_4>"
      // ...
    }
  }
  // ...
}
```

### <a name="configuring-a-websocket-proxy"></a>Configuration d’un proxy WebSocket

Lors de la configuration d’un proxy WebSocket, vous devez tenir compte de certaines considérations supplémentaires.

Si vous utilisez un moteur WebSocket comme [Socket.io](https://socket.io/), vous devez disposer d’un serveur Socket.io en cours d’exécution que vous pouvez utiliser comme cible de proxy. Socket.io ne fonctionne pas avec un serveur WebSocket standard. Plus précisément, ne vous attendez pas à ce que Socket.io fonctionne avec [le test echo WebSocket.org](http://websocket.org/echo.html).

Une bonne documentation est disponible pour la [configuration d’un serveur Socket.io](https://socket.io/docs/).

Les WebSockets standard **fonctionnent** avec un serveur WebSocket standard, ainsi que le test écho WebSocket.org. Vous pouvez utiliser des bibliothèques telles que [ws](https://github.com/websockets/ws) pour le serveur, avec des [WebSockets natifs dans le navigateur](https://developer.mozilla.org/docs/Web/API/WebSocket).

Dans les deux cas, vous pouvez envoyer par proxy manuellement les demandes WebSocket dans `package.json` :

```js
{
  // ...
  "proxy": {
    "/socket": {
      // Your compatible WebSocket server
      "target": "ws://<socket_url>",
      // Tell http-proxy-middleware that this is a WebSocket proxy.
      // Also allows you to proxy WebSocket requests without an additional HTTP request
      // https://github.com/chimurai/http-proxy-middleware#external-websocket-upgrade
      "ws": true
      // ...
    }
  }
  // ...
}
```

## <a name="using-https-in-development"></a>Utilisation du protocole HTTPS dans le développement

>Remarque : cette fonctionnalité est disponible avec `react-scripts@0.4.0` et les versions ultérieures.

Vous pouvez exiger que le serveur de développement serve des pages via HTTPS. Cela peut s’avérer utile lors de l’utilisation de l[a fonctionnalité « proxy »](#proxying-api-requests-in-development) pour traiter par proxy les demandes vers un serveur d’API lorsque ce serveur d’API sert lui-même à utiliser le protocole HTTPS.

Pour ce faire, définissez la variable d’environnement `HTTPS` sur `true`, puis démarrez le serveur de développement comme d’habitude avec `npm start` :

#### <a name="windows-cmdexe"></a>Windows (cmd.exe)

```cmd
set HTTPS=true&&npm start
```

#### <a name="windows-powershell"></a>Windows (Powershell)

```Powershell
($env:HTTPS = $true) -and (npm start)
```

(Remarque : l’absence d’espace blanc est intentionnelle.)

#### <a name="linux-macos-bash"></a>Linux, macOS (Bash)

```bash
HTTPS=true npm start
```

Notez que le serveur utilise un certificat auto-signé, de sorte que votre navigateur web affiche presque définitivement un avertissement lors de l’accès à la page.

## <a name="generating-dynamic-meta-tags-on-the-server"></a>Génération de balises `<meta>` dynamiques sur le serveur

Comme Create React App ne prend pas en charge le rendu du serveur, vous vous demandez peut-être comment rendre les balises dynamiques `<meta>` et refléter l’URL actuelle. Pour résoudre ce problème, nous vous recommandons d’ajouter des espaces réservés dans le code HTML, comme suit :

```html
<!doctype html>
<html lang="en">
  <head>
    <meta property="og:title" content="__OG_TITLE__">
    <meta property="og:description" content="__OG_DESCRIPTION__">
```

Ensuite, sur le serveur, quel que soit le serveur principal que vous utilisez, vous pouvez lire `index.html` en mémoire et remplacer `__OG_TITLE__`, `__OG_DESCRIPTION__` et tout autre espace réservé par des valeurs en fonction de l’URL actuelle. Veillez simplement à assainir et à échapper les valeurs interpolées afin qu’elles puissent être incorporées en toute sécurité dans le code HTML.

Si vous utilisez un serveur Node, vous pouvez même partager la logique de correspondance d’itinéraire entre le client et le serveur. Toutefois, le fait de le dupliquer fonctionne également avec précision dans des cas simples.

## <a name="pre-rendering-into-static-html-files"></a>Prérendu dans des fichiers HTML statiques

Si vous hébergez votre `build` avec un fournisseur d’hébergement statique, vous pouvez utiliser [react-snapshot](https://www.npmjs.com/package/react-snapshot) pour générer des pages HTML pour chaque itinéraire, ou lien relatif, dans votre application. Ces pages deviennent alors en toute transparence actives, ou « hydratées », lorsque le bundle JavaScript est chargé.

Il existe également des opportunités d’utiliser ceci en dehors de l’hébergement statique, afin d’enlever la pression du serveur lors de la génération et de la mise en cache des itinéraires.

Le principal avantage du prérendu est que vous récupérez le contenu de base de chaque page _avec_ la charge utile HTML, que votre bundle JavaScript soit ou non téléchargé avec succès. Cela augmente également la probabilité que chaque itinéraire de votre application soit récupéré par les moteurs de recherche.

Vous pouvez en savoir plus sur [le prérendu sans configuration (également appelé prise de capture instantanée) ici](https://medium.com/superhighfives/an-almost-static-stack-6df0a2791319).

## <a name="injecting-data-from-the-server-into-the-page"></a>Injection de données à partir du serveur dans la page

Comme dans la section précédente, vous pouvez conserver des espaces réservés dans le code HTML qui injectent des variables globales, par exemple :

```js
<!doctype html>
<html lang="en">
  <head>
    <script>
      window.SERVER_DATA = __SERVER_DATA__;
    </script>
```

Ensuite, sur le serveur, vous pouvez remplacer `__SERVER_DATA__` par un JSON de données réelles juste avant d’envoyer la réponse. Le code client peut ensuite lire `window.SERVER_DATA` pour l’utiliser. **Veillez à [assainir le JSON avant de l’envoyer au client](https://medium.com/node-security/the-most-common-xss-vulnerability-in-react-js-applications-2bdffbcc1fa0), car il rend votre application vulnérable aux attaques XSS.**

## <a name="running-tests"></a>Exécution des tests

>Remarque : cette fonctionnalité est disponible avec `react-scripts@0.3.0` et les versions ultérieures.<br>
>[Lisez le guide de migration pour savoir comment l’activer dans des projets plus anciens.](https://github.com/facebookincubator/create-react-app/blob/master/CHANGELOG.md#migrating-from-023-to-030)

Create React App utilise [Jest](https://facebook.github.io/jest/) comme série de tests. Pour préparer cette intégration, nous avons effectué une [grande refonde](https://facebook.github.io/jest/blog/2016/09/01/jest-15.html) de Jest. Par conséquent, si vous avez eu de mauvais échos à son sujet il y a quelques années, vous pouvez maintenant lui faire confiance.

Jest est un testeur basé sur Node. Cela signifie que les tests s’exécutent toujours dans un environnement Node et non dans un navigateur réel. Cela nous permet d’activer une vitesse d’itération rapide et d’empêcher la friabilité.

Bien que Jest fournisse des globales de navigateur, telles que `window` grâce à [jsdom](https://github.com/tmpvar/jsdom), il s’agit uniquement d’approximations du comportement réel du navigateur. Jest est destiné à être utilisé pour les tests unitaires de votre logique et de vos composants plutôt que des excentricités DOM.

Nous vous recommandons d’utiliser un outil distinct pour les tests de bout en bout du navigateur, si vous en avez besoin. Ils n’entrent pas dans le cadre de Create React App.

### <a name="filename-conventions"></a>Conventions de nom de fichier

Jest recherche les fichiers de test avec l’une des conventions d’affectation de noms courantes suivantes :

* Fichiers avec suffixe `.js` dans les dossiers `__tests__`.
* Fichiers avec suffixe `.test.js`.
* Fichiers avec suffixe `.spec.js`.

Les fichiers `.test.js` / `.spec.js` (ou les dossiers `__tests__`) peuvent être situés à n’importe quelle profondeur dans le dossier `src` de premier niveau.

Nous vous recommandons de placer les fichiers de test (ou dossiers `__tests__`) en regard du code qu’ils testent afin que les importations relatives soient plus courtes. Par exemple, si `App.test.js` et `App.js` se trouvent dans le même dossier, le test doit juste être `import App from './App'` au lieu d’un chemin d’accès relatif long. La colocalisation permet également de trouver des tests plus rapidement dans des projets plus volumineux.

### <a name="command-line-interface"></a>Interface de ligne de commande

Lorsque vous exécutez `npm test`, Jest est lancé en mode espion. Chaque fois que vous enregistrez un fichier, il réexécute les tests, tout comme `npm start` recompile le code.

L’observateur inclut une interface de ligne de commande interactive avec la possibilité d’exécuter tous les tests ou de se concentrer sur un modèle de recherche. Il est conçu de cette manière afin que vous puissiez le garder ouvert et profiter de réexécutions rapides. Vous pouvez apprendre les commandes à partir de la section « Surveiller l’utilisation » que l’observateur imprime après chaque exécution :

![Mode espion Jest](http://facebook.github.io/jest/img/blog/15-watch.gif)

### <a name="version-control-integration"></a>Intégration de la gestion de version

Par défaut, lorsque vous exécutez `npm test`, Jest exécute uniquement les tests liés aux fichiers modifiés depuis la dernière validation. Il s’agit d’une optimisation conçue pour accélérer l’exécution de vos tests, quel que soit le nombre de tests dont vous disposez. Toutefois, cela suppose que vous ne validez pas souvent le code qui ne passe pas les tests.

Jest indiquera toujours explicitement qu’il exécutait uniquement des tests liés aux fichiers modifiés depuis la dernière validation. Vous pouvez également appuyer sur `a` dans le mode espion pour forcer Jest à exécuter tous les tests.

Jest exécutera toujours tous les tests sur un serveur d’[intégration continue](#continuous-integration) ou si le projet n’est pas à l’intérieur d’un référentiel Git ou Mercurial.

### <a name="writing-tests"></a>Écriture des tests

Pour créer des tests, ajoutez des blocs `it()` (ou `test()`) avec le nom du test et son code. Vous pouvez éventuellement les inclure dans des blocs `describe()` à des fins de regroupement logique, mais ce n’est ni obligatoire ni recommandé.

Jest fournit une fonction globale intégrée `expect()` pour effectuer des assertions. Un test de base peut se présenter comme suit :

```js
import sum from './sum';

it('sums numbers', () => {
  expect(sum(1, 2)).toEqual(3);
  expect(sum(2, 2)).toEqual(4);
});
```

Tous les éléments correspondants `expect()` pris en charge par Jest sont [largement documentés ici](http://facebook.github.io/jest/docs/expect.html).<br>
Vous pouvez également utiliser [`jest.fn()` et `expect(fn).toBeCalled()`](http://facebook.github.io/jest/docs/expect.html#tohavebeencalled) pour créer des « espions » ou des fonctions factices.

### <a name="testing-components"></a>Test des composants

Il existe un large éventail de techniques de test de composants. Elles vont d’un « test de vérification de build » qui vérifie qu’un composant est restitué sans levée, à un rendu superficiel et à un test d’une partie de la sortie, à un rendu complet et à un test des modifications d’état et du cycle de vie des composants.

Différents projets choisissent différents compromis en matière de test en fonction de la fréquence de modification des composants et de la quantité de logique qu’ils contiennent. Si vous n’avez pas encore choisi de stratégie de test, nous vous recommandons de commencer par créer des tests de vérification de build simples pour vos composants :

```ts
import * as React from 'react';
import * as ReactDOM from 'react-dom';
import App from './App';

it('renders without crashing', () => {
  const div = document.createElement('div');
  ReactDOM.render(<App />, div);
});
```

Ce test monte un composant et s’assure qu’il n’a pas été levé pendant le rendu. Les tests comme celui-ci fournissent beaucoup de valeur, avec très peu d’efforts et ils sont donc très utiles comme point de départ. C’est le test que vous trouverez dans `src/App.test.tsx`.

Lorsque vous rencontrez des bogues provoqués par la modification des composants, vous obtenez des informations plus approfondies sur les parties de ce test dans votre application. Cela peut être un bon moment pour introduire des tests plus spécifiques qui déclarent un comportement ou une sortie attendue spécifique.

Si vous souhaitez tester les composants isolément des composants enfants qu’ils affichent, nous vous recommandons d’utiliser l’[API de rendu `shallow()`](http://airbnb.io/enzyme/docs/api/shallow.html) à partir d’[Enzyme](http://airbnb.io/enzyme/). Pour l'installer, exécutez la commande suivante :

```sh
npm install --save-dev enzyme @types/enzyme enzyme-adapter-react-16 @types/enzyme-adapter-react-16 react-test-renderer @types/react-test-renderer
```

Vous pouvez aussi utiliser `yarn` :

```sh
yarn add --dev enzyme @types/enzyme enzyme-adapter-react-16 @types/enzyme-adapter-react-16 react-test-renderer @types/react-test-renderer
```

#### `src/setupTests.ts`
```ts
import * as Enzyme from 'enzyme';
import * as Adapter from 'enzyme-adapter-react-16';

Enzyme.configure({ adapter: new Adapter() });
```

>Remarque : gardez à l’esprit que si vous décidez d’éjecter avant de créer `src/setupTests.js`, le fichier résultant `package.json` ne contient aucune référence à ce dernier. [Lisez cet article](#initializing-test-environment) pour savoir comment ajouter ceci après l’éjection.

Vous pouvez maintenant écrire un test de vérification de build :

```ts
import * as React from 'react';
import { shallow } from 'enzyme';
import App from './App';

it('renders without crashing', () => {
  shallow(<App />);
});
```

Contrairement au test de vérification de build précédent utilisant `ReactDOM.render()`, ce test rend uniquement `<App>` et n’est pas plus approfondi. Par exemple, même si `<App>` lui-même restitue un `<Button>` qui lève une exception, ce test réussira. Le rendu superficiel est parfait pour les tests unitaires isolés, mais vous pouvez toujours créer des tests de rendu complets pour garantir l’intégration correcte des composants. Enzyme prend en charge le [rendu complet avec `mount()`](http://airbnb.io/enzyme/docs/api/mount.html), et vous pouvez également l’utiliser pour tester les modifications d’état et le cycle de vie des composants.

Vous pouvez lire la documentation sur [Enzyme](http://airbnb.io/enzyme/) pour obtenir des techniques de test supplémentaires. La documentation sur Enzyme utilise Chai et Sinon pour les assertions, mais vous n’êtes pas obligé de les utiliser, car Jest fournit des fonctionnalités intégrées `expect()` et `jest.fn()` pour les espions.

Voici un exemple de la documentation sur Enzyme qui déclare une sortie spécifique, réécrite pour utiliser des mises en correspondance Jest :

```ts
import * as React from 'react';
import { shallow } from 'enzyme';
import App from './App';

it('renders welcome message', () => {
  const wrapper = shallow(<App />);
  const welcome = <h2>Welcome to React</h2>;
  // expect(wrapper.contains(welcome)).to.equal(true);
  expect(wrapper.contains(welcome)).toEqual(true);
});
```

Toutes les mises en correspondances Jest sont [largement documentées ici](http://facebook.github.io/jest/docs/expect.html).<br>
Néanmoins, vous pouvez utiliser une bibliothèque d’assertion tierce comme [Chai](http://chaijs.com/) si vous le souhaitez, comme décrit ci-dessous.

En outre, vous pouvez trouver [jest-enzyme](https://github.com/blainekasten/enzyme-matchers) utile pour simplifier vos tests avec des mises en correspondance lisibles. Le code `contains` ci-dessus peut être écrit plus simplement avec jest-enzyme.

```js
expect(wrapper).toContainReact(welcome)
```

Pour activer ceci, installez `jest-enzyme` :

```sh
npm install --save jest-enzyme
```

Vous pouvez aussi utiliser `yarn` :

```sh
yarn add jest-enzyme
```

Importez-le dans [`src/setupTests.ts`](#initializing-test-environment) pour que ses mises en correspondance soient disponibles dans chaque test :

```js
import 'jest-enzyme';
```

### <a name="using-third-party-assertion-libraries"></a>Utilisation de bibliothèques d’assertion tierces

Nous vous recommandons d’utiliser `expect()` pour les assertions et `jest.fn()` pour les espions. Si vous rencontrez des problèmes avec eux, [indiquez-les à Jest](https://github.com/facebook/jest/issues/new), et nous allons les résoudre. Nous avons l’intention de les rendre plus performants pour React, en prenant en charge, par exemple, [l’impression d’éléments React en tant que JSX](https://github.com/facebook/jest/pull/1566).

Toutefois, si vous êtes habitué à d’autres bibliothèques, telles que [Chai](http://chaijs.com/) et [Sinon](http://sinonjs.org/), ou si vous avez du code existant qui les utilise, vous pouvez les importer normalement comme suit :

```js
import sinon from 'sinon';
import { expect } from 'chai';
```

Puis utilisez-les dans vos tests comme vous le faites habituellement.

### <a name="initializing-test-environment"></a>Initialisation de l’environnement de test

>Remarque : cette fonctionnalité est disponible avec `react-scripts@0.4.0` et les versions ultérieures.

Si votre application utilise une API de navigateur que vous devez simuler dans vos tests ou si vous avez simplement besoin d’une installation globale avant d’exécuter vos tests, ajoutez un `src/setupTests.ts` à votre projet. Ceci sera exécuté automatiquement avant l’exécution de vos tests.

Par exemple :

#### `src/setupTests.ts`
```ts
const localStorageMock = {
  getItem: jest.fn(),
  setItem: jest.fn(),
  clear: jest.fn()
};
global.localStorage = localStorageMock
```

>Remarque : gardez à l’esprit que si vous décidez d’éjecter avant de créer `src/setupTests.js`, le fichier résultant `package.json` ne contient aucune référence. Vous devez donc créer manuellement la propriété `setupTestFrameworkScriptFile` dans la configuration de Jest, comme suit :

>```js
>"jest": {
>   // ...
>   "setupTestFrameworkScriptFile": "<rootDir>/src/setupTests.js"
>  }
>  ```

### <a name="focusing-and-excluding-tests"></a>Focus et exclusion de tests

Vous pouvez remplacer `it()` par `xit()` pour empêcher temporairement l’exécution d’un test.<br>
De même, `fit()` vous permet de vous concentrer sur un test spécifique sans exécuter d’autres tests.

### <a name="coverage-reporting"></a>Rapports de couverture

Jest dispose d’un rapporteur de couverture intégré qui fonctionne bien avec ES6 et ne nécessite aucune configuration.<br>
Exécutez `npm test -- --coverage` (notez l’élément `--` supplémentaire au milieu) pour inclure un rapport de couverture comme suit :

![rapport de couverture](http://i.imgur.com/5bFhnTS.png)

Notez que les tests s’exécutent beaucoup plus lentement avec une couverture. Il est donc recommandé de l’exécuter séparément de votre flux de travail normal.

### <a name="continuous-integration"></a>Intégration continue

Par défaut, `npm test` exécute l’observateur avec l’interface CLI interactive. Toutefois, vous pouvez forcer l’exécution des tests une fois et terminer le processus en définissant une variable d’environnement appelée `CI`.

Lorsque vous créez une build de votre application avec des avertissements lint `npm run build`, ceux-ci ne sont pas activés par défaut. Comme `npm test`, vous pouvez forcer la génération à effectuer une vérification de l’avertissement linter en définissant la variable d’environnement `CI`. Si des avertissements sont détectés, la génération échoue.

Les serveurs CI populaires définissent déjà la variable d’environnement `CI` par défaut, mais vous pouvez le faire vous-même :

### <a name="on-ci-servers"></a>Sur les serveurs CI
#### <a name="travis-ci"></a>Travis CI

1. Suivez le guide de mise en route de [Travis](https://docs.travis-ci.com/user/getting-started/) pour la synchronisation de votre référentiel GitHub avec Travis.  Vous devrez peut-être initialiser certains paramètres manuellement dans la page de votre [profil](https://travis-ci.org/profile).
1. Ajoutez un fichier `.travis.yml` à votre référentiel Git.
```
language: node_js
node_js:
  - 6
cache:
  directories:
    - node_modules
script:
  - npm run build
  - npm test
```
1. Déclenchez votre première génération avec un push Git.
1. [Personnalisez votre build Travis CI](https://docs.travis-ci.com/user/customizing-the-build/) si nécessaire.

#### <a name="circleci"></a>CircleCI

Suivez [cet article](https://medium.com/@knowbody/circleci-and-zeits-now-sh-c9b7eebcd3c1) pour configurer CircleCI avec un projet Create React App.

### <a name="on-your-own-environment"></a>Dans votre propre environnement
##### <a name="windows-cmdexe"></a>Windows (cmd.exe)

```cmd
set CI=true&&npm test
```

```cmd
set CI=true&&npm run build
```

(Remarque : l’absence d’espace blanc est intentionnelle.)

##### <a name="windows-powershell"></a>Windows (Powershell)

```Powershell
($env:CI = $true) -and (npm test)
```

```Powershell
($env:CI = $true) -and (npm run build)
```

##### <a name="linux-macos-bash"></a>Linux, macOS (Bash)

```bash
CI=true npm test
```

```bash
CI=true npm run build
```

La commande de test force Jest à exécuter des tests une fois au lieu de lancer l’observateur.

>  Si vous procédez souvent ainsi en développement, veuillez [signaler un problème](https://github.com/facebookincubator/create-react-app/issues/new) pour nous faire part de votre cas d’utilisation, car nous souhaitons faire de l’observateur la meilleure expérience et être en mesure de changer son fonctionnement pour gérer davantage de flux de travail.

La commande de génération vérifie les avertissements linter et échoue si des avertissements sont détectés.

### <a name="disabling-jsdom"></a>Désactivation de jsdom

Par défaut, le `package.json` du projet généré se présente comme suit :

```js
  "scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test --env=jsdom"
```

Si vous savez qu’aucun de vos tests ne dépend de [jsdom](https://github.com/tmpvar/jsdom), vous pouvez supprimer `--env=jsdom` en toute sécurité et vos tests s’exécuteront plus rapidement :

```diff
  "scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
-   "test": "react-scripts test --env=jsdom"
+   "test": "react-scripts test"
```

Pour vous aider, voici une liste d’API qui **nécessitent jsdom** :

* Tous les globaux de navigateur comme `window` et `document`
* [`ReactDOM.render()`](https://facebook.github.io/react/docs/top-level-api.html#reactdom.render)
* [`TestUtils.renderIntoDocument()`](https://facebook.github.io/react/docs/test-utils.html#renderintodocument) ([un raccourci](https://github.com/facebook/react/blob/34761cf9a252964abfaab6faf74d473ad95d1f21/src/test/ReactTestUtils.js#L83-L91) pour les éléments ci-dessus)
* [`mount()`](http://airbnb.io/enzyme/docs/api/mount.html) dans [Enzyme](http://airbnb.io/enzyme/index.html)

En revanche, **jsdom n’est pas nécessaire** pour les API suivantes :

* [`TestUtils.createRenderer()`](https://facebook.github.io/react/docs/test-utils.html#shallow-rendering) (rendu superficiel)
* [`shallow()`](http://airbnb.io/enzyme/docs/api/shallow.html) dans [Enzyme](http://airbnb.io/enzyme/index.html)

Enfin, jsdom n’est pas non plus nécessaire pour les [tests d’instantané](http://facebook.github.io/jest/blog/2016/07/27/jest-14.html).

### <a name="snapshot-testing"></a>Test d’instantané

Les tests d’instantanés sont une fonctionnalité de Jest qui génère automatiquement des instantanés de texte de vos composants et les enregistre sur le disque. Ainsi, si la sortie de l’interface utilisateur change, vous êtes notifié sans écrire manuellement les assertions sur la sortie du composant. [En savoir plus sur les tests d’instantané.](http://facebook.github.io/jest/blog/2016/07/27/jest-14.html)

### <a name="editor-integration"></a>Intégration de l’éditeur

Si vous utilisez [Visual Studio Code](https://code.visualstudio.com), il existe une [extension Jest](https://github.com/orta/vscode-jest) qui fonctionne avec Create React App et êst prête à l’emploi. Cela fournit de nombreuses fonctionnalités de type IDE tout en utilisant un éditeur de texte : l’affichage de l’état d’une série de tests avec des messages d’échec potentiels inline, le démarrage et l’arrêt automatiques de l’observateur et l’offre de mises à jour d’instantanés en un clic.

![Préversion de Jest pour VS Code](https://cloud.githubusercontent.com/assets/49038/20795349/a032308a-b7c8-11e6-9b34-7eeac781003f.png)

## <a name="debugging-tests"></a>Débogage des tests

Il existe plusieurs façons de configurer un débogueur pour vos tests Jest. Nous aborderons le débogage dans Chrome et [Visual Studio Code](https://code.visualstudio.com/).

>Remarque : les tests de débogage nécessitent Node 8 ou une version ultérieure.

### <a name="debugging-tests-in-chrome"></a>Débogage de tests dans Chrome

Ajoutez ce qui suit à la section `scripts` dans le `package.json` de votre projet
```json
"scripts": {
    "test:debug": "react-scripts --inspect-brk test --runInBand --env=jsdom"
  }
```
Placez des instructions `debugger;` dans n’importe quel test et exécutez :
```bash
$ npm run test:debug
```

Cela démarre l’exécution de vos tests Jest, mais s’interrompt avant l’exécution pour permettre à un débogueur de s’attacher au processus.

Ouvrez les éléments suivants dans Chrome.
```
about:inspect
```

Une fois ce lien ouvert, les Outils de développement Chrome s’affichent. Sélectionnez `inspect` sur votre processus et un point d’arrêt est défini sur la première ligne du script React (cette opération est effectuée simplement pour vous laisser le temps d’ouvrir les outils de développement et d’empêcher Jest de s’exécuter avant que vous n’ayez le temps de le faire). Cliquez sur le bouton qui ressemble à un bouton « lecture » dans le coin supérieur droit de l’écran pour poursuivre l’exécution. Quand Jest exécute le test qui contient l’instruction du débogueur, l’exécution s’interrompt et vous pouvez examiner la portée actuelle et la pile des appels.

>Remarque : l’option CLI --runInBand vérifie que Jest exécute un test dans le même processus plutôt que de générer des processus pour des tests individuels. Normalement, Jest parallélise les séries de tests sur plusieurs processus, mais il est difficile de déboguer plusieurs processus en même temps.

### <a name="debugging-tests-in-visual-studio-code"></a>Débogage de tests dans Visual Studio Code

Le débogage des tests Jest est pris en charge pour [Visual Studio Code](https://code.visualstudio.com).

Utilisez le fichier de configuration [`launch.json`](https://code.visualstudio.com/docs/editor/debugging#_launch-configurations) suivant :
```
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Debug CRA Tests",
      "type": "node",
      "request": "launch",
      "runtimeExecutable": "${workspaceRoot}/node_modules/.bin/react-scripts",      
      "args": [
        "test",
        "--runInBand",
        "--no-cache",
        "--env=jsdom"
      ],
      "cwd": "${workspaceRoot}",
      "protocol": "inspector",
      "console": "integratedTerminal",
      "internalConsoleOptions": "neverOpen"
    }
  ]
}
```

## <a name="developing-components-in-isolation"></a>Développement de composants dans Isolation

En règle générale, dans une application, vous avez un grand nombre de composants d’interface utilisateur et chacun d’eux a de nombreux états différents.
Par exemple, un composant bouton simple peut avoir les états suivants :

* Dans un état normal, avec une étiquette de texte.
* Dans le mode désactivé.
* Dans un état de chargement.

En règle générale, il est difficile de voir ces états sans exécuter un exemple d’application ou quelques exemples.

Create React App n’inclut pas d’outils pour cette option par défaut, mais vous pouvez facilement ajouter [Storybook pour React](https://storybook.js.org) ([source](https://github.com/storybooks/storybook)) ou [React Styleguidist](https://react-styleguidist.js.org/) ([source](https://github.com/styleguidist/react-styleguidist)) à votre projet. **Il s’agit d’outils tiers qui vous permettent de développer des composants et de voir tous leurs états de façon isolée de votre application**.

![Démonstration Storybook pour React](http://i.imgur.com/7CIAWpB.gif)

Vous pouvez également déployer votre Storybook ou votre guide de style en tant qu’application statique. De cette façon, tous les membres de votre équipe peuvent afficher et examiner différents états des composants d’interface utilisateur sans démarrer un serveur principal ni créer un compte dans votre application.

### <a name="getting-started-with-storybook"></a>Prise en main de Storybook

Storybook est un environnement de développement pour les composants d’interface utilisateur React. Il vous permet de parcourir une bibliothèque de composants, d’afficher les différents états de chaque composant et de développer et de tester des composants de manière interactive.

Tout d’abord, installez le package npm suivant globalement :

```sh
npm install -g @storybook/cli
```

Ensuite, exécutez la commande suivante dans le répertoire de votre application :

```sh
getstorybook
```

Ensuite, suivez les instructions à l'écran.

En savoir plus sur React Storybook :

* Capture vidéo : [Prise en main avec React Storybook](https://egghead.io/lessons/react-getting-started-with-react-storybook)
* [Référentiel GitHub](https://github.com/storybooks/storybook)
* [Documentation](https://storybook.js.org/basics/introduction/)
* [Interface utilisateur de test d’instantané](https://github.com/storybooks/storybook/tree/master/addons/storyshots) avec Storybook + addon/storyshot

### <a name="getting-started-with-styleguidist"></a>Prise en main de Styleguidist

Styleguidist combine un guide de style, où tous vos composants sont présentés sur une seule page avec leur documentation et des exemples d’utilisation, avec un environnement de développement de composants isolé, similaire à Storybook. Dans Styleguidist, vous écrivez des exemples dans Markdown, où chaque extrait de code est restitué en tant que playground modifiable dynamique.

Tout d’abord, installez Styleguidist :

```sh
npm install --save react-styleguidist
```

Vous pouvez aussi utiliser `yarn` :

```sh
yarn add react-styleguidist
```

Ensuite, ajoutez ces scripts à votre `package.json` :

```diff
   "scripts": {
+    "styleguide": "styleguidist server",
+    "styleguide:build": "styleguidist build",
     "start": "react-scripts start",
```

Ensuite, exécutez la commande suivante dans le répertoire de votre application :

```sh
npm run styleguide
```

Ensuite, suivez les instructions à l'écran.

En savoir plus sur React Styleguidist :

* [Référentiel GitHub](https://github.com/styleguidist/react-styleguidist)
* [Documentation](https://react-styleguidist.js.org/docs/getting-started.html)

## <a name="publishing-components-to-npm"></a>Publication de composants sur npm

Create React App ne fournit pas de fonctionnalité intégrée pour publier un composant sur npm. Si vous êtes prêt à extraire un composant de votre projet afin que d’autres personnes puissent l’utiliser, nous vous recommandons de le déplacer vers un autre répertoire en dehors de votre projet, puis d’utiliser un outil tel que [nwb](https://github.com/insin/nwb#react-components-and-libraries) pour le préparer à la publication.

## <a name="making-a-progressive-web-app"></a>Création d’une application web progressive

Par défaut, la build de production est une [application web progressive](https://developers.google.com/web/progressive-web-apps/), entièrement fonctionnelle et hors ligne avant tout.

Les applications web progressives sont plus rapides et plus fiables que les pages web traditionnelles et offrent une expérience mobile attrayante :

 * Toutes les ressources de sites statiques sont mises en cache afin que votre page se charge rapidement lors des visites suivantes, quelle que soit la connectivité réseau (par exemple, 2G ou 3G). Les mises à jour sont téléchargées en arrière-plan.
 * Votre application fonctionnera quel que soit l’état du réseau, même si elle est hors connexion. Cela signifie que vos utilisateurs seront en mesure d’utiliser votre application depuis un avion ou dans le métro.
 * Sur les appareils mobiles, votre application peut être ajoutée directement à l’écran d’accueil de l’utilisateur, à l’icône d’application et à tout le reste. Vous pouvez également réimpliquer les utilisateurs à l’aide de **notifications push** web. Cela élimine le besoin de l’App Store.

Le [`sw-precache-webpack-plugin`](https://github.com/goldhand/sw-precache-webpack-plugin) est intégré à la configuration de production et s’occupe de la génération d’un fichier de Worker du service qui met automatiquement en cache toutes vos ressources locales et les met à jour lorsque vous déployez des mises à jour.
Le Worker du service utilise une [stratégie de mise en cache en premier](https://developers.google.com/web/fundamentals/instant-and-offline/offline-cookbook/#cache-falling-back-to-network) pour gérer toutes les demandes de ressources locales, y compris le code HTML initial, garantissant ainsi que votre application web est rapidement fiable, même sur un réseau lent ou non fiable.

### <a name="opting-out-of-caching"></a>Désactivation de la mise en cache

Si vous préférez ne pas activer les Workers de service avant votre déploiement de production initial, supprimez l’appel à `serviceWorkerRegistration.register()` à partir de [`src/index.js`](src/index.js).

Si vous aviez précédemment activé les Workers de service dans votre déploiement de production et que vous avez décidé de les désactiver pour tous vos utilisateurs existants, vous pouvez échanger l’appel à `serviceWorkerRegistration.register()` dans [`src/index.js`](src/index.js) avec un appel à `serviceWorkerRegistration.unregister()`.
Une fois que l’utilisateur a visité une page qui possède `serviceWorkerRegistration.unregister()`, le Worker du service est désinstallé. Notez que, selon la façon dont `/service-worker.js` est servi, l’invalidation du cache peut prendre jusqu’à 24 heures.

### <a name="offline-first-considerations"></a>Considérations relatives au « hors ligne avant tout »

1. Les Workers de service [nécessitent le protocole HTTPS](https://developers.google.com/web/fundamentals/getting-started/primers/service-workers#you_need_https), bien que pour faciliter les tests locaux, cette stratégie [ne s’applique pas à `localhost`](http://stackoverflow.com/questions/34160509/options-for-testing-service-workers-via-http/34161385#34161385).
Si votre serveur web de production ne prend pas en charge le protocole HTTPS, l’inscription du Worker du service échouera, mais le reste de votre application web restera opérationnel.

1. Les Workers de service [ne sont actuellement pas pris en charge](https://jakearchibald.github.io/isserviceworkerready/) dans tous les navigateurs web. L’inscription du Worker du service [n’est pas tentée](src/registerServiceWorker.js) sur les navigateurs qui n’ont pas de support.

1. Le Worker du service est activé uniquement dans l’[environnement de production](#deployment), par exemple la sortie de `npm run build`. Il est recommandé de ne pas activer un Worker du service « hors ligne avant tout » dans un environnement de développement, car cela peut entraîner une certaine frustration quand des ressources mises en cache précédemment sont utilisées et n’incluent pas les dernières modifications apportées localement.

1. Si vous avez *besoin* de tester localement votre Worker du service « hors ligne avant tout », générez l’application (à l’aide de `npm run build`) et exécutez un serveur HTTP simple à partir de votre répertoire de build. Après avoir exécuté le script de génération, `create-react-app` fournit des instructions pour tester votre build de production localement et les [instructions de déploiement](#deployment) ont des instructions pour l’utilisation d’autres méthodes. *Veillez à toujours utiliser une fenêtre incognito pour éviter les complications avec le cache de votre navigateur.*

1. Si possible, configurez votre environnement de production pour traiter le `service-worker.js` généré [avec la mise en cache HTTP désactivée](http://stackoverflow.com/questions/38843970/service-worker-javascript-update-frequency-every-24-hours).
Si ce n’est pas possible ([GitHub Pages](#github-pages) par exemple ne vous permet pas de modifier la durée de vie du cache HTTP par défaut de 10 minutes), sachez que si vous visitez votre site de production et que vous revisitez ensuite à nouveau avant l’expiration de `service-worker.js` de votre cache HTTP, vous continuerez à obtenir les ressources précédemment mises en cache du Worker du service. Si vous avez un besoin immédiat d’afficher votre déploiement de production mis à jour, l’exécution d’une opération Maj-actualiser désactive temporairement le Worker du service et récupère toutes les ressources du réseau.

1. Les utilisateurs ne sont pas toujours familiarisés avec les applications web en mode hors ligne avant tout. Il peut être utile de [laisser l’utilisateur savoir](https://developers.google.com/web/fundamentals/instant-and-offline/offline-ux#inform_the_user_when_the_app_is_ready_for_offline_consumption) quand le Worker du service a fini de remplir vos caches (en indiquant « Cette application web fonctionne hors connexion ! ». ) et aussi de les informer lorsque le Worker du service a récupéré les dernières mises à jour qui seront disponibles lors de la prochaine charge de la page (en indiquant « Nouveau contenu disponible. Veuillez actualiser. » s’afficher). L’affichage de ces messages est actuellement laissé en tant qu’exercice pour le développeur, mais comme point de départ, vous pouvez utiliser la logique incluse dans [`src/registerServiceWorker.js`](src/registerServiceWorker.js), qui montre les événements du cycle de vie du Worker du service à écouter pour détecter chaque scénario et qui, par défaut, enregistre simplement les messages appropriés dans la console JavaScript.

1. Par défaut, le fichier de Worker du service généré n’intercepte pas et ne met en cache aucun trafic Cross-Origin, comme les [demandes d’API](#integrating-with-an-api-backend) HTTP, les images ou les contenus incorporés chargés à partir d’un autre domaine. Si vous souhaitez utiliser une stratégie de mise en cache du runtime pour ces demandes, vous pouvez [`eject`](#npm-run-eject) puis configurer l’option [`runtimeCaching`](https://github.com/GoogleChrome/sw-precache#runtimecaching-arrayobject)
dans la section `SWPrecacheWebpackPlugin` de [`webpack.config.prod.js`](../config/webpack.config.prod.js).

### <a name="progressive-web-app-metadata"></a>Métadonnées de l’application web progressive

La configuration par défaut inclut un manifeste d’application web situé dans [`public/manifest.json`](public/manifest.json), que vous pouvez personnaliser avec des détails spécifiques à votre application web.

Quand un utilisateur ajoute une application web à son écran d’accueil à l’aide de Chrome ou de Firefox sur Android, les métadonnées dans [`manifest.json`](public/manifest.json) déterminent les icônes, noms et couleurs de personnalisation à utiliser lors de l’affichage de l’application web.
Le [Guide du manifeste de l’application web](https://developers.google.com/web/fundamentals/engage-and-retain/web-app-manifest/) fournit plus de contexte sur ce que signifie chaque champ, et la façon dont vos personnalisations affectent l’expérience de vos utilisateurs.

## <a name="analyzing-the-bundle-size"></a>Analyse de la taille du bundle

L’[Explorateur de mappage de source](https://www.npmjs.com/package/source-map-explorer) analyse les lots JavaScript à l’aide des mappages de sources. Cela vous permet de comprendre l’origine du « gonflement » du code.

Pour ajouter l’explorateur de mappages de source à un projet Create React App, procédez comme suit :

```sh
npm install --save source-map-explorer
```

Vous pouvez aussi utiliser `yarn` :

```sh
yarn add source-map-explorer
```

Ensuite, dans `package.json`, ajoutez la ligne suivante à `scripts` :

```diff
   "scripts": {
+    "analyze": "source-map-explorer build/static/js/main.*",
     "start": "react-scripts start",
     "build": "react-scripts build",
     "test": "react-scripts test --env=jsdom",
```

Ensuite, pour analyser le bundle, exécutez la build production, puis exécutez le script d’analyse.

```
npm run build
npm run analyze
```

## <a name="deployment"></a>Déploiement

`npm run build` crée un répertoire `build` avec une version de production de votre application. Configurez votre serveur HTTP préféré de manière à ce qu’un visiteur de votre site voit `index.html`, et que les demandes de chemins d’accès statiques telles que `/static/js/main.<hash>.js` soient traitées avec le contenu du fichier `/static/js/main.<hash>.js`.

### <a name="static-server"></a>Serveur statique

Pour les environnements qui utilisent [Node](https://nodejs.org/), le moyen le plus simple de gérer cela consiste à installer [serve](https://github.com/zeit/serve) et à lui permettre de gérer le reste :

```sh
npm install -g serve
serve -s build
```

La dernière commande illustrée ci-dessus servira votre site statique sur le port **5000**. Comme beaucoup de paramètres internes [serve](https://github.com/zeit/serve), le port peut être ajusté à l’aide des indicateurs `-p` ou `--port`.

Exécutez cette commande pour obtenir la liste complète des options disponibles :

```sh
serve -h
```

### <a name="other-solutions"></a>Autres solutions

Vous n’avez pas nécessairement besoin d’un serveur statique pour exécuter un projet Create React App en production. Cela fonctionne tout aussi bien dans une intégration dynamique existante.

Voici un exemple de programmation utilisant [Node](https://nodejs.org/) et [Express](http://expressjs.com/) :

```javascript
const express = require('express');
const path = require('path');
const app = express();

app.use(express.static(path.join(__dirname, 'build')));

app.get('/', function (req, res) {
  res.sendFile(path.join(__dirname, 'build', 'index.html'));
});

app.listen(9000);
```

Le choix de votre logiciel serveur n’est pas non plus important. Comme Create React App est totalement indépendant des plateformes, il n’est pas nécessaire d’utiliser explicitement Node.

Le dossier `build` avec des ressources statiques est la seule sortie produite par Create React App.

Toutefois, cela n’est pas assez suffisant si vous utilisez le routage côté client. Lisez la section suivante si vous souhaitez prendre en charge des URL comme `/todos/42` dans votre application à page unique.

### <a name="serving-apps-with-client-side-routing"></a>Gérer des applications avec le routage côté client

Si vous utilisez des routeurs qui utilisent l’[API d’historique HTML5 `pushState`](https://developer.mozilla.org/docs/Web/API/History_API#Adding_and_modifying_history_entries) en coulisses (par exemple, [React Routeur](https://github.com/ReactTraining/react-router) avec `browserHistory`), de nombreux serveurs de fichiers statiques échouent. Par exemple, si vous avez utilisé React Routeur avec un itinéraire pour `/todos/42`, le serveur de développement répondra à `localhost:3000/todos/42` correctement, ce qui n’est pas le as avec Express servant une version de production comme ci-dessus.

En effet, lorsqu’une nouvelle page est chargée pour un `/todos/42`, le serveur recherche le fichier `build/todos/42` et ne le trouve pas. Le serveur doit être configuré pour répondre à une demande à `/todos/42` en servant `index.html`. Par exemple, nous pouvons modifier notre exemple Express ci-dessus pour servir `index.html` pour les chemins d’accès inconnus :

```diff
 app.use(express.static(path.join(__dirname, 'build')));

-app.get('/', function (req, res) {
+app.get('/*', function (req, res) {
   res.sendFile(path.join(__dirname, 'build', 'index.html'));
 });
```

Si vous utilisez [Apache HTTP Server](https://httpd.apache.org/), vous devez créer un fichier `.htaccess` dans le dossier `public` qui ressemble à ceci :

```
    Options -MultiViews
    RewriteEngine On
    RewriteCond %{REQUEST_FILENAME} !-f
    RewriteRule ^ index.html [QSA,L]
```

Il sera copié dans le dossier `build` quand vous exécuterez `npm run build`. 

Si vous utilisez [Apache Tomcat](http://tomcat.apache.org/), vous devez suivre [cette réponse Stack Overflow](https://stackoverflow.com/a/41249464/4878474).

Les demandes à `/todos/42` sont maintenant gérées correctement à la fois en développement et en production.

Dans une version de production et dans un navigateur qui prend en charge les [Workers de service](https://developers.google.com/web/fundamentals/getting-started/primers/service-workers), le Worker du service gère automatiquement toutes les demandes de navigation, comme pour `/todos/42`, en servant la copie mise en cache de votre `index.html`. Ce routage de navigation du Worker du service peut être configuré ou désactivé par [`eject`ing](#npm-run-eject) puis en modifiant les options [`navigateFallback`](https://github.com/GoogleChrome/sw-precache#navigatefallback-string)
et [`navigateFallbackWhitelist`](https://github.com/GoogleChrome/sw-precache#navigatefallbackwhitelist-arrayregexp) de la `SWPreachePlugin` [configuration](../config/webpack.config.prod.js).

### <a name="building-for-relative-paths"></a>Génération de chemins d’accès relatifs

Par défaut, Create React App génère une build en supposant que votre application est hébergée à la racine du serveur.<br>
Pour remplacer cela, spécifiez `homepage` dans votre `package.json`, par exemple :

```js
  "homepage": "http://mywebsite.com/relativepath",
```

Cela permet à Create React App de déduire correctement le chemin d’accès racine à utiliser dans le fichier HTML généré.

**Remarque** : si vous utilisez `react-router@^4`, vous pouvez rooter des `<Link>` à l’aide de la proposition `basename` sur tout `<Router>`.<br>
Plus d’informations [ici](https://reacttraining.com/react-router/web/api/BrowserRouter/basename-string).<br>
<br>
Par exemple :
```js
<BrowserRouter basename="/calendar"/>
<Link to="/today"/> // renders <a href="/calendar/today">
```

#### <a name="serving-the-same-build-from-different-paths"></a>Utilisation de la même build à partir de différents chemins

>Remarque : cette fonctionnalité est disponible avec `react-scripts@0.9.0` et les versions ultérieures.

Si vous n’utilisez pas l’API d’historique `pushState` HTML5 ou si vous n’utilisez pas du tout le routage côté client, il est inutile de spécifier l’URL à partir de laquelle votre application sera servie. Au lieu de cela, vous pouvez placer ceci dans votre `package.json` :

```js
  "homepage": ".",
```

Cela permet de s’assurer que tous les chemins d’accès aux ressources sont relatifs à `index.html`. Vous pourrez alors déplacer votre application de `http://mywebsite.com` vers `http://mywebsite.com/relativepath` ou même `http://mywebsite.com/relative/path` sans avoir à la régénérer.

### <a name="azure"></a>Azure

Consultez [ce](https://medium.com/@to_pe/deploying-create-react-app-on-microsoft-azure-c0f6686a4321) billet de blog sur la manière de déployer votre application React sur [Microsoft Azure](https://azure.microsoft.com/).

### <a name="firebase"></a>Firebase

Consultez [ce](https://medium.com/@strid/host-create-react-app-on-azure-986bc40d5bf2#.pycfnafbg) billet de blog ou [ce](https://github.com/ulrikaugustsson/azure-appservice-static) référentiel pour un moyen d’utiliser le déploiement automatique sur Azure App Service.


Installez l’interface de commande de Firebase si vous ne l’avez pas déjà fait en exécutant `npm install -g firebase-tools`. Inscrivez-vous pour obtenir un [compte Firebase](https://console.firebase.google.com/) et créer un nouveau projet. Exécutez `firebase login` et connectez-vous avec votre compte Firebase créé précédemment.

Exécutez ensuite la commande `firebase init` à partir de la racine de votre projet. Vous devez choisir l’**Hébergement : Configurer et déployer des sites d’hébergement Firebase** et choisir le projet Firebase que vous avez créé à l’étape précédente. Vous devez accepter de créer `database.rules.json`, choisir `build` comme répertoire public et accepter de **configurer en tant qu’application à page unique** en répondant à `y`.

```sh
    === Project Setup

    First, let's associate this project directory with a Firebase project.
    You can create multiple project aliases by running firebase use --add,
    but for now we'll just set up a default project.

    ? What Firebase project do you want to associate as default? Example app (example-app-fd690)

    === Database Setup

    Firebase Realtime Database Rules allow you to define how your data should be
    structured and when your data can be read from and written to.

    ? What file should be used for Database Rules? database.rules.json
    ✔  Database Rules for example-app-fd690 have been downloaded to database.rules.json.
    Future modifications to database.rules.json will update Database Rules when you run
    firebase deploy.

    === Hosting Setup

    Your public directory is the folder (relative to your project directory) that
    will contain Hosting assets to uploaded with firebase deploy. If you
    have a build process for your assets, use your build's output directory.

    ? What do you want to use as your public directory? build
    ? Configure as a single-page app (rewrite all urls to /index.html)? Yes
    ✔  Wrote build/index.html

    i  Writing configuration info to firebase.json...
    i  Writing project information to .firebaserc...

    ✔  Firebase initialization complete!
```

IMPORTANT : vous devez définir des en-têtes de mise en cache HTTP appropriés pour le fichier `service-worker.js` dans le fichier `firebase.json`. Sinon, vous ne pourrez pas voir les modifications après le premier déploiement ([problème #2440](https://github.com/facebookincubator/create-react-app/issues/2440)). Cela doit être ajouté à l’intérieur de la clé `"hosting"`, comme suit :

```
{
  "hosting": {
    ...
    "headers": [
      {"source": "/service-worker.js", "headers": [{"key": "Cache-Control", "value": "no-cache"}]}
    ]
    ...
```

Maintenant, après avoir créé une build de production avec `npm run build`, vous pouvez la déployer en exécutant `firebase deploy`.

```sh
    === Deploying to 'example-app-fd690'...

    i  deploying database, hosting
    ✔  database: rules ready to deploy.
    i  hosting: preparing build directory for upload...
    Uploading: [==============================          ] 75%✔  hosting: build folder uploaded successfully
    ✔  hosting: 8 files uploaded successfully
    i  starting release process (may take several minutes)...

    ✔  Deploy complete!

    Project Console: https://console.firebase.google.com/project/example-app-fd690/overview
    Hosting URL: https://example-app-fd690.firebaseapp.com
```

Pour plus d’informations, consultez [Ajouter Firebase à votre projet JavaScript](https://firebase.google.com/docs/web/setup).

### <a name="github-pages"></a>GitHub Pages

>Remarque : cette fonctionnalité est disponible avec `react-scripts@0.2.0` et les versions ultérieures.

#### <a name="step-1-add-homepage-to-packagejson"></a>Étape 1 : Ajouter `homepage` à `package.json`

**L’étape ci-dessous est importante.**<br>
**Si vous l’ignorez, votre application ne sera pas déployée correctement.**

Ouvrez votre `package.json` et ajoutez un champ `homepage` pour votre projet :

```json
  "homepage": "https://myusername.github.io/my-app",
```

ou pour une page utilisateur GitHub :

```json
  "homepage": "https://myusername.github.io",
```

Create React App utilise le champ `homepage` pour déterminer l’URL racine dans le fichier HTML généré.

#### <a name="step-2-install-gh-pages-and-add-deploy-to-scripts-in-packagejson"></a>Étape 2 : Installer `gh-pages` et ajouter `deploy` à `scripts` dans `package.json`

Maintenant, chaque fois que vous exécutez `npm run build`, vous verrez une aide-mémoire avec des instructions sur la façon de déployer sur GitHub Pages.

Pour publier à l’adresse [https://myusername.github.io/my-app](https://myusername.github.io/my-app), exécutez :

```sh
npm install --save gh-pages
```

Vous pouvez aussi utiliser `yarn` :

```sh
yarn add gh-pages
```

Ajoutez les scripts suivants dans votre `package.json` :

```diff
  "scripts": {
+   "predeploy": "npm run build",
+   "deploy": "gh-pages -d build",
    "start": "react-scripts start",
    "build": "react-scripts build",
```

Le script `predeploy` s’exécutera automatiquement avant l’exécution de `deploy`.

Si vous déployez sur une page d’utilisateur GitHub plutôt que sur une page de projet, vous devez apporter deux modifications supplémentaires :

1. Tout d’abord, modifiez la branche source de votre référentiel pour qu’elle soit une branche autre que **principale**.
1. En outre, ajustez vos scripts `package.json` pour effectuer des déploiements push sur la branche **principale** :
```diff
  "scripts": {
    "predeploy": "npm run build",
-   "deploy": "gh-pages -d build",
+   "deploy": "gh-pages -b master -d build",
```

#### <a name="step-3-deploy-the-site-by-running-npm-run-deploy"></a>Étape 3 : Déployer le site en exécutant `npm run deploy`

Ensuite, exécutez :

```sh
npm run deploy
```

#### <a name="step-4-ensure-your-projects-settings-use-gh-pages"></a>Étape 4 : Vérifier que les paramètres de votre projet utilisent `gh-pages`

Enfin, assurez-vous que l’option **GitHub Pages** dans vos paramètres de projet GitHub est définie pour utiliser la branche `gh-pages` :

<img src="http://i.imgur.com/HUjEr9l.png" width="500" alt="gh-pages branch setting">

#### <a name="step-5-optionally-configure-the-domain"></a>Étape 5 : Configurer le domaine (facultatif)

Vous pouvez configurer un domaine personnalisé avec GitHub Pages en ajoutant un fichier `CNAME` au dossier `public/`.

#### <a name="notes-on-client-side-routing"></a>Remarques sur le routage côté client

GitHub Pages ne prend pas en charge les routeurs qui utilisent l’API d’historique HTML5 `pushState` en coulisses (par exemple, React Routeur utilisant `browserHistory`). En effet, lorsqu’il y a un nouveau chargement de page pour une URL telle que `http://user.github.io/todomvc/todos/42`, où `/todos/42` est un itinéraire frontal, le serveur GitHub Pages retourne l’erreur 404, car il ne sait rien de `/todos/42`. Si vous souhaitez ajouter un routeur à un projet hébergé sur GitHub Pages, voici quelques solutions :

* Vous pouvez basculer de l’API d’historique HTML5 au routage avec hachages. Si vous utilisez React Routeur, vous pouvez basculer vers `hashHistory` pour obtenir cet effet, mais l’URL sera plus longue et plus détaillée (par exemple, `http://user.github.io/todomvc/#/todos/42?_k=yknaj`). [En savoir plus](https://reacttraining.com/react-router/web/api/Router) sur les différentes implémentations d’historique dans React Routeur.
* Vous pouvez également utiliser une astuce pour apprendre à GitHub Pages à gérer une erreur 404 en redirigeant vers votre page `index.html` avec un paramètre de redirection spécial. Vous devez ajouter un fichier `404.html` avec le code de redirection dans le dossier `build` avant de déployer votre projet, et vous devez ajouter le code qui gère le paramètre de redirection à `index.html`. Vous trouverez une explication détaillée de cette technique dans ce [guide](https://github.com/rafrex/spa-github-pages).

<<<<<<< HEAD
### <a name="heroku"></a>Heroku
=======
#### <a name="troubleshooting"></a>Dépannage

##### <a name="devtty-no-such-a-device-or-address"></a>« /dev/tty : aucun périphérique ou adresse de ce type »

Si, lors du déploiement, vous recevez `/dev/tty: No such a device or address` ou une erreur similaire, essayez ce qui suit :

1. Créez un [jeton d’accès personnel](https://github.com/settings/tokens).
2. `git remote set-url origin https://<user>:<token>@github.com/<user>/<repo>` .
3. Essayez `npm run deploy again`.

### <a name="heroku"></a>[Heroku](https://www.heroku.com/)
>>>>>>> dfbc71ce2ae07547a8544cce14a1a23fac99e071

Utilisez le [Buildpack Heroku pour Create React App](https://github.com/mars/create-react-app-buildpack).<br>
Vous trouverez des instructions sur le [déploiement de React avec une configuration nulle](https://blog.heroku.com/deploying-react-with-zero-configuration).

#### <a name="resolving-heroku-deployment-errors"></a>Résolution des erreurs de déploiement de Heroku

Parfois `npm run build` fonctionne localement mais échoue pendant le déploiement via Heroku. Voici les cas les plus courants :

##### <a name="module-not-found-error-cannot-resolve-file-or-directory"></a>« Module introuvable : erreur : impossible de résoudre le fichier ou le répertoire »

Si vous obtenez quelque chose qui ressemble à ceci :

```
remote: Failed to create a production build. Reason:
remote: Module not found: Error: Cannot resolve 'file' or 'directory'
MyDirectory in /tmp/build_1234/src
```

Cela signifie que vous devez vous assurer que la casse du fichier ou du répertoire que vous `import` correspond à celui que vous voyez sur votre système de fichiers ou sur GitHub.

Cela est important, car Linux (le système d’exploitation utilisé par Heroku) respecte la casse. Ainsi, `MyDirectory` et `mydirectory` sont deux répertoires distincts. Par conséquent, même si le projet est généré localement, la différence au niveau de la casse interrompt les instructions `import` sur les composants distants de Heroku.

##### <a name="could-not-find-a-required-file"></a>« Impossible de trouver un fichier requis ».

Si vous excluez ou ignorez les fichiers nécessaires du package, une erreur similaire à celle-ci s’affiche :

```
remote: Could not find a required file.
remote:   Name: `index.html`
remote:   Searched in: /tmp/build_a2875fc163b209225122d68916f1d4df/public
remote:
remote: npm ERR! Linux 3.13.0-105-generic
remote: npm ERR! argv "/tmp/build_a2875fc163b209225122d68916f1d4df/.heroku/node/bin/node" "/tmp/build_a2875fc163b209225122d68916f1d4df/.heroku/node/bin/npm" "run" "build"
```

Dans ce cas, assurez-vous que le fichier existe bien avec la casse appropriée et qu’il n’est pas ignoré sur votre `.gitignore` ou `~/.gitignore_global` local.

### <a name="netlify"></a>Netlify

**Pour effectuer un déploiement manuel sur le CDN de Netlify :**

```sh
npm install netlify-cli -g
netlify deploy
```

Choisissez `build` comme chemin d’accès à déployer.

**Pour configurer la livraison continue :**

Avec cette installation, Netlify va générer et déployer lorsque vous effectuerez un push dans Git ou ouvrirez une demande de tirage :

1. [Démarrer un nouveau projet netlify](https://app.netlify.com/signup)
2. Choisissez votre service d’hébergement Git et sélectionnez votre référentiel.
3. Définissez `yarn build` comme commande de génération et `build` comme répertoire de publication.
4. Cliquez sur `Deploy site`

**Prise en charge du routage côté client :**

Pour prendre en charge `pushState`, veillez à créer un fichier `public/_redirects` avec les règles de réécriture suivantes :

```
/*  /index.html  200
```

Lorsque vous allez générer le projet, Create React App va placer le contenu du dossier `public` dans la sortie de la génération.

### <a name="now"></a>maintenant

[now](https://zeit.co/now) offre un déploiement à commande unique sans configuration. Vous pouvez utiliser `now` pour déployer votre application gratuitement.

1. Installez l’outil en ligne de commande `now` à l’aide de l’[outil de bureau](https://zeit.co/download) recommandé ou via Node avec `npm install -g now`.

2. Générez votre application en exécutant `npm run build`.

3. Accédez au répertoire de build en exécutant `cd build`.

4. Exécutez `now --name your-project-name` à partir du répertoire de build. Vous verrez une URL **now.sh** dans votre sortie comme suit :

    ```
    > Ready! https://your-project-name-tpspyhtdtk.now.sh (copied to clipboard)
    ```

    Collez cette URL dans votre navigateur une fois la génération terminée, et vous verrez votre application déployée.

Les détails sont disponibles dans [cet article.](https://zeit.co/blog/unlimited-static)

### <a name="s3-and-cloudfront"></a>S3 et CloudFront

Consultez ce [billet de blog](https://medium.com/@omgwtfmarc/deploying-create-react-app-to-s3-or-cloudfront-48dae4ce0af) sur la manière de déployer votre application React sur Amazon Web Services [S3](https://aws.amazon.com/s3) et [CloudFront](https://aws.amazon.com/cloudfront/).

### <a name="surge"></a>Surge

Installez l’interface de commande de Surge si vous ne l’avez pas déjà fait en exécutant `npm install -g surge`. Exécutez la commande `surge` et connectez-vous ou créez un nouveau compte.

Quand vous êtes invité à indiquer le chemin d’accès au projet, veillez à spécifier le dossier `build`, par exemple :

```sh
       project path: /path/to/project/build
```

Notez que pour prendre en charge les routeurs qui utilisent l’API `pushState` HTML5, vous souhaiterez peut-être renommer `index.html` dans votre dossier de builds en `200.html` avant de procéder au déploiement sur Surge. Cela [garantit que chaque URL revient à ce fichier](https://surge.sh/help/adding-a-200-page-for-client-side-routing).

## <a name="advanced-configuration"></a>Configuration avancée

Vous pouvez ajuster différents paramètres de développement et de production en définissant les variables d’environnement dans votre shell ou avec [.env](#adding-development-environment-variables-in-env).

Variable | Développement | Production | Utilisation
:--- | :---: | :---: | :---
NAVIGATEUR | :white_check_mark: | :x: | Par défaut, Create React App ouvre le navigateur système par défaut, en privilégiant Chrome sur macOS. Spécifiez un [navigateur](https://github.com/sindresorhus/opn#app) pour remplacer ce comportement ou affectez-lui la valeur `none` pour le désactiver complètement. Si vous avez besoin de personnaliser la façon dont le navigateur est lancé, vous pouvez spécifier un script Node à la place. Les arguments passés à `npm start` sont également passés à ce script, et l’URL où votre application est servie est le dernier argument. Le nom de fichier de votre script doit avoir l’extension `.js`.
HOST | :white_check_mark: | :x: | Par défaut, le serveur web de développement se lie à `localhost`. Vous pouvez utiliser cette variable pour spécifier un autre hôte.
PORT | :white_check_mark: | :x: | Par défaut, le serveur web de développement tente d’écouter sur le port 3000 ou vous invite à essayer le port disponible suivant. Vous pouvez utiliser cette variable pour spécifier un port différent.
HTTPS | :white_check_mark: | :x: | Si la valeur est `true`, Create React App exécutera le serveur de développement en mode `https`.
PUBLIC_URL | :x: | :white_check_mark: | Create React App suppose que votre application est hébergée sur la racine du serveur web exécuté ou sur un sous-chemin, comme indiqué dans [`package.json` (`homepage`)](#building-for-relative-paths). Normalement, Create React App ignore le nom d’hôte. Vous pouvez utiliser cette variable pour forcer le renvoi des ressources textuellement à l’URL que vous fournissez (nom d’hôte inclus). Cela peut s’avérer particulièrement utile lors de l’utilisation d’un CDN pour héberger votre application.
CI | :large_orange_diamond: | :white_check_mark: | Quand la valeur est `true`, Create React App traite les avertissements comme des échecs dans la build. Cela fait également que la série de tests n’espionne pas. La plupart des CI définissent cet indicateur par défaut.
REACT_EDITOR | :white_check_mark: | :x: | Quand une application se bloque en cours de développement, vous voyez une erreur avec une pile cliquable dessus. Lorsque vous cliquez dessus, Create React App tente de déterminer l’éditeur que vous utilisez en fonction des processus en cours d’exécution, puis ouvre le fichier source approprié. Vous pouvez [envoyer une requête de tirage pour détecter l’éditeur de votre choix](https://github.com/facebookincubator/create-react-app/issues/2636). La définition de cette variable d’environnement remplace la détection automatique. Si vous procédez ainsi, assurez-vous que votre variable d’environnement de [chemin d’accès](https://en.wikipedia.org/wiki/PATH_(variable)) système pointe vers le dossier bin de votre éditeur. Vous pouvez également le définir sur `none` pour le désactiver complètement.
CHOKIDAR_USEPOLLING | :white_check_mark: | :x: | Lorsque la valeur est `true`, l’observateur est exécuté en mode d’interrogation, si nécessaire, à l’intérieur d’une machine virtuelle. Utilisez cette option si `npm start` ne détecte pas les modifications.
GENERATE_SOURCEMAP | :x: | :white_check_mark: | Lorsque la valeur est `false`, les mappages de source ne sont pas générés pour une génération de production. Cela permet de résoudre les problèmes de mémoire insuffisante sur certaines machines de petite taille.
NODE_PATH | :white_check_mark: |  :white_check_mark: | Identique à [`NODE_PATH` dans Node.js](https://nodejs.org/api/modules.html#modules_loading_from_the_global_folders), mais seuls les dossiers relatifs sont autorisés. Peut être pratique pour émuler une configuration à un seul référentiel en définissant `NODE_PATH=src`.

## <a name="troubleshooting"></a>Dépannage

### <a name="npm-start-doesnt-detect-changes"></a>`npm start` ne détecte pas les modifications.

Lorsque vous enregistrez un fichier pendant que `npm start` est en cours d’exécution, le navigateur doit s’actualiser avec le code mis à jour.<br>
Si cela ne se produit pas, essayez l’une des solutions suivantes :

* Si votre projet se trouve dans un dossier Dropbox, essayez de le déplacer.
* Si l’observateur ne voit pas de fichier nommé `index.js` et que vous y faites référence par le nom de dossier, vous [devez redémarrer l’observateur](https://github.com/facebookincubator/create-react-app/issues/1164) en raison d’un bogue de WebPack.
* Certains éditeurs comme Vim et IntelliJ disposent d’une fonctionnalité d’écriture sécurisée qui interrompt actuellement l’observateur. Vous devez la désactiver. Suivez les instructions de la [section « Ajustement de votre éditeur de texte »](https://webpack.js.org/guides/development/#adjusting-your-text-editor).
* Si le chemin d’accès de votre projet contient des parenthèses, essayez de déplacer le projet vers un chemin d’accès sans celles-ci. Cela est dû à un [bogue de l’observateur WebPack](https://github.com/webpack/watchpack/issues/42).
* Sur Linux et macOS, vous devrez peut-être [modifier les paramètres système](https://github.com/webpack/docs/wiki/troubleshooting#not-enough-watchers) pour autoriser un plus grand nombre d’observateurs.
* Si le projet s’exécute à l’intérieur d’une machine virtuelle telle que (un Vagrant provisionné) VirtualBox, créez un fichier `.env` dans le répertoire de votre projet s’il n’existe pas, puis ajoutez-lui `CHOKIDAR_USEPOLLING=true`. Cela garantit que la prochaine fois que vous exécutez `npm start`, l’observateur utilise le mode d’interrogation, si nécessaire, à l’intérieur d’une machine virtuelle.

Si aucune de ces solutions n’aide, laissez un commentaire [dans ce thread](https://github.com/facebookincubator/create-react-app/issues/659).

### <a name="npm-test-hangs-on-macos-sierra"></a>`npm test` se bloque sur macOS Sierra

Si vous exécutez `npm test` et que la console se bloque après l’impression de `react-scripts test --env=jsdom` sur la console, il se peut qu’il y ait un problème avec votre installation de [Watchman](https://facebook.github.io/watchman/), comme décrit dans [facebookincubator/create-react-app#713](https://github.com/facebookincubator/create-react-app/issues/713).

Nous vous recommandons d’abord de supprimer `node_modules` dans votre projet et d’exécuter `npm install` (ou `yarn` si vous l’utilisez) en premier. Si ce n’est pas le cas, vous pouvez essayer l’une des nombreuses solutions de contournement mentionnées dans les problèmes suivants :

* [facebook/jest#1767](https://github.com/facebook/jest/issues/1767)
* [facebook/watchman#358](https://github.com/facebook/watchman/issues/358)
* [ember-cli/ember-cli#6259](https://github.com/ember-cli/ember-cli/issues/6259)

Il a été signalé que l’installation de Watchman 4.7.0 ou plus récent résout le problème. Si vous utilisez [Homebrew](http://brew.sh/), vous pouvez exécuter ces commandes pour le mettre à jour :

```
watchman shutdown-server
brew update
brew reinstall watchman
```

Vous trouverez d’[autres méthodes d’installation](https://facebook.github.io/watchman/docs/install.html#build-install) dans la page de documentation de Watchman.

Si cela ne vous aide toujours pas, essayez d’exécuter `launchctl unload -F ~/Library/LaunchAgents/com.github.facebook.watchman.plist`.

Il y a également des rapports indiquant que la *désinstallation* de Watchman corrige le problème. Si rien d’autre ne vous aide, supprimez-le de votre système, puis réessayez.

### <a name="npm-run-build-exits-too-early"></a>`npm run build` s’arrête trop tôt

Nous avons reçu un commentaire indiquant que `npm run build` peut échouer sur des ordinateurs ayant une mémoire limitée et aucun espace d’échange, ce qui est courant dans les environnements cloud. Même avec les petits projets, cette commande peut augmenter l’utilisation de la RAM dans votre système de plusieurs centaines de mégaoctets. Par conséquent, si vous disposez de moins de 1 Go de mémoire disponible, votre génération risque d’échouer avec le message suivant :

>  La génération a échoué, car le processus s’est terminé trop tôt. Cela signifie probablement que le système manque de mémoire ou que quelqu’un a appelé `kill -9` sur le processus.

Si vous êtes certain que vous n’avez pas terminé le processus, envisagez d’ajouter de l’[espace d’échange](https://www.digitalocean.com/community/tutorials/how-to-add-swap-on-ubuntu-14-04) à l’ordinateur sur lequel vous effectuez la génération ou générez le projet localement.

### <a name="npm-run-build-fails-on-heroku"></a>`npm run build` échoue sur Heroku

Il peut s’agir d’un problème avec les noms de fichiers sensibles à la casse.
Veuillez consulter [cette section](#resolving-heroku-deployment-errors).

### <a name="momentjs-locales-are-missing"></a>Des paramètres régionaux Moment.js sont manquants

Si vous utilisez [Moment.js](https://momentjs.com/), vous remarquerez peut-être que seuls les paramètres régionaux anglais sont disponibles par défaut. Cela est dû au fait que les fichiers de paramètres régionaux sont volumineux et que vous n’avez probablement besoin que d’un sous-ensemble de [tous les paramètres régionaux fournis par Moment.js](https://momentjs.com/#multiple-locale-support).

Pour ajouter des paramètres régionaux Moment.js spécifiques à votre bundle, vous devez les importer explicitement.<br>
Par exemple :

```js
import moment from 'moment';
import 'moment/locale/fr';
```

Si vous importez plusieurs paramètres régionaux de cette manière, vous pouvez passer de l’un à l’autre en appelant `moment.locale()` avec le nom de paramètres régionaux :

```js
import moment from 'moment';
import 'moment/locale/fr';
import 'moment/locale/es';

// ...

moment.locale('fr');
```

Cela ne fonctionne que pour les paramètres régionaux explicitement importés avant.

### <a name="npm-run-build-fails-to-minify"></a>`npm run build` ne peut pas minifier

Il se peut qu’un package dont vous dépendez ait besoin d’une compilation ou livre du code pour un environnement autre que le navigateur.<br>
Cela est considéré comme une mauvaise pratique dans l’écosystème et n’a pas de trappe d’échappement dans Create React App.<br>
<br>
Pour résoudre ce problème :
1. Ouvrez un problème sur le dispositif de suivi des problèmes de la dépendance et demandez à ce que le package publié soit précompilé (en conservant les modules ES6).
2. Dupliquez le package et publiez vous-même une version corrigée.
3. Si la dépendance est suffisamment petite, copiez-la dans votre dossier `src/` et traitez-la en tant que code d’application.

À l’avenir, nous pourrions commencer à compiler automatiquement des modules tiers incompatibles, mais cela n’est pas pris en charge actuellement. Cette approche ralentirait également les builds de production.

## <a name="alternatives-to-ejecting"></a>Alternatives à l’éjection

L’[éjection](#npm-run-eject) vous permet de personnaliser tout, mais à partir de là, vous devez maintenir la configuration et les scripts vous-même. Cela peut s’avérer décourageant si vous avez de nombreux projets similaires. Dans ce cas, au lieu d’éjecter, nous vous recommandons de *répliquer* `react-scripts` et d’autres packages dont vous avez besoin. [Cet article](https://auth0.com/blog/how-to-configure-create-react-app/) explique comment le faire en détail. Vous trouverez plus d’informations dans [ce problème](https://github.com/facebookincubator/create-react-app/issues/682).

## <a name="something-missing"></a>Des éléments sont manquants ?

Si vous avez des idées de recettes pratiques à ajouter à cette page, [faites-le nous savoir](https://github.com/facebookincubator/create-react-app/issues) ou [proposez-nous-en !](https://github.com/facebookincubator/create-react-app/edit/master/packages/react-scripts/template/README.md)
