---
title: 'Functional Programming — Currying (Part 6)'
date: '2019-10-22T07:00:00+02:00'
description: ''
---

Avant d'aller plus loin, prenons un peu de temps pour parler de l'**ordre des paramètres** d'une fonction. Vous l'avez peut-être déjà remarqué par vous même, l'ordre des paramètres d'une fonction curriée est **très** important.

Prenons par exemple ces deux fonctions qui font exactement la même chose :

```js
// (a[], a -> b) -> b[]
const map1 = (list, mapFn) => list.map(mapFn);

// (a -> b, a[]) -> b[]
const map2 = (mapFn, list) => list.map(mapFn);
```

La seule différence est l'ordre de ses paramètres. Maintenant, curryfions les :

```js
// a[] -> (a -> b) -> b[]
const curriedMap1 = curry(map1);

// (a -> b) -> a[] -> b[]
const curriedMap2 = curry(map2);
```

Vous pouvez voir ici que le premier paramètre "pré-remplissable" change en fonction de la signature de base, ce qui impacte énormément l'utilité et l'utilisation de la version curriée.

Ici, la première version a une utilité très limitée, car elle permet d'appliquer plusieurs transformations sur la même liste alors que la seconde version permet d'appliquer une transformation donnée sur plusieurs listes.

```js
// Number[] -> Number[]
const divideByTwo = curriedMap2(i => i / 2);
```

La règle générale est de mettre la valeur à transformer / manipuler en dernier dans la liste de paramètres.
