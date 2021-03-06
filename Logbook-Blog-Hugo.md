---
title: "logbook du blog sous Hugo"
date: 2018-03-18
lastmod: 2018-03-25
draft: true
hidden: true

---

# Logbook du blog perso avec Hugo

Pense bête et logbook

## Todo

- finaliser migration
	- supprimer wordpress site et service ovh associé
- date a changer en francais dans la toc et l'entete du post
- tweet du post et share qui ne sont pas bons dans chaque post (ou supprimer les liens si pas possible) 
- enlever mon usage (IP only?) de google analytics 


- comment faire mise a jour de victor-hugo (pas cloner, mais du coup download and copie/paste contenu du site ? comment tester compatibilite theme, et contenu?)
- regarder comment checker [update d'un submodule](https://blog.github.com/2016-02-01-working-with-submodules/) ne va pas faire foirer le site - comment tester une nouvelle version , avant mise en prod du nouveau theme?


## References 

- [Disqus admin](https://disqus.com/admin/)

- Quick [reference de markdown](https://en.support.wordpress.com/markdown-quick-reference/)

- Desciption des variables et formats du [front matter](https://gohugo.io/content-management/front-matter/), cad entete/metadata des posts

- Petit [guide de git](http://rogerdudler.github.io/git-guide/index.fr.html)
	- Cmd dans folder local huguesblog.fr
	- Vous pouvez proposer un changement (l'ajouter à l'Index) en exécutant les commandes
		> git add <filename>
		> git add *
		> git add .
		
	- C'est la première étape dans un workflow git basique. Pour valider ces changements, utilisez
		> git commit -m "Message de validation"
	- Le fichier est donc ajouté au HEAD, mais pas encore dans votre dépôt distant. 
	- Vos changements sont maintenant dans le HEAD de la copie de votre dépôt local. Pour les envoyer à votre dépôt distant, exécutez la commande
		> git push origin master
	- Remplacez master par la branche dans laquelle vous souhaitez envoyer vos changements 

- Liste des [commandes victor Hugo](https://github.com/netlify/victor-hugo)
	- Lancer le site en local
		> npm start
	- To build a static version of the website inside the /dist folder, run:
		> npm run build
	- To get a preview of posts or articles not yet published, run:
		> npm run build-preview
	- publish a new post (with draft status in archetype template)
		> hugo new posts/premier.md


### Pour aller plus loin

- [Passez de Jekyll a Hugo](https://jamstatic.fr/2017/06/07/migration-de-jekyll-a-hugo/) contient plus d'explication sur la structure d'un site Hugo

- structure site

  |--site                // Everything in here will be built with hugo
  |  |--content          // Pages and collections - ask if you need extra pages
  |  |--data             // YAML data files with any data for use in examples
  |  |--layouts          // This is where all templates go
  |  |  |--partials      // This is where includes live
  |  |  |--index.html    // The index page
  |  |--static           // Files in here ends up in the public folder
  |--src                 // Files that will pass through the asset pipeline
  |  |--css              // CSS files in the root of this folder will end up in /css/...
  |  |--js               // app.js will be compiled to /app.js with babel


## Log install de Hugo

suivi les instructions d'[install victor Hugo et Netlify](https://www.christopheducamp.com/2017/08/23/victor-hugo-sur-netlify--un-guide-%C3%A9tape-par-%C3%A9tape/) 

- install victor-hugo en clonant
	- version: Hugo Static Site Generator v0.35 windows/amd64 BuildDate: 2018-01-31T10:45:14Z
	- pb besoin de rajouter la ligne de commande vers Hugo dans le Path Windows
	- pb lors de la creation du repo du site => supp dossier .git, j'aurai mieux fait de faire un upload 
	- Quid commment faire mise a jour proprement de victor-hugo (sans clone ?)
- install [cactus theme](https://github.com/nodejh/hugo-theme-cactus-plus) 
	- version: Release v1.1.1 - 04th September 2017
	- fait par clone, mais a entrainer un probleme lors du deploiement avec netlify (en raison du theme) => supprimer theme et creation d'un [submodule](https://gohugo.io/hosting-and-deployment/hosting-on-netlify/)
	- passer pas mal de temps dans la [configuration](https://gohugo.io/getting-started/configuration/) pour faire marcher certains nombres de choses
	- probleme avec le clone, download manuel du theme et rajout au repo manuel (merder en prenant un autre theme, legerement different en plus)
- creer Repo Git
	- renomage du dossier "victor-hugo" en "huguesblog.fr"
	- en fait le clone a empecher de faire l'install (sinon cela serait un push sur github de victorhugo) => enlever les .git pour refaire repo
	- plus tard, je me suis rendu compte que le theme cloné n'a pas été copié, cf haut dessus
	- surpris de ne pas voir tous les fichiers recopier (en particulier, pas de copie des dossiers node-module, et dist) a copier sur github seulement dossiers site, src 
- [Netlify config](https://app.netlify.com/account/sites)
	- probleme initial de production en raison du submodule du theme non gere (cf plus haut)
	- au final, fait download manuel du theme et rajouter dans le dossier theme a la main, avant de le rajouter au repo => netlify passe (envoyer issue a l'auteur)
- ouverture d'un compte [google analytics](https://analytics.google.com) sur le site huguesblog.fr
- ouverture d'un compte disques avec compte google pour website name: huguesblog.disqus le site: https://huguesblog.netlify.com/
- configuration des noms de [domaines de ovh vers netlify](https://www.netlify.com/docs/custom-domains/#dns-configuration)
	- changer baseurl dans config.toml, au final le laisser a "/" et pas a url du site car sinon perte des feuilles de styles
- Migration fini, derniers tests
	- tester google analytics - ok
	- tester disqus - ok
	- rajouter un dossier raw-material dans folder content et le faire ignorer par le build avec ignoreFiles dans config.toml




