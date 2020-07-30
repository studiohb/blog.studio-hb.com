---
layout: post
title:  "Optimiser l'utilisation de ses partials avec Rails"
author: guillaumebriday
categories:
  - Développement
image: 2020/04/puzzle.jpg
---

En fonction de comment sont utilisés les partials en Rails, il y a un impact très important sur les performances.

Il faut noter deux trois choses. La différence de performance est de l'ordre `100ms` à `5ms` juste dans le rendering des partials.

## Tous les chemins sont absolus

Cela permet à Rails de ne pas avoir à déviner le chemin et ainsi gagner ce temps de calcul.

```ruby
# Don't
render 'form'

# Do
render 'users/form'
```

## Toujours utiliser le mot-clé collections

Cela va permettre à Rails de mettre en cache la partial en question pour lui injecter les données sans avoir à recalculer le template à chaque fois. C'est surement le gain le plus important.

```ruby
# Don't
- @users.each do |user|
  render 'users/user', user: user

# Do
render partial: 'users/user', collection: @users
```

## Toujours utiliser des variables locales

Utiliser des variables d'instances dans une partials rend difficile la réutilisation de ces dernières. Cela ne nous permettra pas de rendre leur nom générique si besoin, ni d'omettre certaines valeurs en fonction de la situation.

```ruby
# Don't
render 'form'

# Do
render 'form', user: @user
```
