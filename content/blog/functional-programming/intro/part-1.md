---
title: 'Functional Programming — Introduction (Part 1)'
date: '2019-10-21T20:00:00+02:00'
description: ''
---

Bienvenue dans cette introduction à la programmation fonctionnelle !

Avant de commencer, voici quelques pré-requis afin de tout comprendre.

## JavaScript / ES6

Nous allons utiliser JavaScript (et plus particulièrement la version ES6) pour les exemples dans cette introduction. JavaScript est un bon candidat car c'est un langage très dynamique, partiellement fonctionnel qui reste compréhensible par une grande majorité des développeurs familiers avec n'importe quel langage impératif (C#, Java, Python...).

<!-- Si vous ne pensez pas avoir le niveau requis en JS / ES6, n'hésitez pas a suivre les cours dédiés [ici](). -->

Quelques rappels sur ES6:

```js
const list = [1, 2, 3];

// équivalent à console.log(list[0], list[1], list[2])
console.log(...list);

// déclaration d'une fonction anonyme ayant un paramètre "a"
const test = a => console.log(a);

// déclaration d'une fonction anonyme ayant deux paramètres "a" et "b"
const test = (a, b) => console.log(a, b);

// déclaration d'une fonction anonyme ayant n paramètres disponibles dans la collection "args"
const test = (...args) => console.log(...args);

// déclaration d'une fonction anonyme ayant deux paramètres numériques et retournant leur somme
const add = (a, b) => a + b;
// équivalent a
const add = (a, b) => {
  return a + b;
};
```

## Notation de type de fonction

Le javascript ne possédant pas de types explicites, il est parfois difficile de comprendre ce qu'attends une fonction en paramètres et ce qu'elle retourne.

Pour la suite, nous allons utiliser une notation sous forme de commentaire afin d'expliciter la signature des fonctions.

Prenons comme convention quelques types primitifs : `String`, `Number`, `Boolean` et `[]` comme suffixe désignant une collection. Les fonctions sont représentées ainsi : `<arguments> -> <résultat>`.

```js
// (Number, Number) -> Number
const add = (a, b) => a + b;
```

Les lettres telles que `a`, `b`... représentent un type " _non défini_ ". C'est l'équivalent d'un type générique.

```js
// (a, String) -> b
const prop = (obj, propName) => obj[propName];
```

Il est possible de chainer les fonctions comme par exemple : `a -> b -> c`, ce qui signifie _fonction qui prends un `a`, qui retourne une fonction qui prends un `b` qui retourne un `c`_.

```js
// Number -> Number -> Number
const add = a => b => a + b;

// a -> String -> b
const prop = obj => propName => obj[propName];
```
