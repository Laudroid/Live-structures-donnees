Bonjour !

Voici deux propositions de solutions pour le TP "Premiers Pas Algorithmiques - La Mini-Calculatrice". Ces approches illustrent comment décomposer et formaliser un problème simple en utilisant le pseudo-code, une étape fondamentale avant d'aborder des structures de données plus complexes.

---

## Chapitre 1 : Solution 1 - Approche Directe et Explicite

Cette première solution adopte une approche très directe, en détaillant chaque étape de manière explicite, de la lecture des entrées à l'affichage du résultat.

### 1.1 Analyse du Problème

*   **Entrées (Inputs) :**
    *   `nombre1` : Le premier nombre entier à additionner.
    *   `nombre2` : Le second nombre entier à additionner.
*   **Sortie (Output) :**
    *   `somme` : Le résultat de l'addition des deux nombres entiers.
*   **Contraintes :**
    *   Les deux nombres (`nombre1` et `nombre2`) doivent être des entiers.

### 1.2 Conception de l'Algorithme (Pseudo-code)


```
ALGORITHME AdditionSimple
    // Déclaration des variables
    VARIABLE nombre1 : ENTIER
    VARIABLE nombre2 : ENTIER
    VARIABLE somme   : ENTIER

    // Début de l'algorithme
    DEBUT

        // Étape 1 : Lire les entrées fournies par l'utilisateur
        AFFICHER "Veuillez entrer le premier nombre entier :"
        LIRE nombre1

        AFFICHER "Veuillez entrer le second nombre entier :"
        LIRE nombre2

        // Étape 2 : Effectuer l'opération d'addition
        somme <- nombre1 + nombre2

        // Étape 3 : Afficher le résultat
        AFFICHER "La somme de ", nombre1, " et ", nombre2, " est : ", somme

    FIN
```


### 1.3 Test et Validation

Voici deux jeux de valeurs pour tester l'algorithme :

1.  **Jeu de test 1 :**
    *   Entrées : `nombre1` = 5, `nombre2` = 3
    *   Résultat attendu : 8
    *   *Vérification :* 5 + 3 = 8. L'algorithme devrait produire ce résultat.

2.  **Jeu de test 2 :**
    *   Entrées : `nombre1` = -10, `nombre2` = 7
    *   Résultat attendu : -3
    *   *Vérification :* -10 + 7 = -3. L'algorithme devrait gérer correctement les nombres négatifs.

---

## Chapitre 2 : Solution 2 - Approche Fonctionnelle Simplifiée

Cette seconde solution présente l'algorithme sous une forme légèrement plus compacte, en le conceptualisant comme une fonction qui prend des arguments et retourne une valeur, ce qui est une pratique courante en programmation.

### 2.1 Analyse du Problème

*   **Entrées (Inputs) :**
    *   `valeurA` : Le premier opérande entier.
    *   `valeurB` : Le second opérande entier.
*   **Sortie (Output) :**
    *   `resultatAddition` : L'entier représentant la somme de `valeurA` et `valeurB`.
*   **Contraintes :**
    *   Les opérandes (`valeurA` et `valeurB`) doivent être des entiers.

### 2.2 Conception de l'Algorithme (Pseudo-code)


```
FONCTION CalculerSomme(valeurA : ENTIER, valeurB : ENTIER) RETOURNE ENTIER
    // Déclaration des variables locales
    VARIABLE resultatAddition : ENTIER

    // Début de la fonction
    DEBUT

        // Effectuer l'addition des deux valeurs
        resultatAddition <- valeurA + valeurB

        // Retourner le résultat de l'addition
        RETOURNER resultatAddition

    FIN_FONCTION

// Programme principal (exemple d'utilisation de la fonction)
ALGORITHME ProgrammePrincipal
    // Déclaration des variables
    VARIABLE num1 : ENTIER
    VARIABLE num2 : ENTIER
    VARIABLE sommeFinale : ENTIER

    DEBUT
        AFFICHER "Entrez le premier nombre :"
        LIRE num1

        AFFICHER "Entrez le second nombre :"
        LIRE num2

        // Appel de la fonction pour calculer la somme
        sommeFinale <- CalculerSomme(num1, num2)

        AFFICHER "La somme calculée est : ", sommeFinale
    FIN
```


### 2.3 Test et Validation

Voici deux jeux de valeurs pour tester cette approche :

1.  **Jeu de test 1 :**
    *   Entrées pour `CalculerSomme` : `valeurA` = 12, `valeurB` = 0
    *   Résultat attendu : 12
    *   *Vérification :* 12 + 0 = 12. La fonction devrait retourner ce résultat.

2.  **Jeu de test 2 :**
    *   Entrées pour `CalculerSomme` : `valeurA` = 100, `valeurB` = 250
    *   Résultat attendu : 350
    *   *Vérification :* 100 + 250 = 350. La fonction devrait produire ce résultat.

---