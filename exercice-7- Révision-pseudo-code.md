
#  Exercice 1 

##  Objectif : Séquence + calcul simple

###  Énoncé

Écrire un algorithme en pseudo-code qui :

1. Demande le prénom d’un étudiant
2. Demande sa note sur 20
3. Affiche :

   * "Admis" si la note est ≥ 10
   * "Ajourné" sinon

---

###  Contraintes

* Utiliser `Lire`
* Utiliser `Afficher`
* Utiliser une structure `Si`

---


# Exercice 2 

## Objectif : Conditions multiples

### Énoncé

Écrire un algorithme qui :

1. Lit l’âge d’un utilisateur
2. Affiche la catégorie correspondante :

* Moins de 12 → "Enfant"
* Entre 12 et 17 → "Adolescent"
* Entre 18 et 59 → "Adulte"
* 60 et plus → "Senior"

---

###  Contraintes

* Utiliser des conditions imbriquées ou `SinonSi`
* Gérer correctement les intervalles
* Éviter les erreurs de logique (chevauchement)

---

# Exercice 3

## Objectif : Boucle + condition + calcul

### Énoncé

Écrire un algorithme qui :

1. Demande combien de notes l’étudiant veut saisir
2. Permet de saisir toutes les notes
3. Calcule la moyenne
4. Affiche :

   * La moyenne
   * "Mention Bien" si moyenne ≥ 14
   * "Mention Assez Bien" si moyenne ≥ 12
   * "Passable" si moyenne ≥ 10
   * "Ajourné" sinon

---

### Contraintes

* Utiliser une boucle `Pour`
* Utiliser un accumulateur (ex : `somme`)
* Gérer correctement les conditions dans le bon ordre

---

# Bonus (Défi pour les plus rapides)

Modifier l’exercice 3 pour :

* Refuser une note si elle est < 0 ou > 20
* Redemander la note tant qu’elle n’est pas valide

Cela nécessite une boucle `TantQue`.

---

# Exercice 4 – Récursion simple

## Objectif : Comprendre le principe d’appel récursif

### Énoncé

Écrire une fonction récursive en pseudo-code qui calcule la **factorielle** d’un nombre entier positif `n`.

Rappel mathématique :

* 0! = 1
* n! = n × (n-1)!

Exemple :
5! = 5 × 4 × 3 × 2 × 1 = 120

---

### Contraintes

* Utiliser une **fonction**
* Définir un **cas de base**
* Définir le **cas récursif**
* Ne pas utiliser de boucle

---

### Indications pédagogiques

Une fonction récursive doit toujours contenir :

1. Un cas d’arrêt (cas de base)
2. Un appel à elle-même
3. Un rapprochement vers le cas de base

---

### Structure attendue

```
Fonction Factorielle(n : entier) : entier
Début
    ...
Fin
```

Puis un programme principal qui :

* Lit un nombre
* Appelle la fonction
* Affiche le résultat

---


# Exercice 5 – Récursion avec condition

## Objectif : Maîtriser la récursion avec logique conditionnelle

### Énoncé

Écrire une fonction récursive qui calcule la **somme des entiers de 1 à n**.

Exemple :

* somme(5) = 1 + 2 + 3 + 4 + 5 = 15
* somme(4) = 10

---

### Contraintes

* Utiliser une fonction récursive
* Interdire l’utilisation d’une boucle
* Gérer correctement le cas de base

---

### Indications pédagogiques

On peut observer que :

```
somme(n) = n + somme(n - 1)
```

Mais il faut définir :

Quand la fonction doit s’arrêter

---

### Structure attendue

```
Fonction Somme(n : entier) : entier
Début
    ...
Fin
```

Puis :

* Lecture de n
* Appel de la fonction
* Affichage du résultat

