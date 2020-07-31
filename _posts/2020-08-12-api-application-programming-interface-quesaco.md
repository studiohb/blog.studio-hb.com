---
title: API, Application Programming Interface, quèsaco ?
layout: post
author: laurentbuffevant
categories:
- Développement
image: -
image_caption: -
---

Vous avez déjà probablement entendu parler d'API. Mais qu'est-ce donc ? Quand et pourquoi en utiliser ? Quels sont les pièges à éviter ? Comment Studio HB peut vous accompagner dans la conception ou la consommation de vos API ?

Suivez le guide, c'est par ici!


## Un moyen de communication ...

Une **API**, **Application Programming Interface** - Interface de Programmation d’Application en français dans le texte - est couramment décrite comme un moyen pour faire communiquer 2 systèmes d'information. Ces systèmes d'information peuvent prendre différentes formes:
* Application mobile
* Site internet
* Base de données
* Logiciel métier
* Terminal de paiement
* ...

Concrètement, une API va par exemple être utilisée pour faire communiquer votre nouvelle application smartphone avec le serveur hébergeant vos données. La même API pouvant être utilisée par votre Site web pour récupérer et mettre à jour ces mêmes données. L'énorme avantage est que les différents systèmes d'informations peuvent être développés dans des langages complètements différents, l'API leur permettra de dialoguer et d'échanger dans un dialecte commun.

Schéma ?

Une API se caractérise toujours par une interface d'entrée (input), et une de sortie (output). En clair, une API va permettre de recevoir une information afin d'en renvoyer une autre en réponse après l'avoir analysée et traitée.

## ... mais pas que !

Vous entendrez souvent le terme de **passerelle**, ou de **webservice** comme synonyme une API. C'est partiellement vrai. Un webservice va permettre la communication de 2 systèmpes d'informations sur un réseau. L'API elle, va plus loin car elle va permettre l'interaction entre 2 systèmes qui peuvent être à l'intérieur d'une même application. Un webservice est par conséquent un type d'API. Il exite donc d'autres types d'API.

Par exemple, pour les plus techniques d'entre vous, on le sait moins mais ActionDispatch qui gère le routage des requêtes HTTP est une API qui permet d'accueillir en entrée une requête HTTP et de la diriger vers le bon Controleur Rails. ActionController est ainsi lui même une API permettant de traiter les informations de la requête, d'appeler d'autres API (ApplicationRecord, Services, Policies, ActionView, etc... ) afin de renvoyer en retour un contenu (HTML, JSON, XML, CSV, etc...) que votre navigateur va pouvoir interpréter.

## Qu'est-ce qu'une bonne API ? Quels sont les pièges à éviter ?

Ce n'est pas tout de vouloir mettre en place des API. Encore faut-il respecter certaines rêgles pour qu'elles soient efficaces et pertinentes.

### Utiliser les normes et protocoles standardisés

Si vous souhaitez que votre API soit facilement utilisée (consommée) par le plus grand nombre il est nécessaire que celle-ci soit développée en suivant certaines normes et protocoles standardisés. Interessons nous principalement aux API web qui sont celles que vous allez principalement rencontrer:

* Le protocole de transport le plus couramment utilisé est HTTP (HTTPS pour la version sécurisée). Ce standard est reconnu et interprété par tous les systèmes d'information existants. Pas de risque d'incompatibilité avec HTTP!
* Des architectures de webservice différentes:
  * **(REST)[https://fr.wikipedia.org/wiki/Representational_state_transfer]** est l'architecture la plus utilisée et la plus connue pour consevoir des API web. La plupart des API ouvertes utilise cette architecture à la fois simple et permettant un large panel de possibilités
  * Depuis quelques années **(GraphQL)[https://www.howtographql.com/]** est une architecture qui vient concurrencer REST. Elle se veut plus performante en terme de ressource et plus adapatée aux écosystèmes Front (Javascript) actuels
  * D'autres architectures tels que **SOAP** ou **XML-RPC** sont parfois utilisées mais tombent de plus en plus en désuétude
* Les formats de réponse doivent également être normalisés:
  * Pour les données on priviligiera **JSON** ou **XML**
  * Pour l'affichage **HTML** est le format le plus connu


### La bonne documentation: Une des clé

Pour être comprise une API doit nécessairement être documentée. Imaginez-vous au téléphone avec un correspondant ne parlant pas un mot de votre langue. Sans un dictionnaire permettant de traduire ce que vous voulez lui demander et ce qu'il va vous répondre, impossible de se comprendre. Avec une API c'est la même chose. Il est impossible de la comprendre sans une bonne documentation. Celle-ci doit être découpée en plusieurs niveaux et sous-niveaux:
* Les protocoles, architectures et format de réponse
* La méthode de connexion et les moyens d'authentification
* Les points d'accès (L'url dans le cas d'une API HTTP) de chacun des flux. Ils doivent contenir:
  * La description du point d'accès
  * Les données / paramètres attendus en entrée et leur descriptifs
  * Les données renvoyées en retour et leurs descriptifs

Impression d'écran venant de https://carredor-partner-api.studio-hb.fr/#req_63f0e5dc542642bca652a291f0679eab ?

## Et chez Studio HB ?

Vous l'aurez compris, chez Studio HB les API c'est notre pain quotidien. Pour nos clients dans l'immobilier par exemple, nous récupérons les biens en vente via une API mise à disposition par les éditeurs de logiciel immobilier ((Apimo)[https://apimo.net/fr/], (Avantio)[https://www.avantio.fr/], (Hektor)[https://www.la-boite-immo.com/logiciel-immobilier.html], etc...).

Pour nos projets nécessitant un paiement en ligne pour un achat ou un abonnement nous allons nous connecter aux API proposées par des banques ((Monetico/CIC)[https://www.monetico-paiement.fr/fr/accueil.html]), ou des intermédiaires bancaires ((Stripe)[https://stripe.com/en-fr], (Systempay)[https://paiement.systempay.fr/doc/fr-FR/]).

Et nous en utilisons pour bien d'autres fonctionnalités (Connexion Réseaux sociaux, Récupération de statistiques Google Analytics, affichage de cartes, etc... )

A l'inverse nous développons également des API pour vos projets afin de communiquer des informations vers l'exterieur ou échanger des données avec d'autres systèmes que vous seriez amené à vouloir utiliser. C'est le cas par exemple pour notre client (Carré d'Or)[https://www.carredor.immo/] où nous avons mis en place une API privée afin d'envoyer le descriptif de certains de leurs programmes sur la plateforme de visite virtuelle (Habiteo)[https://www.habiteo.com/]

Vous l'aurez compris l'équipe de Studio HB vous accompagnera pour la conception ou l'utilisation d'une API pour votre projet. N'hésitez pas à visiter (notre site)[https://www.studio-hb.com/] et (nous contacter)[https://www.studio-hb.com/contactez-nous/new] pour de plus amples informations.

