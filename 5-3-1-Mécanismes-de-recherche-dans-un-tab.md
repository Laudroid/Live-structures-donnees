# Algorithmes de recherche simple  
## Mécanismes de recherche dans un tableau : la recherche linéaire

La recherche dans un tableau est une opération fondamentale en algorithmique, consistant à localiser la position d’un élément donné dans une collection. La technique la plus simple et universelle pour ce faire est la **recherche linéaire** (ou séquentielle), qui consiste à parcourir tous les éléments côte à côte jusqu’à trouver la valeur recherchée ou atteindre la fin du tableau.

---

## 1. Principe de la recherche linéaire

La recherche linéaire balaie, un à un, les éléments du tableau **T** en partant de la première case (indice 0) jusqu’à la dernière, en comparant chaque valeur à la cible. 

- Si une correspondance est trouvée, l’algorithme retourne l’indice où elle se situe.  
- Sinon, le processus se termine en indiquant que l’élément n’est pas présent.

Ce mécanisme ne nécessite pas que le tableau soit trié.

---

## 2. Pseudo-code de la recherche linéaire

```pseudo
Fonction RechercheLin(T: tableau, val: élément) : entier
    i ← 0
    trouve ← FAUX
    TAILLE ← longueur(T)

    TANT QUE i < TAILLE ET trouve = FAUX FAIRE
        SI T[i] = val ALORS
            trouve ← VRAI
        SINON
            i ← i + 1
        FIN SI
    FIN TANT QUE

    SI trouve ALORS
        Retourner i
    SINON
        Retourner -1  // valeur spéciale indiquant "non trouvé"
    FIN SI
Fin Fonction
```

---

## 3. Exemple concret

Rechercher la valeur 15 dans un tableau T = [7, 2, 15, 6, 9] :

- i=0 : T[0]=7 ≠ 15 → continuer  
- i=1 : T[1]=2 ≠ 15 → continuer  
- i=2 : T[2]=15 = 15 → trouvé → retourner 2

---

## 4. Complexité

- **Temps dans le pire cas** : \(O(n)\), où \(n\) est la taille du tableau (cas où l’élément est absent ou en dernière position).  
- **Temps dans le meilleur cas** : \(O(1)\) si l’élément recherché est en première position.  

La recherche linéaire est simple mais peut devenir inefficace avec de grands tableaux non triés.

---

## 5. Diagramme Mermaid illustrant la recherche linéaire

```mermaid
flowchart TD
    Start[Début] --> Init[i=0, trouve=Faux]
    Init --> Condition{i < taille(T) et trouve = Faux ?}
    Condition -- Non --> FinNonTrouve[Retourner -1]
    Condition -- Oui --> Comparaison[T[i] = val ?]
    Comparaison -- Oui --> Trouve[i]
    Comparaison -- Non --> Increment[i ← i+1] --> Condition
    Trouve --> FinTrouve[Retourner i]
```

---

## 6. Variantes et améliorations

- **Recherche linéaire dans des tableaux triés** : on peut arrêter la recherche dès que l’élément examiné dépasse la valeur recherchée.  
- **Recherche séquentielle avec sentinelle** : ajouter temporairement la valeur recherchée à la fin du tableau pour simplifier la condition de sortie (réduction des comparaisons).  
- Pour des recherches sur tableaux triés, des algorithmes plus efficaces comme la recherche dichotomique sont préférables.

---

## Sources utilisées

- [OpenClassrooms - Algorithme de recherche séquentielle](https://openclassrooms.com/fr/courses/6204541-initiez-vous-a-lalgorithmique/6263950-la-recherche-sequentielle)  
- [Wikipedia - Recherche linéaire](https://fr.wikipedia.org/wiki/Recherche_lin%C3%A9aire)  
- [Developpez.com - Recherche linéaire](https://algorithmique.developpez.com/cours/recherches/#Recherche_lin%C3%A9aire)  

---

La **recherche linéaire** est une méthode simple, directe et universelle pour retrouver une valeur dans un tableau, particulièrement utile lorsque l’ordre des données est inconnu ou lorsque les structures associées plus complexes ne sont pas justifiées. Elle sert aussi de base pour comprendre et concevoir des méthodes de recherche plus avancées.