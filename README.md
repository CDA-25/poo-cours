# La POO en JavaScript

---

# Programmation orientée objet en JavaScript

## 1. Qu'est-ce que la POO ?

> C'est une manière d'organiser ton code autour **d'objets** qui représentent des **choses du monde réel** (voiture, utilisateur, article…).

**Principes clés :**

* **Encapsulation** : cacher les détails internes d'un objet
* **Héritage** : un objet peut hériter d’un autre
* **Polymorphisme** : une méthode peut agir différemment selon l’objet
* **Abstraction** : simplifier ce qui est exposé

---

## 2. JavaScript : POO basée sur des prototypes

Contrairement à PHP (et d'autres langages comme Java, C#...), **JavaScript n'a pas été conçu à la base pour la POO avec des classes**. Il utilise un système de **prototypes**.

Mais depuis ES6, JS a introduit la **syntaxe `class`** pour se rapprocher de ce qu'on connaît en PHP.

---

## 3. Comparaison JS vs PHP

### Création de classe

**JS :**

```js
class Utilisateur {
  constructor(nom) {
    this.nom = nom;
  }

  saluer() {
    console.log(`Bonjour, je suis ${this.nom}`);
  }
}
```

**PHP :**

```php
class Utilisateur {
    private $nom;

    public function __construct($nom) {
        $this->nom = $nom;
    }

    public function saluer() {
        echo "Bonjour, je suis $this->nom";
    }
}
```

### Similitudes :

* Constructeur pour initialiser
* Méthodes dans la classe
* Accès à l’instance via `this` (JS) ou `$this` (PHP)

### ⚠Différences clés :

| Caractéristique              | JavaScript                                                 | PHP                                         |
| ---------------------------- | ---------------------------------------------------------- | ------------------------------------------- |
| Syntaxe des classes          | Ajoutée récemment (ES6)                                    | Native depuis longtemps                     |
| Héritage                     | Via `extends`                                              | Via `extends` aussi                         |
| Visibilité (public, private) | Disponible avec `#` ou `private` (ES2022)                  | Présente (`private`, `protected`, `public`) |
| Typage                       | Dynamique                                                  | Typage plus strict (PHP 7+)                 |
| Objet = fonction             | Les classes JS sont du **sugar syntax** pour les fonctions | Les classes PHP sont réelles                |

---

## 4. Héritage

**JS :**

```js
class Admin extends Utilisateur {
  supprimerUtilisateur() {
    console.log(`${this.nom} supprime un utilisateur`);
  }
}
```

**PHP :**

```php
class Admin extends Utilisateur {
    public function supprimerUtilisateur() {
        echo "$this->nom supprime un utilisateur";
    }
}
```

---

## 5. Encapsulation en JS

JS n’a **pas de vrai `private`** avant ES2022 (avec `#`) :

```js
class Compte {
  #solde = 0;

  deposer(montant) {
    this.#solde += montant;
  }

  afficherSolde() {
    console.log(`Solde: ${this.#solde}`);
  }
}
```

En PHP :

```php
class Compte {
    private $solde = 0;

    public function deposer($montant) {
        $this->solde += $montant;
    }

    public function afficherSolde() {
        echo "Solde: {$this->solde}";
    }
}
```

---

## Conclusion

|                      | JavaScript                     | PHP                           |
| -------------------- | ------------------------------ | ----------------------------- |
| Paradigme par défaut | Prototype                      | Classe                        |
| Héritage             | `extends` (prototypes dessous) | `extends`                     |
| Encapsulation        | `#` (depuis ES2022)            | `private` / `protected`       |
| Typage               | Dynamique                      | Fort / de plus en plus strict |
| Modèle de classe     | Plus souple, plus libre        | Plus strict, plus structuré   |

---
