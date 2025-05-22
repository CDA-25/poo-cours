# Les "classes" LA POO en mode rapide 

---

## 1. Rappel : Objet littéral

En JS, on peut créer un objet directement comme ça :

```js
const voiture = {
  marque: 'Toyota',
  démarrer() {
    console.log("Vroum !");
  }
};

voiture.démarrer(); // Vroum !
```

Simple, rapide
Mais difficile à réutiliser pour créer **plusieurs objets similaires**.

---

## 2. Les classes

Une **classe** sert à créer plusieurs objets "du même type", comme un moule.

```js
class Voiture {
  constructor(marque) {
    this.marque = marque;
  }

  démarrer() {
    console.log(`${this.marque} démarre : Vroum !`);
  }
}

const v1 = new Voiture('Renault');
const v2 = new Voiture('Peugeot');

v1.démarrer(); // Renault démarre : Vroum !
v2.démarrer(); // Peugeot démarre : Vroum !
```

### Que se passe-t-il ici ?

* `class Voiture` : on déclare une classe
* `constructor()` : fonction appelée à la création de l'objet
* `this.marque` : propriété de l’objet
* `new Voiture(...)` : crée un nouvel objet à partir de la classe

---

## 3. Différence principale

| Objet littéral              | Classe / `new`                    |
| --------------------------- | --------------------------------- |
| 1 seul objet                | Crée autant d’objets que tu veux  |
| Pas de réutilisation facile | Classe réutilisable               |
| Pas besoin de `this`        | Utilisation obligatoire de `this` |

---

## 4. Ajout de méthodes dynamiques (bonus avancé)

```js
Voiture.prototype.klaxonner = function() {
  console.log(`${this.marque} fait pouet pouet`);
};

v1.klaxonner(); // Renault fait pouet pouet
```

Mais en général on reste avec la syntaxe **dans la classe**.

---

## À retenir

* **Objet littéral** : simple, direct, 1 seul objet.
* **Classe** : permet de créer plusieurs objets avec le même "modèle".
* `constructor` initialise chaque objet.
* `this` pointe vers **l’instance** créée.
