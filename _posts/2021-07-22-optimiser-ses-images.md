---
layout: post
title: "Pourquoi et comment optimiser les images d’un site Internet ?"
author: celinechamiot
categories:
- Développement front
excerpt: Découvrez pourquoi et comment traiter vos images avant leur publication sur votre site Internet. Céline, développeuse web chez Studio Hb vous explique.
image: 2021/05/choisir-forfait-regie-site-internet.jpg
image_alt: pourquoi et comment optimiser les images pour web
image_caption: "Crédit photo: Talles Alves"
---

**Optimiser ses images** est une action désormais indispensable à effectuer avant leurs publications sur un site Internet. Pourquoi porter une attention si particulière au **traitement des images** ? Quelles sont les différentes méthodes pour **réduire le poids d’une image web** ? Céline, développeuse web chez [Studio HB](https://www.studio-hb.com/) nous a préparé un topo sur ce sujet fondamental.

## Pourquoi est-il important d'optimiser les images pour mon site ?
Il est difficile de s&#39;abstenir de **l’optimisation des images sur son site**. La plupart des outils qui évalue la performance pénalise dans les recherches les sites avec des **images trop lourdes ou au **mauvais format**. Le poids des images sur le total de la page a aussi un impact direct sur **le temps de chargement de la page** et peut **désintéresser très vite l’utilisateur**.

Les avantages principaux à **optimiser les images web** sont donc:

- Une amélioration du **temps de chargement**
- Participe aux critères pris en compte pour le **référencement** du site
- Moins **d’espace de stockage** sur le serveur

<!-- {% include image.html img="2021/06/exemple-couleurs-vives-site-internet.jpg" alt="pourquoi optimiser les images sur un site internet" %}
[https://stmartin.agency/](https://stmartin.agency/) -->

## Et la qualité des images alors ?
Le but du travail **d’optimisation d’images** est de trouver le bon équilibre entre des tailles de fichier plus petites et **la qualité** du rendu sur le site. Il existe deux types de compression. La première, dont on ne peut pas s’abstraire, c’est la **compression “sans perte”** qui va venir **réduire le poids de la photo sans altérer sa qualité**. C’est celle que nous sommes obligés de faire à chaque fois qu’on veut mettre une image sur un site.

Il est ensuite aussi possible de **réduire la qualité à 70% ou 80%** selon le rendu des images si le temps de chargement est toujours trop long. Par défaut, une dégradation de 75% est appliquée sur les photos des back office de Studio HB.

<!-- {% include image.html img="2021/06/exemple-couleurs-vives-site-internet.jpg" alt="Illustration pour la qualité d'image sur le web" %}
[https://stmartin.agency/](https://stmartin.agency/) -->

[Herbert Goetsch](https://unsplash.com/@hg_photo/)

## Le choix du format des images sur son site internet

On trouve principalement deux typologies de formats : les **images vectorielles** et les **images matricielles**. Les images vectorielles sont indépendantes du zoom et de la résolution de l’écran, elles sont le plus souvent retrouvées sur **les icônes et le logo** du site avec **le format SVG**.

Pour les images matricielles, c’est l’inverse. Il faut se préoccuper de la taille et de la **résolution de l’image** sur les formats **JPG, PNG et GIF**. **Le format jpeg** est celui qu’il faut **privilégier impérativement** s'il n’y a pas de transparence sur l’image.

En résumé:
- Le formats de prédilection: JPG, SVG
- Les formats possibles au besoin: PNG, GIF

## Comment déterminer le bon poids pour ma photo ?
Il est difficile de déterminer une règle car le bon poids dépend du format et de la taille de l’image à renseigner. Mais pour donner une idée, **une image de “hero”** en plein format peut faire **aux alentours de 500 ko compressée** et un plus petit format dans la page comme une photo à côté d’un bloc texte sera plutôt aux alentours de 250 ko.

## Le recadrage de la photo

<!-- {% include image.html img="2021/06/exemple-couleurs-vives-site-internet.jpg" alt="3 étapes importantes pour le traitement d'une image" %}
[https://stmartin.agency/](https://stmartin.agency/) -->


### Première étape indispensable avant l'optimisation
**La taille de l’image** à un impact direct sur son poids pour les images JPG et PNG. **Commencer par recadrer les images au bon format** en suivant les indications de tailles fournies dans le back office permet de simplifier grandement toutes les prochaines étapes ! Cela permet aussi de prendre **moins de temps aux outils d’optimisation** lors du passage des algorithmes car les images sont déjà au bon format.

Exemple ! Quand on reçoit des photos venant d’un appareil photo reflex ou d’un photographe, les images peuvent être très grandes comme 5000**5000 px de large ou plus alors que l’image présente sur le site fait 800 px de large.

### Comment recadrer ses photos web
Pour recadrer des photos une par une, il existe des outils en ligne comme [Spark](https://spark.adobe.com/fr-FR/tools/image-resize/) ou plusieurs logiciels comme [Sketch](https://www.sketch.com/), [Figma](https://www.figma.com/), [Photoshop](https://www.adobe.com/fr/products/photoshop.html?mv=search&amp;mv=search&amp;sdid=LZ32SYVR&amp;ef_id=CjwKCAjwz_WGBhA1EiwAUAxIcbEZ7AmG_9qfh1kyO_al7-Dg7CYVpC0Te2RuJqwdYKJxou5Al98ObRoCn44QAvD_BwE:G:s&amp;s_kwcid=AL!3085!3!341240721080!e!!g!!photoshop!1435912275!56537390339&amp;gclid=CjwKCAjwz_WGBhA1EiwAUAxIcbEZ7AmG_9qfh1kyO_al7-Dg7CYVpC0Te2RuJqwdYKJxou5Al98ObRoCn44QAvD_BwE) ou [Gimp](https://www.gimp.org/downloads/).

Sur mac, il est possible de recadrer plusieurs photos à la fois comme expliquer dans ce tutoriel: [recadrer des photos par lot](https://www.youtube.com/watch?v=Qqf2GMrIpf4). En double-cliquant sur une sélection de photo, on arrive sur la vue groupée de photos sur Aperçu. Dans l’onglet Édition, après avoir fait cmd+A, on peut ajuster la taille de plusieurs photos.

## Comment compresser ses images : les différents outils
Chez Studio HB, nous utilisons le logiciel [ImageOptim](https://imageoptim.com/fr) pour **compresser les images** sur nos sites. Nous utilisons les paramètres suivant :

<!-- {% include image.html img="2021/06/exemple-couleurs-vives-site-internet.jpg" alt="paramètre ImageOptim pour compresser les images" %}
[https://stmartin.agency/](https://stmartin.agency/)

image_alt: paramètre ImageOptim pour compresser les images

{% include image.html img="2021/06/exemple-couleurs-vives-site-internet.jpg" alt="paramètre ImageOptim pour optimiser les images par compression" %}
[https://stmartin.agency/](https://stmartin.agency/)

image_alt: paramètre ImageOptim pour optimiser les images par compression

{% include image.html img="2021/06/exemple-couleurs-vives-site-internet.jpg" alt="paramètre ImageOptim de compression d’images" %}
[https://stmartin.agency/](https://stmartin.agency/)

image_alt: paramètre ImageOptim de compression d’images -->

Il existe aussi des **outils de compression d'images en ligne**:

- [Squoosh](https://squoosh.app/) : outil en ligne de Google pour compresser les images JPEG, PNG et SVG
- [Photoshop avec save for web](hhttps://www.adobe.com/fr/products/photoshop.html?mv=search&mv=search&sdid=LZ32SYVR&ef_id=CjwKCAjwz_WGBhA1EiwAUAxIcff9RO5TXUHv5EsVbzfRQvKLIJORcW48LD-HU5fasl7HJnPYovV44RoCUHgQAvD_BwE:G:s&s_kwcid=AL!3085!3!341240721080!e!!g!!photoshop!1435912275!56537390339&gclid=CjwKCAjwz_WGBhA1EiwAUAxIcff9RO5TXUHv5EsVbzfRQvKLIJORcW48LD-HU5fasl7HJnPYovV44RoCUHgQAvD_BwE)
- [Gimp save for web](https://www.gimp.org/downloads/)
- [Tinyjpg](https://www.figma.com/)
- [Tinypng](https://tinypng.com/)
- [Imagify](https://imagify.io/fr)
- [Compressor](https://compressor.io/)

Les outils en ligne sont pratiques mais si vous possédez des photos payantes ou avec des droits d’images, les images sont envoyées sur des **serveurs en ligne** et peuvent donc être consultées par ces services avant d’être traitées.

Optimiser ses images web est donc un processus à intégrer dès le départ en les recadrant puis en les compressant. Améliorer la performance et la rapidité de votre site Internet est un enjeu primordial pour gagner en visibilité et garder vos internautes sur votre site ! Consultez aussi notre article sur [l’optimisation du chargement de vos pages web](https://blog.studio-hb.com/optimiser-le-chargement-de-vos-pages-web/).



