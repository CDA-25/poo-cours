# Prototypage la POO en JS

---

## 🧬 C’est quoi le **prototypage** en JavaScript ?

En JavaScript, **chaque objet hérite d’un autre objet**, qu’on appelle son **prototype**.

Exemple simple :

```js
const humain = {
  parler() {
    console.log("Bonjour !");
  }
};

const john = Object.create(humain);
john.parler(); // Bonjour !
```

🔍 Ici :

* `john` **n’a pas** de méthode `parler` directement
* Mais il **hérite** de `humain`, donc il peut l’utiliser
* JS regarde dans l’objet, puis dans son **prototype** si la méthode existe

> Ce mécanisme s’appelle la **chaîne de prototypes** (prototype chain).

---

## ⚙️ Différence avec la **POO classique** (comme en PHP)

|                   | JavaScript (prototypes)        | PHP / Java (POO classique)    |
| ----------------- | ------------------------------ | ----------------------------- |
| Héritage          | Par prototype                  | Par classe                    |
| Objet enfant      | Crée à partir d’un autre objet | Crée à partir d’une classe    |
| Modèle            | Flexible, modifiable à chaud   | Strict, basé sur un plan fixe |
| Syntaxe de classe | Apparue plus tard (ES6)        | Nativement présente           |

---

## 👨‍🏫 Une comparaison visuelle

### Prototypage (JS natif) :

```js
function Animal(nom) {
  this.nom = nom;
}

Animal.prototype.parler = function() {
  console.log(this.nom + " fait du bruit");
};

const chat = new Animal("Mimi");
chat.parler(); // Mimi fait du bruit
```

### POO classique (comme PHP) :

```php
class Animal {
    public $nom;

    public function __construct($nom) {
        $this->nom = $nom;
    }

    public function parler() {
        echo $this->nom . " fait du bruit";
    }
}

$chat = new Animal("Mimi");
$chat->parler(); // Mimi fait du bruit
```

---

## 📌 À retenir

* JavaScript utilise le **prototypage** pour faire de l’héritage.
* Ce système est **plus souple**, mais **moins strict** que la POO classique.
* Depuis ES6, JS propose des **classes** qui cachent ce système (syntactic sugar), donc tu peux coder en style POO **sans penser aux prototypes**.
* Sous le capot, même avec `class`, **tout reste basé sur les prototypes** !

---
