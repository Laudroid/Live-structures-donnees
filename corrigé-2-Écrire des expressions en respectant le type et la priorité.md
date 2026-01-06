Bonjour !

Voici deux propositions de solutions pour le TP sur les expressions, les types et les priorités, en utilisant Python comme langage de programmation. Ces solutions visent à illustrer les concepts clés de manière pragmatique, en se concentrant sur la clarté et la correction du code.

---

## Chapitre 1 : Solution 1 - Python avec gestion explicite des types

Cette première approche utilise des types de données distincts pour les notes (flottants) et les coefficients (entiers), puis s'assure que le calcul final respecte la précision attendue.

### 1.1 Analyse du Problème

Le but est de calculer une moyenne pondérée. Les entrées sont trois notes et leurs coefficients respectifs. La sortie est la moyenne pondérée, qui doit être un nombre flottant affiché avec au moins deux décimales. La formule est `(Somme des (note * coefficient)) / (Somme des coefficients)`.

### 1.2 Déclaration et Initialisation des Variables

Pour les notes, qui peuvent avoir des décimales, le type `float` est approprié. Pour les coefficients, qui sont des nombres entiers, le type `int` est suffisant.


```python
# Notes (peuvent être décimales)
note_tp = 15.0
note_projet = 12.5
note_examen = 18.0

# Coefficients (entiers)
coef_tp = 2
coef_projet = 3
coef_examen = 5
```


### 1.3 Écriture de l'Expression de Calcul

L'expression de la moyenne pondérée nécessite une attention particulière aux parenthèses pour garantir la priorité des opérations. Les multiplications `note * coefficient` doivent être effectuées avant les additions, et la somme des produits doit être calculée avant la division par la somme des coefficients.


```python
# Calcul de la somme des produits (note * coefficient)
somme_produits = (note_tp * coef_tp) + 
                 (note_projet * coef_projet) + 
                 (note_examen * coef_examen)

# Calcul de la somme des coefficients
somme_coefficients = coef_tp + coef_projet + coef_examen

# Calcul de la moyenne pondérée
# En Python 3, l'opérateur de division '/' effectue toujours une division flottante,
# même si les opérandes sont des entiers. Cela garantit un résultat décimal.
moyenne_ponderee = somme_produits / somme_coefficients
```


**Explication des parenthèses :**
*   Les parenthèses autour de chaque `(note * coefficient)` ne sont pas strictement nécessaires ici car la multiplication a une priorité plus élevée que l'addition. Cependant, elles améliorent la lisibilité et clarifient l'intention de regrouper ces opérations.
*   Les parenthèses autour de `somme_produits` et `somme_coefficients` dans l'expression finale sont implicites car nous calculons ces sommes dans des variables intermédiaires. Si l'expression était écrite en une seule ligne, elles seraient cruciales : `(note_tp * coef_tp + note_projet * coef_projet + note_examen * coef_examen) / (coef_tp + coef_projet + coef_examen)`.

### 1.4 Gestion des Types et Précision

Comme mentionné, l'opérateur `/` en Python 3 assure une division flottante. Pour l'affichage, les f-strings (formatage de chaînes littérales) sont une méthode moderne et efficace pour contrôler la précision décimale.


```python
# Affichage du résultat avec une précision de deux décimales
print(f"La note finale du module est : {moyenne_ponderee:.2f}")
```


Le `.2f` dans la f-string indique que le nombre flottant (`f`) doit être formaté avec deux chiffres après la virgule.

### 1.5 Code Complet (Python)


```python
# Déclaration et initialisation des variables
note_tp = 15.0
note_projet = 12.5
note_examen = 18.0

coef_tp = 2
coef_projet = 3
coef_examen = 5

# Écriture de l'expression de calcul
somme_produits = (note_tp * coef_tp) + 
                 (note_projet * coef_projet) + 
                 (note_examen * coef_examen)

somme_coefficients = coef_tp + coef_projet + coef_examen

moyenne_ponderee = somme_produits / somme_coefficients

# Affichage du résultat avec la précision requise
print(f"La note finale du module est : {moyenne_ponderee:.2f}")

# --- Expérimentation (pour comprendre la priorité des opérateurs) ---
# Si on omettait les parenthèses pour la somme des produits dans une seule ligne,
# et que la division était faite avec des entiers (comme en C/Java pour '/'):
# exemple_incorrect = note_tp * coef_tp + note_projet * coef_projet + note_examen * coef_examen / coef_tp + coef_projet + coef_examen
# Ici, la division 'note_examen * coef_examen / coef_tp' serait effectuée en premier,
# puis les additions, ce qui donnerait un résultat erroné pour une moyenne pondérée.
# La bonne pratique est d'utiliser des parenthèses pour clarifier l'ordre désiré.
```


---

## Chapitre 2 : Solution 2 - Python avec types flottants uniformes

Cette seconde approche simplifie la gestion des types en déclarant toutes les variables numériques (notes et coefficients) comme des flottants dès le départ. Cela peut rendre le code plus robuste face aux divisions, car toutes les opérations se feront en arithmétique flottante.

### 2.1 Analyse du Problème

L'analyse reste la même : calculer une moyenne pondérée à partir de notes et coefficients, avec un résultat flottant formaté.

### 2.2 Déclaration et Initialisation des Variables

En déclarant les coefficients comme des flottants, on s'assure que toutes les opérations intermédiaires et finales sont traitées comme des nombres à virgule flottante, évitant ainsi tout risque de division entière involontaire (même si Python 3 gère bien cela avec `/`).


```python
# Notes (flottants)
note_tp = 15.0
note_projet = 12.5
note_examen = 18.0

# Coefficients (déclarés comme flottants pour une uniformité des types)
coef_tp = 2.0
coef_projet = 3.0
coef_examen = 5.0
```


### 2.3 Écriture de l'Expression de Calcul

L'expression reste structurellement identique, mais la nature flottante de toutes les variables simplifie mentalement le suivi des types.


```python
# Calcul de la somme des produits
somme_produits = (note_tp * coef_tp) + \
                 (note_projet * coef_projet) + \
                 (note_examen * coef_examen)

# Calcul de la somme des coefficients
somme_coefficients = coef_tp + coef_projet + coef_examen

# Calcul de la moyenne pondérée
moyenne_ponderee = somme_produits / somme_coefficients
```


### 2.4 Gestion des Types et Précision

Avec toutes les variables en `float`, la gestion des types est simplifiée. Le formatage de l'affichage reste le même pour garantir la précision requise.


```python
# Affichage du résultat avec une précision de deux décimales
print(f"La note finale du module est : {moyenne_ponderee:.2f}")
```


### 2.5 Code Complet (Python)


```python
# Déclaration et initialisation des variables (toutes en flottants)
note_tp = 15.0
note_projet = 12.5
note_examen = 18.0

coef_tp = 2.0  # Noter le .0 pour indiquer un flottant
coef_projet = 3.0
coef_examen = 5.0

# Écriture de l'expression de calcul
somme_produits = (note_tp * coef_tp) + \
                 (note_projet * coef_projet) + \
                 (note_examen * coef_examen)

somme_coefficients = coef_tp + coef_projet + coef_examen

moyenne_ponderee = somme_produits / somme_coefficients

# Affichage du résultat avec la précision requise
print(f"La note finale du module est : {moyenne_ponderee:.2f}")

# --- Expérimentation et Vérification ---
# Si l'on modifie l'expression volontairement pour tester la priorité :
# moyenne_incorrecte_test = note_tp * coef_tp + note_projet * coef_projet / coef_examen + note_examen
# print(f"Résultat incorrect (test priorité) : {moyenne_incorrecte_test:.2f}")
# Le résultat serait différent car 'note_projet * coef_projet / coef_examen' serait calculé en premier,
# puis les additions, ce qui ne correspond pas à la logique de la moyenne pondérée.
# Cela souligne l'importance des parenthèses pour forcer l'ordre d'évaluation désiré.
```