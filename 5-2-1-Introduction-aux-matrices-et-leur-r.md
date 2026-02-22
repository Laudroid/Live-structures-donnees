# Tableaux bidimensionnels  
## Introduction aux matrices et leur représentation en tableau bidimensionnel

Les **tableaux bidimensionnels** sont des structures de données fondamentales constituées d’éléments organisés en lignes et colonnes, permettant la représentation et la manipulation de matrices. Ils sont très utilisés en algorithmique, notamment dans les domaines des mathématiques, du traitement d’images, et de l’analyse de données.

---

## 1. Définition de la matrice

Une matrice est un ensemble rectangulaire d’éléments organisés en lignes et colonnes :

\[
M = \begin{bmatrix}
m_{1,1} & m_{1,2} & \cdots & m_{1,n} \\
m_{2,1} & m_{2,2} & \cdots & m_{2,n} \\
\vdots & \vdots & \ddots & \vdots \\
m_{m,1} & m_{m,2} & \cdots & m_{m,n}
\end{bmatrix}
\]

où \( m \) est le nombre de lignes et \( n \) le nombre de colonnes.

---

## 2. Représentation en tableau bidimensionnel

En algorithmique, une matrice est représentée par un tableau à deux dimensions : une collection de tableaux unidimensionnels, où chaque tableau représente une ligne.

### Notation et indices

- Le tableau est noté \( T \).
- Chaque élément est accessible par deux indices : \( T[i][j] \), où \( i \) est l’indice de la ligne (souvent de 0 à \( m-1 \)), et \( j \) est l’indice de la colonne (de 0 à \( n-1 \)).

---

## 3. Déclaration et initialisation (pseudo-code)

```pseudo
// Déclaration d'une matrice de 3 lignes et 4 colonnes
TAB entiers M[3][4]

// Initialisation : remplir la matrice avec des valeurs
POUR i DE 0 A 2 FAIRE
    POUR j DE 0 A 3 FAIRE
        M[i][j] ← i * 10 + j
    FIN POUR
FIN POUR
```

Après exécution, la matrice \( M \) contient :

| i\j | 0 | 1 | 2 | 3 |
|------|---|---|---|---|
| 0    | 0 | 1 | 2 | 3 |
| 1    | 10| 11| 12| 13|
| 2    | 20| 21| 22| 23|

---

## 4. Accès et manipulation des éléments

- **Lecture** : \( x \leftarrow M[i][j] \)  
- **Écriture** : \( M[i][j] \leftarrow val \)  

Pour parcourir et afficher tous les éléments :

```pseudo
POUR i DE 0 A 2 FAIRE
    POUR j DE 0 A 3 FAIRE
        Afficher M[i][j]
    FIN POUR
FIN POUR
```

---

## 5. Représentation graphique Mermaid d'une matrice 3x4

```mermaid
graph TD
    subgraph Matrice M
        direction TB
        L0["Ligne 0"]
        L1["Ligne 1"]
        L2["Ligne 2"]
    end
    L0 --> M00[M[0][0] = 0]
    L0 --> M01[M[0][1] = 1]
    L0 --> M02[M[0][2] = 2]
    L0 --> M03[M[0][3] = 3]

    L1 --> M10[M[1][0] = 10]
    L1 --> M11[M[1][1] = 11]
    L1 --> M12[M[1][2] = 12]
    L1 --> M13[M[1][3] = 13]

    L2 --> M20[M[2][0] = 20]
    L2 --> M21[M[2][1] = 21]
    L2 --> M22[M[2][2] = 22]
    L2 --> M23[M[2][3] = 23]
```

---

## 6. Applications classiques

- **Représentation d’images** : chaque pixel correspond à un élément de la matrice.  
- **Traitement matriciel** : calcul de sommes, produits, transpositions, etc.  
- **Jeux à grille** : échiquier, sudoku, où chaque case peut être indexée par deux dimensions.  

---

## 7. Points de vigilance

- Toujours respecter les bornes des indices en ligne et colonne (éviter les dépassements).  
- La gestion mémoire peut devenir conséquente pour des tableaux très grands.  
- Comprendre la différence entre lignes (1ère dimension) et colonnes (2ème dimension) est crucial pour traiter correctement les matrices.

---

## Sources utilisées

- [OpenClassrooms - Les tableaux multidimensionnels](https://openclassrooms.com/fr/courses/6204541-initiez-vous-a-lalgorithmique/6263954-les-tableaux-multidimensionnels)  
- [Wikipedia - Matrice (informatique)](https://fr.wikipedia.org/wiki/Matrice_(informatique))  
- [Developpez.com - Manipulation des matrices](https://algorithmique.developpez.com/cours/tableaux/#Tableaux_multidimensionnels)  

---

La représentation des matrices via des tableaux bidimensionnels constitue un socle algorithmique incontournable, facilitant la modélisation et la résolution de très nombreux problèmes où les données sont organisées en deux dimensions.