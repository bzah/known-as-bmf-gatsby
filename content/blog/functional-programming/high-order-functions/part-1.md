---
title: 'Functional Programming — High-Order Functions (Part 1)'
date: '2019-10-21T21:00:00+02:00'
description: ''
---

Dans le paradigme fonctionnel, les fonctions sont des **[objets de première classe](https://fr.wikipedia.org/wiki/Objet_de_premi%C3%A8re_classe)**. Cela signifie qu'elles peuvent être :

- Construites à la volée (aussi appelé **[fonction anonyme ou fonction lambda](https://fr.wikipedia.org/wiki/Fonction_anonyme)**)
- Affectées à des variables
- Utilisées comme paramètre d'une fonction
- Retournées par une fonction

De plus, une fonction qui prends en paramètre une autre fonction ou qui retourne une fonction en résultat est appelée une **[fonction d'ordre supérieur](https://fr.wikipedia.org/wiki/Fonction_d%27ordre_sup%C3%A9rieur)** (high-order function ou hof en anglais).

Tous les critères cités ci-dessus sont remplis en JavaScript.

```js
// construction à la volée et affectation a une variable
// (String, String) -> String
const test = (a, b) => `${a} ${b}!`;

// prends en parametre une fonction et en retourne une
// ((a, b, c, …) -> z) -> (..., c, b, a) -> z
const reverseArgs = fn => (...args) => fn(...args.reverse());

const reversedTest = reverseArgs(test);

console.log(test('hello', 'bmf'));
console.log(reversedTest('hello', 'bmf'));

// > hello bmf!
// > bmf hello!
```
