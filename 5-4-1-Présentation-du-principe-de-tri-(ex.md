# Introduction aux tris  
## Présentation du principe de tri : l’exemple du tri par sélection

Le tri est une opération fondamentale en informatique qui consiste à organiser les éléments d’un tableau dans un certain ordre, le plus souvent croissant ou décroissant. Cette organisation facilite la recherche, l’analyse et l’exploitation des données.

---

## 1. Principe général du tri

Le tri vise à réarranger les éléments d’une collection afin qu’ils respectent une relation d’ordre (par exemple : du plus petit au plus grand).

---

## 2. Le tri par sélection : présentation simple

Le **tri par sélection** est une méthode intuitive pour trier un tableau.

- L’idée est de parcourir le tableau pour trouver l’élément minimum (ou maximum) dans la portion non triée.
- Ensuite, cet élément est échangé avec le premier élément non trié.  
- On répète cette opération en décalant le début de la portion non triée jusqu’à ce que tout soit trié.

---

## 3. Fonctionnement illustré

Prenons un tableau T = [29, 10, 14, 37, 14].

- 1ère itération : le minimum dans l’ensemble est 10 → échange avec T[0]  
  Tableau devient [10, 29, 14, 37, 14]

- 2ème itération : minimum dans T[1..4] est 14 → échange avec T[1]  
  Tableau devient [10, 14, 29, 37, 14]

- 3ème itération : minimum dans T[2..4] est 14 → échange avec T[2]  
  Tableau devient [10, 14, 14, 37, 29]

- 4ème itération : minimum dans T[3..4] est 29 → échange avec T[3]  
  Tableau devient [10, 14, 14, 29, 37]

Le tableau est maintenant trié.

---

## 4. Pseudo-code du tri par sélection

```pseudo
POUR i DE 0 A n-2 FAIRE
    minIndex ← i
    POUR j DE i+1 A n-1 FAIRE
        SI T[j] < T[minIndex] ALORS
            minIndex ← j
        FIN SI
    FIN POUR
    Echanger T[i] et T[minIndex]
FIN POUR
```

---

## 5. Diagramme Mermaid illustrant le processus

```mermaid
flowchart TD
    Start[Début]
    Start --> IInit[i = 0]
    IInit --> JInit[j = i+1]
    JInit --> Compare{T[j] < T[minIndex] ?}
    Compare -- Oui --> UpdateMin[minIndex = j]
    Compare -- Non --> Continue
    Continue --> NextJ[j < n ?]
    NextJ -- Oui --> IncrementJ[j = j+1] --> Compare
    NextJ -- Non --> Swap[Echanger T[i] et T[minIndex]]
    Swap --> NextI[i < n-2 ?]
    NextI -- Oui --> IncrementI[i = i+1] --> JInit
    NextI -- Non --> End[Fin]
```

---

## 6. Utilisation et limites

Le tri par sélection est simple à comprendre et implémenter, efficace sur de petits tableaux ou lorsque la mémoire est limitée (car il réalise un nombre minimal d’échanges).

Cependant, il n’est pas optimal pour de très grandes structures car sa complexité est \(O(n^2)\).

---

## Sources utilisées

- [OpenClassrooms - Apprenez à programmer : tris](https://openclassrooms.com/fr/courses/6204541-initiez-vous-a-lalgorithmique/6263957-le-tri-par-selection)  
- [Wikipedia - Tri par sélection](https://fr.wikipedia.org/wiki/Tri_par_s%C3%A9lection)  
- [Developpez.com - Algorithmes de tri](https://algorithmique.developpez.com/cours/tris/#Tri_selection)  

---

Le tri par sélection illustre clairement le concept fondamental de tri par répétition de sélection de l’élément minimal, posé comme base avant d’aborder des algorithmes plus sophistiqués.