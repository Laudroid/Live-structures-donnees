Bonjour !

Voici deux propositions de solutions pour le TP "Gestionnaire de Catalogue Produit Simplifié", implémentées en Python. Ces solutions vous guideront à travers la modélisation des données, l'implémentation d'algorithmes de recherche et de tri, et une réflexion sur leurs performances et améliorations.

---

## Chapitre 1 : Solution 1 - Catalogue avec Objets `Produit` et Tri par Sélection

Cette solution utilise une classe Python pour représenter les produits, ce qui offre une structure claire et orientée objet pour chaque élément du catalogue.

### 1.1 Modélisation du Catalogue

Nous définissons une classe `Produit` pour encapsuler les attributs de chaque article. Le catalogue est une liste de ces objets.



```python
class Produit:
    """
    Représente un produit dans le catalogue avec un ID, un nom, un prix et une quantité en stock.
    """
    def __init__(self, id: int, nom: str, prix: float, quantiteStock: int):
        self.id = id
        self.nom = nom
        self.prix = prix
        self.quantiteStock = quantiteStock

    def __str__(self):
        """
        Retourne une représentation textuelle lisible du produit.
        """
        return f"ID: {self.id}, Nom: {self.nom:<20}, Prix: {self.prix:.2f}€, Stock: {self.quantiteStock}"

def afficher_catalogue(catalogue: list[Produit]):
    """
    Affiche tous les produits du catalogue de manière lisible.
    """
    if not catalogue:
        print("Le catalogue est vide.")
        return
    print("\n--- Catalogue des Produits ---")
    for produit in catalogue:
        print(produit)
    print("----------------------------")

# Initialisation du catalogue avec des objets Produit
catalogue_initial = [
    Produit(101, "Ordinateur Portable", 1200.50, 15),
    Produit(102, "Souris Sans Fil", 25.99, 50),
    Produit(103, "Clavier Mécanique", 80.00, 20),
    Produit(104, "Écran 27 pouces", 300.00, 10),
    Produit(105, "Webcam HD", 45.50, 30),
    Produit(106, "Disque Dur Externe", 90.00, 25),
    Produit(107, "Casque Gaming", 110.00, 18)
]
```



### 1.2 Recherche d'un Produit

La fonction `rechercher_produit_par_nom` implémente une recherche linéaire, parcourant chaque élément jusqu'à trouver une correspondance.



```python
def rechercher_produit_par_nom(catalogue: list[Produit], nom_recherche: str) -> Produit | None:
    """
    Recherche un produit dans le catalogue par son nom (insensible à la casse).
    Retourne l'objet Produit s'il est trouvé, sinon None.
    """
    nom_recherche_lower = nom_recherche.lower()
    for produit in catalogue:
        if produit.nom.lower() == nom_recherche_lower:
            return produit
    return None # Retourne None si aucun produit n'est trouvé
```



### 1.3 Tri du Catalogue par Sélection

Deux fonctions sont créées pour trier le catalogue, l'une par prix et l'autre par nom, en utilisant l'algorithme de tri par sélection.



```python
def trier_catalogue_par_prix(catalogue: list[Produit]):
    """
    Trie le catalogue par prix (ordre croissant) en utilisant l'algorithme de tri par sélection.
    Modifie la liste en place.
    """
    n = len(catalogue)
    for i in range(n - 1):
        min_idx = i
        for j in range(i + 1, n):
            if catalogue[j].prix < catalogue[min_idx].prix:
                min_idx = j
        # Échange les éléments
        catalogue[i], catalogue[min_idx] = catalogue[min_idx], catalogue[i]

def trier_catalogue_par_nom(catalogue: list[Produit]):
    """
    Trie le catalogue par nom (ordre alphabétique, insensible à la casse)
    en utilisant l'algorithme de tri par sélection. Modifie la liste en place.
    """
    n = len(catalogue)
    for i in range(n - 1):
        min_idx = i
        for j in range(i + 1, n):
            # Comparaison insensible à la casse pour le nom
            if catalogue[j].nom.lower() < catalogue[min_idx].nom.lower():
                min_idx = j
        # Échange les éléments
        catalogue[i], catalogue[min_idx] = catalogue[min_idx], catalogue[i]
```



### 1.4 Intégration et Démonstration (Programme Principal)



```python
def main_solution1():
    print("--- Démarrage du Gestionnaire de Catalogue (Solution 1) ---")
    
    # Création d'une copie du catalogue initial pour ne pas modifier l'original
    # si on veut le réutiliser dans d'autres tests.
    catalogue_courant = list(catalogue_initial) 

    afficher_catalogue(catalogue_courant)

    # Test de la recherche
    nom_recherche = input("\nEntrez le nom d'un produit à rechercher : ")
    produit_trouve = rechercher_produit_par_nom(catalogue_courant, nom_recherche)
    if produit_trouve:
        print(f"Produit trouvé : {produit_trouve}")
    else:
        print(f"Le produit '{nom_recherche}' n'a pas été trouvé.")

    # Test de la recherche d'un produit inexistant
    produit_inexistant = rechercher_produit_par_nom(catalogue_courant, "Cafetière")
    if not produit_inexistant:
        print("Test : 'Cafetière' n'a pas été trouvé (attendu).")

    # Tri par prix
    print("\n--- Tri du catalogue par prix (croissant) ---")
    trier_catalogue_par_prix(catalogue_courant)
    afficher_catalogue(catalogue_courant)

    # Tri par nom
    print("\n--- Tri du catalogue par nom (alphabétique) ---")
    trier_catalogue_par_nom(catalogue_courant)
    afficher_catalogue(catalogue_courant)

    print("--- Fin du Gestionnaire de Catalogue (Solution 1) ---")

# Pour exécuter cette solution, décommenter la ligne ci-dessous:
# main_solution1()
```



### 1.5 Réflexion et Amélioration

1.  **Utilisation de l'IA :**
    Si j'avais utilisé une IA, j'aurais probablement commencé par des prompts pour la définition de la classe `Produit` et la fonction d'affichage. Ensuite, j'aurais demandé l'implémentation de la recherche linéaire et du tri par sélection. Par exemple :
    *   "Écris une classe Python `Produit` avec `id`, `nom`, `prix`, `quantiteStock` et une méthode `__str__`."
    *   "Comment implémenter une recherche linéaire dans une liste d'objets Python par un attribut de chaîne, en ignorant la casse ?"
    *   "Donne-moi le code Python pour l'algorithme de tri par sélection pour une liste d'objets, triant par un attribut numérique (prix)."
    *   "Adapte le tri par sélection pour trier par un attribut de chaîne (nom) en ordre alphabétique, insensible à la casse."
    J'aurais vérifié le code généré en le comparant à ma compréhension des algorithmes. L'IA peut parfois omettre la gestion de la casse ou des cas limites (liste vide), nécessitant une adaptation. Par exemple, l'IA pourrait ne pas proposer `lower()` pour la comparaison des noms, ce que j'aurais ajouté pour la robustesse.

2.  **Performance de la recherche :**
    Pour un catalogue de 100 000 produits, la fonction `rechercher_produit_par_nom` (recherche linéaire) aurait un impact significatif sur les performances. Dans le pire des cas (produit à la fin ou non trouvé), elle devrait parcourir les 100 000 produits. Sa complexité est **O(N)**, où N est le nombre de produits. Cela signifie que le temps de recherche augmente linéairement avec la taille du catalogue.
    **Idée d'amélioration pour un catalogue trié :** Si le catalogue est souvent trié (par nom, par exemple), on pourrait utiliser une **recherche dichotomique (ou binaire)**. Cet algorithme a une complexité de **O(log N)**, ce qui est beaucoup plus rapide pour de grands ensembles de données. Il fonctionne en divisant le tableau en deux à chaque étape, éliminant la moitié des éléments à chaque fois.

3.  **Efficacité du tri par sélection :**
    Le tri par sélection n'est pas l'algorithme de tri le plus efficace en général. Sa complexité temporelle est **O(N²)** dans tous les cas (pire, moyen, meilleur), car il doit toujours parcourir une grande partie du tableau pour trouver le minimum à chaque itération.
    Un autre algorithme de tri est le **Tri Fusion (Merge Sort)**. Son principe est de diviser récursivement le tableau en deux sous-tableaux jusqu'à ce qu'ils ne contiennent qu'un seul élément, puis de fusionner ces sous-tableaux triés. Sa complexité est **O(N log N)**. Il est généralement plus efficace que le tri par sélection pour de grands ensembles de données, mais il nécessite une mémoire supplémentaire pour les fusions.

4.  **Robustesse du gestionnaire :**
    Pour rendre le gestionnaire de catalogue plus robuste, on pourrait :
    *   **Validation des entrées utilisateur :** S'assurer que les IDs sont des entiers, les prix des nombres décimaux valides, etc., et gérer les erreurs de saisie.
    *   **Gestion des IDs en double :** Empêcher l'ajout de produits avec un `id` déjà existant.
    *   **Opérations CRUD complètes :** Ajouter des fonctionnalités pour `C`réer (ajouter), `U`pdater (modifier), et `D`elete (supprimer) des produits.
    *   **Persistance des données :** Sauvegarder le catalogue dans un fichier (CSV, JSON) et le charger au démarrage pour ne pas perdre les données à chaque exécution.
    *   **Gestion des stocks :** Mettre à jour la quantité en stock lors d'une vente ou d'un réapprovisionnement.

---

## Chapitre 2 : Solution 2 - Catalogue avec Dictionnaires et Tri par Sélection

Cette solution utilise des dictionnaires Python pour représenter les produits. C'est une alternative flexible aux classes pour structurer des données, particulièrement utile pour des structures simples ou des données semi-structurées.

### 2.1 Modélisation du Catalogue

Chaque produit est un dictionnaire, et le catalogue est une liste de ces dictionnaires.



```python
def afficher_catalogue_dict(catalogue: list[dict]):
    """
    Affiche tous les produits du catalogue (représentés par des dictionnaires)
    de manière lisible.
    """
    if not catalogue:
        print("Le catalogue est vide.")
        return
    print("\n--- Catalogue des Produits (Dictionnaires) ---")
    for produit in catalogue:
        # Utilisation de .get() pour une gestion plus robuste si une clé manque
        print(f"ID: {produit.get('id', 'N/A')}, "
              f"Nom: {produit.get('nom', 'N/A'):<20}, "
              f"Prix: {produit.get('prix', 0.0):.2f}€, "
              f"Stock: {produit.get('quantiteStock', 0)}")
    print("--------------------------------------------")

# Initialisation du catalogue avec des dictionnaires
catalogue_initial_dict = [
    {'id': 101, 'nom': "Ordinateur Portable", 'prix': 1200.50, 'quantiteStock': 15},
    {'id': 102, 'nom': "Souris Sans Fil", 'prix': 25.99, 'quantiteStock': 50},
    {'id': 103, 'nom': "Clavier Mécanique", 'prix': 80.00, 'quantiteStock': 20},
    {'id': 104, 'nom': "Écran 27 pouces", 'prix': 300.00, 'quantiteStock': 10},
    {'id': 105, 'nom': "Webcam HD", 'prix': 45.50, 'quantiteStock': 30},
    {'id': 106, 'nom': "Disque Dur Externe", 'prix': 90.00, 'quantiteStock': 25},
    {'id': 107, 'nom': "Casque Gaming", 'prix': 110.00, 'quantiteStock': 18}
]
```



### 2.2 Recherche d'un Produit

La recherche linéaire est adaptée pour travailler avec les clés des dictionnaires.



```python
def rechercher_produit_par_nom_dict(catalogue: list[dict], nom_recherche: str) -> dict | None:
    """
    Recherche un produit dans le catalogue (liste de dictionnaires) par son nom (insensible à la casse).
    Retourne le dictionnaire du produit s'il est trouvé, sinon None.
    """
    nom_recherche_lower = nom_recherche.lower()
    for produit in catalogue:
        # Vérifie si la clé 'nom' existe avant de tenter la comparaison
        if 'nom' in produit and produit['nom'].lower() == nom_recherche_lower:
            return produit
    return None
```



### 2.3 Tri du Catalogue par Sélection

Les fonctions de tri sont modifiées pour accéder aux valeurs via les clés des dictionnaires.



```python
def trier_catalogue_par_prix_dict(catalogue: list[dict]):
    """
    Trie le catalogue (liste de dictionnaires) par prix (ordre croissant)
    en utilisant l'algorithme de tri par sélection. Modifie la liste en place.
    """
    n = len(catalogue)
    for i in range(n - 1):
        min_idx = i
        for j in range(i + 1, n):
            # Assure que la clé 'prix' existe pour la comparaison
            if catalogue[j].get('prix', float('inf')) < catalogue[min_idx].get('prix', float('inf')):
                min_idx = j
        catalogue[i], catalogue[min_idx] = catalogue[min_idx], catalogue[i]

def trier_catalogue_par_nom_dict(catalogue: list[dict]):
    """
    Trie le catalogue (liste de dictionnaires) par nom (ordre alphabétique, insensible à la casse)
    en utilisant l'algorithme de tri par sélection. Modifie la liste en place.
    """
    n = len(catalogue)
    for i in range(n - 1):
        min_idx = i
        for j in range(i + 1, n):
            # Assure que la clé 'nom' existe pour la comparaison
            nom_j = catalogue[j].get('nom', '').lower()
            nom_min_idx = catalogue[min_idx].get('nom', '').lower()
            if nom_j < nom_min_idx:
                min_idx = j
        catalogue[i], catalogue[min_idx] = catalogue[min_idx], catalogue[i]
```



### 2.4 Intégration et Démonstration (Programme Principal)



```python
def main_solution2():
    print("--- Démarrage du Gestionnaire de Catalogue (Solution 2 - Dictionnaires) ---")
    
    catalogue_courant_dict = list(catalogue_initial_dict)

    afficher_catalogue_dict(catalogue_courant_dict)

    # Test de la recherche
    nom_recherche = input("\nEntrez le nom d'un produit à rechercher : ")
    produit_trouve = rechercher_produit_par_nom_dict(catalogue_courant_dict, nom_recherche)
    if produit_trouve:
        print(f"Produit trouvé : {produit_trouve}")
    else:
        print(f"Le produit '{nom_recherche}' n'a pas été trouvé.")

    # Tri par prix
    print("\n--- Tri du catalogue par prix (croissant) ---")
    trier_catalogue_par_prix_dict(catalogue_courant_dict)
    afficher_catalogue_dict(catalogue_courant_dict)

    # Tri par nom
    print("\n--- Tri du catalogue par nom (alphabétique) ---")
    trier_catalogue_par_nom_dict(catalogue_courant_dict)
    afficher_catalogue_dict(catalogue_courant_dict)

    print("--- Fin du Gestionnaire de Catalogue (Solution 2 - Dictionnaires) ---")

# Pour exécuter cette solution, décommenter la ligne ci-dessous:
# main_solution2()
```



### 2.5 Réflexion et Amélioration

1.  **Utilisation de l'IA :**
    Pour cette solution basée sur les dictionnaires, mes prompts à l'IA auraient été similaires, mais en spécifiant l'utilisation de dictionnaires. Par exemple :
    *   "Comment représenter des produits avec des dictionnaires dans une liste Python ?"
    *   "Écris une fonction Python pour afficher une liste de dictionnaires représentant des produits."
    *   "Comment implémenter une recherche linéaire dans une liste de dictionnaires Python par la valeur d'une clé (nom), en ignorant la casse ?"
    *   "Adapte l'algorithme de tri par sélection pour trier une liste de dictionnaires par la valeur d'une clé numérique (prix)."
    *   "Adapte le tri par sélection pour trier une liste de dictionnaires par la valeur d'une clé de chaîne (nom) en ordre alphabétique, insensible à la casse."
    L'IA aurait pu générer du code fonctionnel, mais j'aurais dû m'assurer que les accès aux clés (`produit['nom']`) sont robustes (par exemple, en utilisant `produit.get('nom', '')` pour éviter les erreurs si une clé est manquante) et que la logique de tri est correcte pour les comparaisons de chaînes.

2.  **Performance de la recherche :**
    La performance de la recherche linéaire reste **O(N)**, identique à la solution avec des objets. Pour 100 000 produits, le temps de recherche serait proportionnel à ce nombre.
    **Idée d'amélioration :** Si la recherche par nom est très fréquente et le catalogue est trié par nom, une **recherche dichotomique** serait l'amélioration la plus pertinente (O(log N)). Si la recherche par `id` est fréquente et les `id` sont uniques, l'utilisation d'un **dictionnaire (ou table de hachage)** où les clés sont les `id` et les valeurs sont les produits permettrait une recherche en **O(1)** en moyenne.

3.  **Efficacité du tri par sélection :**
    Le tri par sélection, qu'il s'agisse d'objets ou de dictionnaires, conserve sa complexité de **O(N²)**. Il est simple à comprendre et à implémenter, mais moins efficace pour de grands ensembles de données.
    Un autre algorithme de tri est le **Tri Rapide (Quick Sort)**. Il fonctionne en choisissant un "pivot", puis en partitionnant le tableau en deux sous-tableaux : les éléments plus petits que le pivot et les éléments plus grands. Il trie ensuite récursivement les sous-tableaux. Sa complexité moyenne est **O(N log N)**, mais son pire cas est O(N²). Il est souvent plus rapide en pratique que le Tri Fusion car il effectue le tri "in-place" (sans mémoire supplémentaire significative pour la fusion).

4.  **Robustesse du gestionnaire :**
    Les mêmes améliorations de robustesse que pour la Solution 1 s'appliquent ici :
    *   **Validation des entrées :** S'assurer que les valeurs saisies par l'utilisateur correspondent aux types attendus (entier pour `id` et `quantiteStock`, flottant pour `prix`).
    *   **Gestion des clés manquantes :** Utiliser `produit.get('cle', valeur_par_defaut)` lors de l'accès aux données pour éviter les `KeyError` si un dictionnaire n'a pas une clé attendue.
    *   **Unicité de l'ID :** Lors de l'ajout de nouveaux produits, vérifier que l'`id` n'est pas déjà utilisé.
    *   **Fonctionnalités complètes :** Implémenter des fonctions pour ajouter, modifier, et supprimer des produits du catalogue.
    *   **Persistance :** Sauvegarder et charger le catalogue depuis un fichier (par exemple, au format JSON, qui est très adapté aux listes de dictionnaires en Python).


    Voici **la traduction complète et pédagogique de ce corrigé en langage C**, en conservant **la logique algorithmique**, les **commentaires explicatifs** et l’**esprit TP**.
En C, il n’y a **ni classes ni dictionnaires natifs** :

* les **classes Python → `struct` en C**
* les **listes → tableaux**
* les **dictionnaires → `struct` également** (avec accès direct aux champs)

---

# Chapitre 3 – Solution en C

### Catalogue avec `struct Produit` et tri par sélection

---

## 3.1 Modélisation du catalogue

### Structure `Produit`

```c
#include <stdio.h>
#include <string.h>
#include <ctype.h>

#define MAX_PRODUITS 100
#define MAX_NOM 50

typedef struct {
    int id;
    char nom[MAX_NOM];
    float prix;
    int quantiteStock;
} Produit;
```

---

### Affichage du catalogue

```c
void afficher_catalogue(Produit catalogue[], int taille) {
    if (taille == 0) {
        printf("Le catalogue est vide.\n");
        return;
    }

    printf("\n--- Catalogue des Produits ---\n");
    for (int i = 0; i < taille; i++) {
        printf("ID: %d, Nom: %s, Prix: %.2f€, Stock: %d\n",
               catalogue[i].id,
               catalogue[i].nom,
               catalogue[i].prix,
               catalogue[i].quantiteStock);
    }
    printf("----------------------------\n");
}
```

---

### Initialisation du catalogue

```c
Produit catalogue_initial[] = {
    {101, "Ordinateur Portable", 1200.50, 15},
    {102, "Souris Sans Fil", 25.99, 50},
    {103, "Clavier Mecanique", 80.00, 20},
    {104, "Ecran 27 pouces", 300.00, 10},
    {105, "Webcam HD", 45.50, 30},
    {106, "Disque Dur Externe", 90.00, 25},
    {107, "Casque Gaming", 110.00, 18}
};

int taille_catalogue = 7;
```

---

## 3.2 Recherche linéaire par nom (insensible à la casse)

```c
int comparer_sans_casse(const char *a, const char *b) {
    while (*a && *b) {
        if (tolower(*a) != tolower(*b))
            return 0;
        a++;
        b++;
    }
    return *a == *b;
}

Produit* rechercher_produit_par_nom(Produit catalogue[], int taille, char nom[]) {
    for (int i = 0; i < taille; i++) {
        if (comparer_sans_casse(catalogue[i].nom, nom)) {
            return &catalogue[i];
        }
    }
    return NULL;
}
```

---

## 3.3 Tri par sélection

### Tri par prix

```c
void trier_par_prix(Produit catalogue[], int taille) {
    for (int i = 0; i < taille - 1; i++) {
        int min = i;
        for (int j = i + 1; j < taille; j++) {
            if (catalogue[j].prix < catalogue[min].prix) {
                min = j;
            }
        }
        Produit temp = catalogue[i];
        catalogue[i] = catalogue[min];
        catalogue[min] = temp;
    }
}
```

---

### Tri par nom (alphabétique, insensible à la casse)

```c
int strcmp_sans_casse(const char *a, const char *b) {
    while (*a && *b) {
        char ca = tolower(*a);
        char cb = tolower(*b);
        if (ca != cb)
            return ca - cb;
        a++;
        b++;
    }
    return tolower(*a) - tolower(*b);
}

void trier_par_nom(Produit catalogue[], int taille) {
    for (int i = 0; i < taille - 1; i++) {
        int min = i;
        for (int j = i + 1; j < taille; j++) {
            if (strcmp_sans_casse(catalogue[j].nom, catalogue[min].nom) < 0) {
                min = j;
            }
        }
        Produit temp = catalogue[i];
        catalogue[i] = catalogue[min];
        catalogue[min] = temp;
    }
}
```

---

## 1.4 Programme principal

```c
int main() {
    afficher_catalogue(catalogue_initial, taille_catalogue);

    char recherche[MAX_NOM];
    printf("\nEntrez le nom d'un produit a rechercher : ");
    fgets(recherche, MAX_NOM, stdin);
    recherche[strcspn(recherche, "\n")] = 0;

    Produit *p = rechercher_produit_par_nom(catalogue_initial, taille_catalogue, recherche);
    if (p != NULL) {
        printf("Produit trouve : %s (%.2f€)\n", p->nom, p->prix);
    } else {
        printf("Produit non trouve.\n");
    }

    printf("\n--- Tri par prix ---\n");
    trier_par_prix(catalogue_initial, taille_catalogue);
    afficher_catalogue(catalogue_initial, taille_catalogue);

    printf("\n--- Tri par nom ---\n");
    trier_par_nom(catalogue_initial, taille_catalogue);
    afficher_catalogue(catalogue_initial, taille_catalogue);

    return 0;
}
```

---

# Réflexion algorithmique (valable en C)

| Problème                              | Complexité          |
| ------------------------------------- | ------------------- |
| Recherche linéaire                    | **O(N)**            |
| Tri par sélection                     | **O(N²)**           |
| Recherche dichotomique (tableau trié) | **O(log N)**        |
| Table de hachage (ID → produit)       | **O(1)** en moyenne |

