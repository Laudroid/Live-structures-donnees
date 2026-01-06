Bonjour !

Voici deux propositions de solutions pour le TP "Classificateur Numérique Interactif", implémentées en Python. Ces solutions illustrent l'utilisation des structures conditionnelles et des boucles, avec une attention particulière à la gestion des entrées utilisateur.

---

## Chapitre 1 : Solution 1 - Classificateur Basique

Cette première solution se concentre sur la logique principale de classification et de comptage, en supposant que l'utilisateur saisira des nombres entiers valides.

### 1.1 Pseudocode


```
ALGORITHME ClassificateurBasique
    // Déclaration des variables
    nombre_total_a_analyser : ENTIER
    compteur_positifs : ENTIER <- 0
    compteur_negatifs : ENTIER <- 0
    compteur_zeros : ENTIER <- 0
    nombre_saisi : ENTIER

    // Étape 1 : Initialisation
    AFFICHER "Combien de nombres souhaitez-vous analyser ?"
    LIRE nombre_total_a_analyser

    // Vérifier si l'utilisateur veut analyser 0 nombre
    SI nombre_total_a_analyser <= 0 ALORS
        AFFICHER "Aucun nombre à analyser. Fin du programme."
        RETOUR
    FIN_SI

    // Étape 2 : Saisie et Classification pour chaque nombre
    POUR i ALLANT DE 1 À nombre_total_a_analyser FAIRE
        AFFICHER "Veuillez saisir le nombre entier ", i, " :"
        LIRE nombre_saisi

        SI nombre_saisi > 0 ALORS
            AFFICHER "Le nombre ", nombre_saisi, " est positif."
            compteur_positifs <- compteur_positifs + 1
        SINON SI nombre_saisi < 0 ALORS
            AFFICHER "Le nombre ", nombre_saisi, " est négatif."
            compteur_negatifs <- compteur_negatifs + 1
        SINON // nombre_saisi est égal à 0
            AFFICHER "Le nombre ", nombre_saisi, " est nul."
            compteur_zeros <- compteur_zeros + 1
        FIN_SI
    FIN_POUR

    // Étape 3 : Rapport Final
    AFFICHER "--- Rapport Final ---"
    AFFICHER "Nombres positifs : ", compteur_positifs
    AFFICHER "Nombres négatifs : ", compteur_negatifs
    AFFICHER "Nombres nuls : ", compteur_zeros
FIN_ALGORITHME
```


### 1.2 Code Python


```python
# Initialisation des compteurs
compteur_positifs = 0
compteur_negatifs = 0
compteur_zeros = 0

# Étape 1 : Demander le nombre de nombres à analyser
try:
    nombre_total_a_analyser = int(input("Combien de nombres souhaitez-vous analyser ? "))
except ValueError:
    print("Saisie invalide. Veuillez entrer un nombre entier.")
    exit() # Quitte le programme si la première saisie est invalide

if nombre_total_a_analyser <= 0:
    print("Aucun nombre à analyser. Fin du programme.")
else:
    # Étape 2 : Saisie et Classification pour chaque nombre
    for i in range(1, nombre_total_a_analyser + 1):
        try:
            nombre_saisi = int(input(f"Veuillez saisir le nombre entier {i} : "))

            if nombre_saisi > 0:
                print(f"Le nombre {nombre_saisi} est positif.")
                compteur_positifs += 1
            elif nombre_saisi < 0:
                print(f"Le nombre {nombre_saisi} est négatif.")
                compteur_negatifs += 1
            else: # nombre_saisi est égal à 0
                print(f"Le nombre {nombre_saisi} est nul.")
                compteur_zeros += 1
        except ValueError:
            print("Saisie invalide. Ce n'est pas un nombre entier. Ce nombre ne sera pas comptabilisé.")
            # On pourrait aussi choisir de redemander la saisie, mais pour cette solution, on passe au suivant.

    # Étape 3 : Rapport Final
    print("\n--- Rapport Final ---")
    print(f"Nombres positifs : {compteur_positifs}")
    print(f"Nombres négatifs : {compteur_negatifs}")
    print(f"Nombres nuls : {compteur_zeros}")

```


### 1.3 Explications

*   **Initialisation :** Les compteurs `compteur_positifs`, `compteur_negatifs`, `compteur_zeros` sont mis à zéro avant la boucle.
*   **Saisie du nombre total :** L'utilisateur est invité à spécifier combien de nombres il souhaite analyser. Une gestion d'erreur basique est ajoutée pour la première saisie afin d'éviter un crash si l'utilisateur ne rentre pas un entier.
*   **Boucle `for` :** Une boucle `for` est utilisée pour répéter les étapes de saisie et de classification le nombre de fois spécifié. `range(1, nombre_total_a_analyser + 1)` génère les nombres de 1 jusqu'à `nombre_total_a_analyser` inclus.
*   **Structures conditionnelles `if-elif-else` :** À l'intérieur de la boucle, un bloc `if-elif-else` détermine la catégorie de chaque `nombre_saisi` :
    *   `if nombre_saisi > 0:` : Le nombre est positif.
    *   `elif nombre_saisi < 0:` : Le nombre est négatif.
    *   `else:` : Si le nombre n'est ni positif ni négatif, il est nécessairement nul.
*   **Incrémentation :** Le compteur correspondant est incrémenté (`+= 1`) pour chaque classification.
*   **Affichage immédiat :** Le résultat de la classification est affiché directement après chaque saisie.
*   **Rapport final :** Après la boucle, un récapitulatif des comptes est affiché.
*   **Gestion d'erreur simple :** Un `try-except ValueError` est utilisé pour la saisie de chaque nombre. Si l'utilisateur entre une valeur non entière, un message d'erreur est affiché et le programme passe au nombre suivant sans compter l'entrée invalide.

---

## Chapitre 2 : Solution 2 - Classificateur Robuste avec Gestion d'Erreurs

Cette solution améliore la précédente en intégrant une gestion d'erreurs plus robuste pour la saisie des nombres, garantissant que seuls des entiers valides sont traités.

### 2.1 Pseudocode


```
ALGORITHME ClassificateurRobuste
    // Déclaration des variables
    nombre_total_a_analyser : ENTIER
    compteur_positifs : ENTIER <- 0
    compteur_negatifs : ENTIER <- 0
    compteur_zeros : ENTIER <- 0
    nombre_saisi : ENTIER

    // Étape 1 : Initialisation avec validation de l'entrée pour le nombre total
    TANT_QUE VRAI FAIRE
        AFFICHER "Combien de nombres souhaitez-vous analyser ?"
        LIRE_CHAINE_DE_CARACTERES entree_utilisateur
        SI est_entier(entree_utilisateur) ALORS
            nombre_total_a_analyser <- convertir_en_entier(entree_utilisateur)
            SI nombre_total_a_analyser >= 0 ALORS
                CASSER_BOUCLE // Sortir de la boucle si l'entrée est un entier positif ou nul
            SINON
                AFFICHER "Veuillez entrer un nombre positif ou nul."
            FIN_SI
        SINON
            AFFICHER "Saisie invalide. Veuillez entrer un nombre entier."
        FIN_SI
    FIN_TANT_QUE

    SI nombre_total_a_analyser = 0 ALORS
        AFFICHER "Aucun nombre à analyser. Fin du programme."
        RETOUR
    FIN_SI

    // Étape 2 : Saisie et Classification pour chaque nombre avec validation
    POUR i ALLANT DE 1 À nombre_total_a_analyser FAIRE
        TANT_QUE VRAI FAIRE // Boucle pour s'assurer d'une saisie valide
            AFFICHER "Veuillez saisir le nombre entier ", i, " :"
            LIRE_CHAINE_DE_CARACTERES entree_nombre
            SI est_entier(entree_nombre) ALORS
                nombre_saisi <- convertir_en_entier(entree_nombre)
                CASSER_BOUCLE // Sortir de la boucle interne si l'entrée est valide
            SINON
                AFFICHER "Saisie invalide. Veuillez entrer un nombre entier."
            FIN_SI
        FIN_TANT_QUE

        SI nombre_saisi > 0 ALORS
            AFFICHER "Le nombre ", nombre_saisi, " est positif."
            compteur_positifs <- compteur_positifs + 1
        SINON SI nombre_saisi < 0 ALORS
            AFFICHER "Le nombre ", nombre_saisi, " est négatif."
            compteur_negatifs <- compteur_negatifs + 1
        SINON
            AFFICHER "Le nombre ", nombre_saisi, " est nul."
            compteur_zeros <- compteur_zeros + 1
        FIN_SI
    FIN_POUR

    // Étape 3 : Rapport Final
    AFFICHER "--- Rapport Final ---"
    AFFICHER "Nombres positifs : ", compteur_positifs
    AFFICHER "Nombres négatifs : ", compteur_negatifs
    AFFICHER "Nombres nuls : ", compteur_zeros
FIN_ALGORITHME
```


### 2.2 Code Python


```python
# Initialisation des compteurs
compteur_positifs = 0
compteur_negatifs = 0
compteur_zeros = 0

# Étape 1 : Demander le nombre de nombres à analyser avec validation robuste
nombre_total_a_analyser = 0
while True:
    try:
        saisie_nb_total = input("Combien de nombres souhaitez-vous analyser ? ")
        nombre_total_a_analyser = int(saisie_nb_total)
        if nombre_total_a_analyser >= 0:
            break # Sort de la boucle si l'entrée est un entier positif ou nul
        else:
            print("Veuillez entrer un nombre positif ou nul.")
    except ValueError:
        print("Saisie invalide. Veuillez entrer un nombre entier.")

if nombre_total_a_analyser == 0:
    print("Aucun nombre à analyser. Fin du programme.")
else:
    # Étape 2 : Saisie et Classification pour chaque nombre avec validation robuste
    for i in range(1, nombre_total_a_analyser + 1):
        nombre_saisi = 0
        while True: # Boucle interne pour s'assurer d'une saisie valide pour le nombre courant
            try:
                saisie_nombre_courant = input(f"Veuillez saisir le nombre entier {i} : ")
                nombre_saisi = int(saisie_nombre_courant)
                break # Sort de la boucle interne si l'entrée est un entier valide
            except ValueError:
                print("Saisie invalide. Veuillez entrer un nombre entier.")

        if nombre_saisi > 0:
            print(f"Le nombre {nombre_saisi} est positif.")
            compteur_positifs += 1
        elif nombre_saisi < 0:
            print(f"Le nombre {nombre_saisi} est négatif.")
            compteur_negatifs += 1
        else: # nombre_saisi est égal à 0
            print(f"Le nombre {nombre_saisi} est nul.")
            compteur_zeros += 1

    # Étape 3 : Rapport Final
    print("\n--- Rapport Final ---")
    print(f"Nombres positifs : {compteur_positifs}")
    print(f"Nombres négatifs : {compteur_negatifs}")
    print(f"Nombres nuls : {compteur_zeros}")

```


### 2.3 Explications

*   **Boucles `while True` pour la validation :** La différence majeure réside dans l'utilisation de boucles `while True` pour la saisie des entrées.
    *   Pour le `nombre_total_a_analyser`, la boucle continue tant qu'une valeur entière positive ou nulle n'est pas fournie.
    *   Pour chaque `nombre_saisi` à l'intérieur de la boucle `for`, une boucle `while True` interne est utilisée. Cela signifie que l'utilisateur sera **systématiquement invité à nouveau** à saisir un nombre pour l'itération courante tant qu'il n'aura pas fourni un entier valide.
*   **Bloc `try-except ValueError` :** C'est le mécanisme clé de gestion d'erreurs en Python.
    *   `try:` : Le code potentiellement générateur d'erreur (ici, `int(input(...))`) est placé dans ce bloc.
    *   `except ValueError:` : Si une `ValueError` se produit (par exemple, si `int()` tente de convertir une chaîne non numérique), le code de ce bloc est exécuté, affichant un message d'erreur.
    *   `break` : Une fois qu'une saisie valide est obtenue et convertie en entier sans erreur, `break` est utilisé pour sortir de la boucle `while True` et passer à la suite du programme.
*   **Clarté et robustesse :** Cette approche rend le programme beaucoup plus robuste face aux erreurs de saisie de l'utilisateur, améliorant ainsi l'expérience utilisateur et la fiabilité du programme.

Ces deux solutions vous donnent une base solide pour comprendre et appliquer les structures conditionnelles et la gestion des entrées. La seconde solution, plus robuste, est souvent préférée dans des applications réelles.