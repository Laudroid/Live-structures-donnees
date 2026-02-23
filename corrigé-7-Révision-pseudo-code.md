
# Corrigé Exercice 1

## Séquence + condition simple

### Algorithme

```
Algorithme ResultatEtudiant

Variables :
    prenom : chaîne
    note : réel

Début
    Afficher "Entrer votre prénom : "
    Lire prenom
    
    Afficher "Entrer votre note : "
    Lire note
    
    Si note >= 10 Alors
        Afficher prenom, " est Admis"
    Sinon
        Afficher prenom, " est Ajourné"
    FinSi
Fin
```

---

### Explication

1. On déclare les variables avec leur type.
2. On récupère les entrées utilisateur.
3. On teste la condition `note >= 10`.
4. On affiche le résultat en fonction du test.

✔ Structure séquentielle
✔ Une seule condition
✔ Logique simple

---

---

# Corrigé Exercice 2

## Conditions multiples

### Algorithme

```
Algorithme CategorieAge

Variables :
    age : entier

Début
    Afficher "Entrer votre âge : "
    Lire age
    
    Si age < 12 Alors
        Afficher "Enfant"
        
    SinonSi age >= 12 ET age <= 17 Alors
        Afficher "Adolescent"
        
    SinonSi age >= 18 ET age <= 59 Alors
        Afficher "Adulte"
        
    Sinon
        Afficher "Senior"
    FinSi
Fin
```

---

### Explication

1. On lit l’âge.
2. On vérifie les intervalles **dans l’ordre logique**.
3. Chaque intervalle est exclusif.
4. Le dernier cas (`Sinon`) capture les 60 et plus.

Important :
L’ordre des conditions est essentiel pour éviter les erreurs.

✔ Utilisation de `SinonSi`
✔ Opérateur logique `ET`
✔ Gestion correcte des intervalles

---

---

# Corrigé Exercice 3

## Boucle + accumulation + conditions ordonnées

### Algorithme

```
Algorithme CalculMoyenneMentions

Variables :
    n, i : entier
    note, somme, moyenne : réel

Début
    Afficher "Combien de notes voulez-vous saisir ?"
    Lire n
    
    somme ← 0
    
    Pour i allant de 1 à n Faire
        Afficher "Entrer la note ", i, " : "
        Lire note
        somme ← somme + note
    FinPour
    
    moyenne ← somme / n
    
    Afficher "La moyenne est : ", moyenne
    
    Si moyenne >= 14 Alors
        Afficher "Mention Bien"
        
    SinonSi moyenne >= 12 Alors
        Afficher "Mention Assez Bien"
        
    SinonSi moyenne >= 10 Alors
        Afficher "Passable"
        
    Sinon
        Afficher "Ajourné"
    FinSi
Fin
```

---

## Explication détaillée

### 1️⃣ Initialisation

`somme ← 0`
On initialise l’accumulateur avant la boucle.

---

### 2️⃣ Boucle

```
Pour i allant de 1 à n
```

Permet de répéter la saisie `n` fois.

À chaque tour :

```
somme ← somme + note
```

On ajoute la note à la somme.

---

### 3️⃣ Calcul de la moyenne

```
moyenne ← somme / n
```

---

### 4️⃣ Conditions ordonnées

Très important :
On commence par la condition la plus élevée (`>= 14`)
Sinon la moyenne 15 serait classée "Passable".

Ordre logique décroissant :

* ≥ 14
* ≥ 12
* ≥ 10
* sinon

---

✔ Utilisation d’un accumulateur
✔ Boucle contrôlée
✔ Conditions hiérarchisées
✔ Raisonnement structuré


---

# Bonus – Version avec validation des notes

```
Algorithme MoyenneAvecVerification

Variables :
    n, i : entier
    note, somme, moyenne : réel

Début
    Afficher "Combien de notes ?"
    Lire n
    
    somme ← 0
    
    Pour i allant de 1 à n Faire
        
        Répéter
            Afficher "Entrer une note entre 0 et 20 : "
            Lire note
        JusquA note >= 0 ET note <= 20
        
        somme ← somme + note
        
    FinPour
    
    moyenne ← somme / n
    
    Afficher "Moyenne : ", moyenne
Fin
```

---

# Corrigé Exercice 4 – Factorielle

## Rappel

* 0! = 1
* n! = n × (n − 1)!

---

## Algorithme complet

```
Algorithme ProgrammeFactorielle

Fonction Factorielle(n : entier) : entier
Début
    Si n = 0 Alors
        Retourner 1
    Sinon
        Retourner n * Factorielle(n - 1)
    FinSi
FinFonction


Variables :
    nombre : entier
    resultat : entier

Début
    Afficher "Entrer un nombre : "
    Lire nombre
    
    resultat ← Factorielle(nombre)
    
    Afficher "La factorielle est : ", resultat
Fin
```

---

## Explication détaillée

### 1️⃣ Cas de base (condition d’arrêt)

```
Si n = 0 Alors
    Retourner 1
```

Pourquoi ?

Parce que **0! = 1**.
Sans ce cas, la fonction s’appellerait à l’infini.

Toute fonction récursive doit avoir un cas d’arrêt.

---

### Cas récursif

```
Retourner n * Factorielle(n - 1)
```

La fonction :

* Multiplie `n`
* Appelle elle-même avec `n - 1`
* Se rapproche progressivement du cas de base

---

## Déroulement pour n = 4

Appels successifs :

```
Factorielle(4)
→ 4 * Factorielle(3)
→ 4 * (3 * Factorielle(2))
→ 4 * (3 * (2 * Factorielle(1)))
→ 4 * (3 * (2 * (1 * Factorielle(0))))
→ 4 * (3 * (2 * (1 * 1)))
```

Résultat :

```
4 * 3 * 2 * 1 = 24
```

---

## Ce qu’il faut retenir

✔ Cas de base obligatoire
✔ Appel à soi-même
✔ Chaque appel réduit le problème
✔ La récursion remplace une boucle

---

---

# Corrigé Exercice 5 – Somme des entiers de 1 à n

## Rappel mathématique

```
Somme(n) = n + Somme(n - 1)
```

---

## Algorithme complet

```
Algorithme ProgrammeSomme

Fonction Somme(n : entier) : entier
Début
    Si n = 1 Alors
        Retourner 1
    Sinon
        Retourner n + Somme(n - 1)
    FinSi
FinFonction


Variables :
    nombre : entier
    resultat : entier

Début
    Afficher "Entrer un nombre : "
    Lire nombre
    
    resultat ← Somme(nombre)
    
    Afficher "La somme est : ", resultat
Fin
```

---

## Explication détaillée

### 1️⃣ Cas de base

```
Si n = 1 Alors
    Retourner 1
```

Pourquoi ?

Parce que :

```
Somme(1) = 1
```

C’est le point d’arrêt minimal.

---

### Cas récursif

```
Retourner n + Somme(n - 1)
```

Chaque appel :

* Ajoute `n`
* Diminue la valeur
* Se rapproche de 1

---

## Déroulement pour n = 5

```
Somme(5)
→ 5 + Somme(4)
→ 5 + (4 + Somme(3))
→ 5 + (4 + (3 + Somme(2)))
→ 5 + (4 + (3 + (2 + Somme(1))))
→ 5 + (4 + (3 + (2 + 1)))
```

Résultat :

```
5 + 4 + 3 + 2 + 1 = 15
```
