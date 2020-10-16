---
layout: post
title:  "Et Lottie, on en pense quoi à Studio HB ?"
author: celinechamiot
categories:
  - Développement
image: 2020/10/article_celine.png
---

Les animations ont une place importante dans le design et la conception d’une solution digitale, l’animation rend le produit plus attractif et permet de créer du lien émotionnel avec l’utilisateur. À Studio HB on se pose souvent la question de quelles solutions mettre en place sur nos projets et pour quels besoins, essayons de nous éclairer sur le sujet avec cet article.

## De quelles animations on parle exactement ?

Avant de commencer dans le vif du sujet précisons de quels genres d’animations on va parler !

On peut séparer les animations web en deux grandes familles :

- Animations à but “illustratives”

{% include image.html img="2020/10/orange.gif" caption="Animation tirée du compte dribble Kankan" %}

- Animations immersives (parallaxe, rollover, zoom au scroll)

Les éléments évoqués dans cet article ne concerne pas les animations du deuxième groupes et feront peut-être l’objet d’un deuxième article dédié à ce sujet.

## Petit point historique sur les "animations" dans le web

Pour mieux comprendre faisons un point historique sur ce qu’il s’est passé dans le web concernant les animations. Il y a quelques années de ça, Flash était une des seules technologies permettant de faire des animations dans une page web (ok boomer si tu travaillais déjà dans le web à cette époque). Et pourtant, même si la technologie a été de plus en plus abandonnée depuis l’arrivé du HTML5 et CSS3, les techniques d’animations sont restées et ont été adaptées aux nouveaux standards du web par la suite.

### Les animations avec les sprites

Elles ont été encore beaucoup utilisées avec du javascript moderne et sont le vestige de ce que faisaient les intégrateurs flash à l’époque.

{% include image.html img="2020/10/sprite.jpg" caption="Exemple d’un magnifique sprite de pigeons" %}

### Les animations avec des gifs

Mais aussi, on n'oublie pas notre ami le gif, qui a eu lui aussi son heure de gloire dans l’utilisation de site web comme moyen plus rapide d’ajouter un petit plus interactif.

{% include image.html img="2020/10/baymax.gif" caption="Animation tirée du compte dribble BombashLin" %}

Ces deux dernières solutions ont des inconvénients, le premier utilise des images très volumineuses souvent en png et alourdit le chargement du site. Le gif est lui aussi un format d’image assez lourd et visuellement il compresse les couleurs qui ne donne jamais une très bonne qualité d’animation par rapport au reste du site (sans oublier qu’on ne peut pas utiliser de gif sur fond transparent)

## Et en 2020 comment intègre-t-on des animations complexes sans passer par le GIF ?

Trois options s'offrent à nous :

### 1. Utiliser une vidéo en boucle 💔

Dans certains cas utiliser une vidéo peut sembler une bonne solution si c’est un cas isolé sur le site, attention toutefois elle peut rapidement surcharger le site s'il s'agit d’ajouter plusieurs animations il faudra passer sur une autre solution.

### 2. Créer les animations “from scratch” 🔥💜

Avec les keyframes CSS ou en utilisant des librairies d’animations comme [GSAP](https://greensock.com/gsap/) à partir d’une intention d’animation par un designer.

C’est la solution la plus personnalisable mais le temps investi par le développeur et le designer peut vite devenir onéreux pour un projet. Il faut aussi une certaine expertise du développeur en javascript pour arriver à reproduire les animations. On ne peut également pas utiliser le même code sur plusieurs plateforme (si par exemple le client possède une application native et un site internet).

<p class="codepen" data-height="300" data-theme-id="light" data-default-tab="html,result" data-user="opendeal" data-slug-hash="vYOZbNg" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="Drawn path keyframe  css ">
  <span>See the Pen <a href="https://codepen.io/opendeal/pen/vYOZbNg">
  Drawn path keyframe  css </a> by Chamiot Céline (<a href="https://codepen.io/opendeal">@opendeal</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>

### 3. Utiliser un outil comme Lottie et Bodymovin 🔥💜

Pour palier à ces problématiques AirBnB à développé [Lottie](https://airbnb.design/lottie/), sa propre librairie cross plateforme (iOS, Android, React Native et web) qui permet de lancer des animations à partir d’un fichier json exporté depuis le plugin [Bodymovin](https://exchange.adobe.com/creativecloud.details.12557.html) d’after effects.

En développant cette librairie AirBnB avait pour but de :

- Simplifier les échanges entre les designers et les développeurs
- Proposer une solution rapide et moins onéreuse d’animation (à l’instar du gif mais en mieux)
- Améliorer le temps de chargement en utilisant des canvas et du vectoriel à la place des sprites png
- Pouvoir interagir en code avec l’animation

## Passons à la pratique ! On vous montre comment on a appliqué cette méthode pour notre projet [MOHOM](https://www.mohom.com/notre-story) avec Lottie

Illustration page \"Notre Story\" du projet [MOHOM](https://www.mohom.com/notre-story) 

<p class="codepen" data-height="600" data-theme-id="light" data-default-tab="html,result" data-user="opendeal" data-slug-hash="Bazjxor" style="height: 800px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="Bazjxor">
  <span>See the Pen <a href="https://codepen.io/opendeal/pen/Bazjxor">
  Bazjxor</a> by Chamiot Céline (<a href="https://codepen.io/opendeal">@opendeal</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>

## Que dire à son designer avant qu’il prenne en main Lottie et After Effect ?

Les 5 commandements du designer qui utilise Lottie :

1. [Bodymovin](https://exchange.adobe.com/creativecloud.details.12557.html), tu installeras (sur ton After Effect)
1. Outils de base d'after effect tu utiliseras: [Documentation Lottie](https://airbnb.io/lottie/#/supported-features)
2. Des images SVG tu feras
3. [L'outil de Prévisualisation de Airbnb](https://lottiefiles.com/web-player) tu utiliseras
4. Ton animation tu admireras

## Comment intègre-t-on Lottie avec Vuejs ?

De la même façon que l’utilisation du gif, il y a moins d’efforts à faire côté développement. Le développeur front doit mettre en place le player lottie sur son site au bon endroit et charger le fichier json.

Chez Studio HB on a décidé d'intégrer le player lottie dans un composant qui est hérité par un composant vue.js. Il se charge de lui envoyer le bon fichier json.

Composant vue.js à chaque animation :
```js
<script>
import LottieAnimationBase from '@utils/lottie-animation.js'
import JsonData from '@animations/man.json'

export default {
  extends: LottieAnimationBase,

  data: () => ({ JsonData })
}
</script>
```
Composant du player lottie réutilisable :
```js
import lottie from 'lottie-web'

export default {
  props: {
    height: {
      type: String,
      default: "400px"
    },

    width: {
      type: String,
      default: "100%"
    }
  },

  data () {
    return {
      style: {
        width: this.width,
        height: this.height,
        overflow: 'hidden',
        margin: '0 auto'
      }
    }
  },

  mounted () {
    lottie.loadAnimation({
      container: this.$refs.container,
      renderer: 'svg',
      loop: true,
      autoplay: true,
      animationData: this.JsonData
    }).play()
  },

  render (createElement) {
    return createElement(
      'div',
      {
        ref: 'container',
        style: this.style
      }
    )
  }
}
```

## Conclustion, on valide pour Lottie !

L’utilisation de Lottie est une bonne surprise, la librairie est plutôt simple et rapide à mettre en place et apporte un vrai bénéfice quand il y a plusieurs animations à charger sur le même projet. En revanche, s'il faut charger lottie juste pour un cas isolé il vaudrait mieux essayer de trouver une solution en css ou en javascript.

| Gif | Video | From scratch | Lottie |
| ------ | ------ |------ | ------ |
| Oh no dear, Why ? | C’est lourd, Pas cool | C'est cool et ça prend du temps | C'est cool et ça prend moins de temps |
| 💔 | 💔 | 🔥💜 | 🔥💜 |

Lottie permet d’intégrer la notion de motion design dans la conception de nos futurs sites internet. À Studio HB le retour d’expérience est positif sur le premier projet sur lequel il a été installé, qui nous a permis d’intégrer des animations personnalisées facilement !

<script async src="https://static.codepen.io/assets/embed/ei.js"></script>