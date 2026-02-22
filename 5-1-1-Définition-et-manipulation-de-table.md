# Tableaux unidimensionnels  
## Définition et manipulation de tableaux à une dimension

Un **tableau unidimensionnel** est une structure de données simple mais fondamentale, utilisée pour stocker une collection ordonnée d’éléments du même type, accessibles via un indice unique. Cette structure facilite la gestion et le traitement séquentiel des données.

---

## 1. Définition du tableau unidimensionnel

Un tableau à une dimension peut être vu comme une liste d’éléments regroupés, chacun identifié par un numéro appelé **indice** ou **index**. La numérotation commence généralement à 0 ou 1 selon les langages.

|Par exemple, un tableau T de taille 5 peut contenir :|  
|---|  
|T[0], T[1], T[2], T[3], T[4]|  

Chaque élément est stocké dans une case mémoire contiguë, ce qui permet une manipulation efficace.

---

## 2. Déclaration et initialisation (pseudo-code)

```pseudo
// Déclaration d'un tableau de 5 entiers
TAB entiers T[5]

// Initialisation
POUR i DE 0 A 4 FAIRE
    T[i] ← i * 10
FIN POUR
```

Ici, chaque élément T[i] prend la valeur `i * 10`, soit : [0, 10, 20, 30, 40].

---

## 3. Accès et modification des éléments

- **Lecture d’une valeur** : on accède à un élément avec son indice  
  Exemple : `x ← T[2]` récupère la valeur à l’indice 2 (dans l’exemple 20)

- **Écriture** : on modifie la valeur à un indice donné  
  Exemple : `T[3] ← 99` remplace la valeur 30 par 99

---

## 4. Parcours d’un tableau unidimensionnel

Le parcours séquentiel est réalisé en itérant sur les indices :

```pseudo
POUR i DE 0 A taille(T) - 1 FAIRE
    Afficher T[i]
FIN POUR
```

---

## 5. Application pratique : recherche d’un élément

Recherche linéaire d’une valeur `val` dans le tableau T :

```pseudo
i ← 0
trouve ← FAUX
TANT QUE i < taille(T) ET trouve = FAUX FAIRE
    SI T[i] = val ALORS
        trouve ← VRAI
    SINON
        i ← i + 1
    FIN SI
FIN TANT QUE

SI trouve ALORS
    Afficher "Valeur trouvée à l'indice " + i
SINON
    Afficher "Valeur non trouvée"
FIN SI
```

---

## 6. Diagramme Mermaid illustrant la structure et l'accès

```mermaid
graph LR
    A[Tableau T] --> T0[T[0] = 0]
    A --> T1[T[1] = 10]
    A --> T2[T[2] = 20]
    A --> T3[T[3] = 30]
    A --> T4[T[4] = 40]
```

```mermaid
flowchart TD
    Start[Début] --> ForLoop[Pour i de 0 à taille(T)-1]
    ForLoop --> Aff[T[i] → Afficher]
    Aff --> Increment[Incrémenter i]
    Increment --> ForLoop
    ForLoop --> End[Fin]
```

---

## 7. Points importants

- Les indices doivent toujours être dans les bornes du tableau pour éviter les erreurs d’accès mémoire.  
- La taille du tableau est fixe dans la plupart des langages classiques.  
- Le tableau unidimensionnel est la base pour construire des structures plus complexes comme les matrices ou listes.

---

## Sources utilisées

- [OpenClassrooms - Les tableaux en algorithmique](https://openclassrooms.com/fr/courses/6204541-initiez-vous-a-lalgorithmique/6263946-les-tableaux)  
- [Wikipedia - Tableaux (informatique)](https://fr.wikipedia.org/wiki/Tableau_(informatique))  
- [Developpez.com - Manipulations des tableaux](https://algorithmique.developpez.com/cours/tableaux/)  

---

Maîtriser la définition et l’usage d’un tableau unidimensionnel permet d’aborder la gestion efficace des données et de poser les bases pour de nombreux algorithmes familiers comme le tri, la recherche ou la manipulation séquentielle.