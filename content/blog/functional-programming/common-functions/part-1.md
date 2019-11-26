---
title: 'Functional Programming — Common functions (Part 1)'
date: '2019-10-22T08:00:00+02:00'
description: ''
---

Une des choses très intimidante quand on débute dans la programmation fonctionnelle, c'est le vocabulaire. Beaucoup de termes sembles étrangers et complexes. Essayons de les démystifier un peu.

Voici une liste de fonctions classiques et une implémentation naïve. Certaines ont déjà une implémentation en JavaScript standard, mais il est très utile d'en créer une version fonctionnelle pour la suite.

- `identity` une fonction qui prends un argument et le retourne tel quel. parfois appelé `id`.

```js
// a -> a
const identity = x => x;
```

- `always` une fonction qui prends un argument et retourne une fonction qui retournera toujours cette valeur. Parfois appelé `constant`.

```js
// a -> () -> a
const always = x => () => x;
```

- `map` applique une fonction de transformation a chaque élément d'une collection. Parfois appelé `select`.

```js
// (a -> b) -> a[] -> b[]
const map = mapFn => list => list.map(mapFn);
```

- `filter` filtre une collection avec un prédicat. Parfois appelé `where`.

```js
// (a -> Boolean) -> a[] -> a[]
const filter = filterFn => list => list.filter(filterFn);
```

- `find` trouve la première valeur dans collection qui satisfait un prédicat. Parfois appelé `first`.

```js
// (a -> Boolean) -> a[] -> a
const find = findFn => list => list.find(findFn);
```

- `any` vérifie si au moins un des élément d'une collection satisfais un prédicat. Parfois appelé `some`.

```js
// (a -> Boolean) -> a[] -> Boolean
const any = anyFn => list => list.some(anyFn);
```

- `all` vérifie si tous les éléments d'une collection satisfont un prédicat. Parfois appelé `every`.

```js
// (a -> Boolean) -> a[] -> Boolean
const all = allFn => list => list.every(allFn);
```

- `flatMap`
- `reduce`
