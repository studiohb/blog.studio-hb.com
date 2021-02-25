---
layout: post
title: "Optimiser le chargement de vos pages web avec 'prefetch', 'preload' et 'preconnect'"
author: benoitbaumann
categories:
- Développement
image: 2021/02/2021_02_23-optimiser-chargement-hero.png
---

Qui n'a pas déjà râlé au moins une fois parce qu'une page internet mettait trop de temps à s'afficher&nbsp;?

Eh oui, à l'heure actuelle, tout va de plus en plus vite, nous sommes devenus impatients et n'aimons plus attendre. Et quand quelque chose prend trop de temps à notre gout, nous allons souvent voir ailleurs. La vitesse de chargement d'un site web est un critère essentiel qui peut avoir de fâcheuses conséquences. Pourtant, il existe des techniques très simples permettant d'optimiser facilement le chargement des pages web. Suivez le guide !

## Pourquoi optimiser ?

Des pages qui mettent trop de temps à s'afficher peuvent faire fuir des utilisateurs et vous faire perdre des clients potentiels. Ce comportement peut se mesurer grâce à un indicateur marketing qui s'appelle le **taux de rebond**. Il représente le pourcentage d'internautes qui sont arrivés sur une page web et qui ont ensuite quitté le site sans avoir consulté d'autres pages. Ce taux reflète bien souvent l'insatisfaction de l'utilisateur. Les sources de cette insatisfaction peuvent être nombreuses mais il est certain q'un *délai de chargement trop long* en fait parti.

Cette insatisfaction a aussi un impact sur un autre indicateur très important : le **taux de conversion**. Ce dernier reflète, quant à lui le pourcentage de visiteurs réalisant une action sur votre site, que ce soit un achat dans le cas d'un site marchand ou le remplissage d'un formulaire de contact/newsletter dans les autres cas.

Mais cela ne s'arrête pas là. Ce serait bien trop beau. Les pages internet lentes à charger sont aussi **les ennemis** des moteurs de recherche et notamment de Google, qui en font la chasse depuis quelques années maintenant en les **pénalisant dans leur référencement naturel** et donc dans leur visibilité au sein des résultats de recherche.

Avant de voir comment optimiser ces temps de chargement, il faut d'abord comprendre ce qu'il se passe sous le capot.

## Mais pourquoi ça met tellement de temps ?!

Une page web peut contenir tout un tas de ressources telles que des images ou vidéos, des polices d'écriture particulière, plusieurs feuilles de style pour définir l'identité visuel de la page mais aussi des scripts ou widgets pour améliorer l'expérience utilisateur et l'interactivité. Qui plus est, ces ressources peuvent être hébergées sur le même serveur que le site que vous visitez ou bien être disponibles à travers des services tiers. Toutes ces ressources *pèsent* un certain poids et doivent être téléchargées par votre navigateur afin d'afficher correctement la page.

Bien entendu, le téléchargement des ressources est une tâche récurrente pour un navigateur (en fait, il passe son temps à faire ça) et se décompose de la manière suivante :

- la résolution DNS de l’origine de la ressource
(si le navigateur ne l’a pas déjà faite)
- la connexion au serveur de cette ressource
(si le navigateur n’est pas déjà connecté)
- le téléchargement de la ressource
(si la ressource n’est pas déjà dans le cache client et est toujours valide)
- et son éventuelle évaluation/exécution et utilisation

Les navigateurs ont fait de nettes améliorations sur ce sujet ces dernières années et sont désormais capables de prioriser certaines ressources en fonction de leur type (contenu principal, image de fond, police d'écriture, etc.). Néanmoins, le résultat n'est pas toujours parfait et peut être amélioré.

Heureusement, les navigateurs ont à disposition quelques outils simples permettant aux développeurs d'optimiser très facilement le chargement de leur pages web.

## Quelques solutions simples à mettre en place

### DNS-prefetch

Il peut arriver que des ressources nécessaires à notre page doivent être téléchargées depuis des services tiers (des polices d'écriture depuis des serveurs de Google ou des feuilles de style/images depuis des CDN par exemple). Pour aider le navigateur à optimiser leur chargement, il existe la directive `dns-prefetch` :

```html
<link rel="dns-prefetch" href="https://fonts.gstatic.com/" >
```

Pour qu'un navigateur puisse se connecter à un site internet, il doit connaitre son adresse IP. Or, tout ce que nous lui donnons comme information est en général l'url du site en question, par exemple *https://www.studio-hb.com*. C'est à ce moment où le service *DNS* entre en jeu. Le *Domaine Name System* ou *DNS* est un service distribué composé de nombreux serveurs répartis partout autour du monde dont le seul but est de traduire des noms de domaine en adresse IP.

Notre navigateur devra donc envoyer une requête à l'un de ces nombreux serveurs DNS à chaque fois qu'il souhaitera se connecter à un domaine internet. Bien que ces requêtes prennent très peu de bande passante, elles peuvent avoir des latences assez élevées, notamment sur les réseaux mobiles de nature plus instables.

Cette directive permet donc de dire au navigateur de commencer à résoudre des noms de domaine qu'on lui aura indiqués (et obtenir leur adresse IP) bien avant qu'il ne détecte qu'il devra se connecter à ses domaines pour télécharger des ressources. Qui plus est, il conservera en *cache* (c'est-à-dire en mémoire) ces adresses IP afin de faciliter et accélérer les futures connections à ces domaines.

Là où cette solution devient intéressante c'est quand notre page possède de *nombreuses ressources provenant de plusieurs domaines internet différents*. Par contre, elle n'offre aucun avantage dans le cas où nos ressources sont stockées sur notre serveur.

### Preconnect

La directive `preconnect` reprend exactement ce que fait `dns-prefetch` mais en allant encore plus loin. En plus de dire au navigateur de résoudre des noms de domaine en avance, elle lui indique aussi d'établir en avance une connexion avec ces domaines, évitant ainsi d'effectuer ces opérations couteuses en temps (TCP handshake et négociation TLS) au moment où ces ressources seront vraiment nécessaires.

```html
<link rel="preconnect" href="https://fonts.gstatic.com/" crossorigin>
```

Cette directive est un outil très important d'optimisation pouvant faire gagner très facilement plusieurs centaines de milli-secondes.

Néanmoins, il faut être sûr que les ressources pour lesquelles nous initions une pré-connexion seront bel et bien utilisées dans notre page, faute de quoi nous augmenterons le temps de chargement au lieu de le diminuer...
De plus, la directive `preconnect` étant plus récente, connait un moins grand support de la part des navigateurs que `dns-prefetch`. Il se peut donc que cette fonctionnalité ne soit pas prise en charge par une partie des visiteurs de votre site utilisant des versions de navigateur non compatibles.

### Prefetch

`prefetch` est une autre technique d'optimisation qui permet d'indiquer au navigateur de télécharger **arrière plan** certaines ressources non nécessaires à la page actuelle de manière **non-prioritaire** et de les **mettre en cache** pour une future utilisation.

```html
<link rel="prefetch" href="image.png">
```

Tout le challenge de cette technique est de pouvoir **anticiper la navigation** de l'utilisateur afin de ne pas charger des ressources pour rien. Dans de nombreux cas, il sera tout bonnement impossible de prévoir avec certitude quelle page il visitera ensuite sauf dans quelques cas précis comme une page de connexion ou des pages à l'intérieur d'un tunnel de paiement ou réservation.

### Preloading

`preload` est un nouveau standard du web permettant de dire au navigateur de traiter certaines ressources comme **hautement prioritaire**, de les **télécharger aussi tôt que possible** et de les **mettre en cache** en attendant leur utilisation future.

```html
<link rel="preload" as="script" href="ultra-high-priority.js">
<link rel="preload" as="style" href="super-duper-important.css">
```

Le mot clé `as` est très important car il indique au navigateur le type de ressource. Ceci lui permet entre-autre de **prioriser plus précisément** les préchargements. Les types de ressources pris en charge sont les suivants:

- font
- script
- style
- image
- media
- document

Contrairement aux autres directives vues plus haut qui sont considérées comme des "*suggestions*" par le navigateur (il peut ne pas les appliquer dans certains cas), `preload` est une **instruction obligatoire**.

`preload` trouve tout son intérêt pour les ressources qui seront utilisées très tôt dans votre page et dont leur priorité est considéré comme basse par défaut par le navigateur.

## Conclusion

Comme nous avons pu le voir ensemble, il est très facile de mettre en place certains outils afin d'optimiser le chargement de nos pages internet. Mais il en existe encore bien d'autres comme l'utilisation de **CDN (Content Delivery Network)** pour vos ressources, la **minification des fichiers javascript et CSS**, **l'optimisation des images et vidéos**, la **compression Gzip**, le **lazy loading** (ou chargement différé) du contenu de votre page, l'utilisation du **protocole HTTPS** et j'en passe...

Chez StudioHb, nous mettons en place ces optimisations sur tout les sites que nous concevons. N'hésitez surtout pas à venir nous consulter, nous serons heureux de discuter de votre projet.
