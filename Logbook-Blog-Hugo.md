---
title: "logbook du blog sous Hugo"
date: 2018-03-18
lastmod: 2018-03-18
draft: true
hidden: true

---

# Logbook du blog perso avec Hugo

Pense bête et logbook

## Todo

### config site
- trouver le probleme de la page 404 qui n'est pas appelle
- date a changer en francais dans la toc et l'entete du post
- tweet du post et share qui ne sont pas bons dans chaque post
- une fois migration faites
	- config changer baseurl
	- changer le [nom de domaine](https://www.netlify.com/docs/custom-domains/)
- comment faire mise a jour de victor-hugo (pas cloner, mais du coup download and copie/paste contenu du site ? comment tester compatibilite theme, et contenu?)
- regarder comment checker [update d'un submodule](https://blog.github.com/2016-02-01-working-with-submodules/) ne va pas faire foirer le site - comment tester une nouvelle version , avant mise en prod du nouveau theme?
- clean-up dans repo des readme etc

### migration site
- post Connaissance
	- photo center et resizer
	- add video
	- add lien avec post précédent et suivant
- post ...x...


### References 

- Quick [reference de markdown](https://en.support.wordpress.com/markdown-quick-reference/)

- Desciption des variables et formats du [front matter](https://gohugo.io/content-management/front-matter/), cad entete/metadata des posts

- Petit [guide de git](http://rogerdudler.github.io/git-guide/index.fr.html)

- Liste des [commandes victor Hugo](https://github.com/netlify/victor-hugo)
	- Lancer le site en local
		> npm start
	- To build a static version of the website inside the /dist folder, run:
		> npm run build
	- To get a preview of posts or articles not yet published, run:
		> npm run build-preview


#### Pour aller plus loin

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
	- pb lors de la creation du repo du site => supp dossier .git, j'aurai mieux fait de faire un upload 
	- Quid commment faire mise a jour proprement de victor-hugo (sans clone ?)
- install [castus theme](https://github.com/nodejh/hugo-theme-cactus-plus) 
	- version: Release v1.1.1 - 04th September 2017
	- fait par clone, mais a entrainer un probleme lors du deploiement avec netlify (en raison du theme) => supprimer theme et creation d'un [submodule](https://gohugo.io/hosting-and-deployment/hosting-on-netlify/)
	- passer pas mal de temps dans la [configuration](https://gohugo.io/getting-started/configuration/) pour faire marcher certains nombres de choses
- creer Repo Git
	- renomage du dossier "victor-hugo" en "huguesblog.fr"
	- en fait le clone a empecher de faire l'install (sinon cela serait un push sur github de victorhugo) => enlever les .git pour refaire repo
	- plus tard, je me suis rendu compte que le theme cloné n'a pas été copié, cf haut dessus
	- surpris de ne pas voir tous les fichiers recopier (en particulier, pas de copie des dossiers node-module, et dist) a copier sur github seulement dossiers site, src 
- Netlify config
	- probleme initial de production en raison du submodule du theme non gere (cf plus haut)

