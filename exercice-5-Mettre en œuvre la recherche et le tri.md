Bonjour à toutes et à tous,

Ce TP a pour but de vous faire manipuler deux opérations fondamentales en informatique : la recherche et le tri. Nous allons les appliquer dans le cadre d'un mini-projet concret pour mieux en saisir l'utilité.

---

## TP : Gestionnaire de Catalogue Produit Simplifié

### Objectif Pédagogique

*   Implémenter un algorithme de recherche linéaire dans un tableau d'objets.
*   Implémenter l'algorithme de tri par sélection pour organiser un tableau d'objets selon différents critères.
*   Comprendre l'impact de ces algorithmes sur la manipulation de données.

### Contexte du Mini-Projet

Vous êtes chargé(e) de développer un petit module pour gérer un catalogue de produits. Ce catalogue sera représenté par un tableau (ou une liste) d'objets `Produit`. Chaque `Produit` aura les caractéristiques suivantes :

*   `id` (entier unique)
*   `nom` (chaîne de caractères)
*   `prix` (nombre décimal)
*   `quantiteStock` (entier)

Votre programme devra permettre de :
1.  Afficher l'ensemble du catalogue.
2.  Rechercher un produit par son nom.
3.  Trier le catalogue par prix ou par nom.

### Prérequis

*   Connaissances de base en programmation (variables, types, boucles, conditions, fonctions/méthodes).
*   Compréhension des tableaux (ou listes) et des structures de données simples (objets/structs).

### Travail à Réaliser

#### Partie 1 : Modélisation du Catalogue

1.  **Définir la structure `Produit` :**
    *   Créez une structure (ou une classe, un dictionnaire selon votre langage) nommée `Produit` avec les attributs `id`, `nom`, `prix`, et `quantiteStock`.
2.  **Initialiser le catalogue :**
    *   Créez un tableau (ou une liste) nommé `catalogue` et ajoutez-y au moins 5 à 7 objets `Produit` avec des données variées (noms, prix, stocks différents).
    *   Exemple de données :
        *   `id: 101, nom: "Ordinateur Portable", prix: 1200.50, quantiteStock: 15`
        *   `id: 102, nom: "Souris Sans Fil", prix: 25.99, quantiteStock: 50`
        *   `id: 103, nom: "Clavier Mécanique", prix: 80.00, quantiteStock: 20`
        *   `id: 104, nom: "Écran 27 pouces", prix: 300.00, quantiteStock: 10`
        *   `id: 105, nom: "Webcam HD", prix: 45.50, quantiteStock: 30`
3.  **Fonction d'affichage du catalogue :**
    *   Écrivez une fonction `afficher_catalogue(catalogue)` qui prend en paramètre le tableau de produits et affiche les détails de chaque produit de manière lisible.

#### Partie 2 : Recherche d'un Produit

1.  **Implémentation de la recherche linéaire :**
    *   Écrivez une fonction `rechercher_produit_par_nom(catalogue, nom_recherche)` qui prend en paramètre le catalogue et le nom d'un produit à rechercher.
    *   Cette fonction doit parcourir le catalogue et retourner le premier produit trouvé dont le nom correspond (ignorer la casse pour une meilleure robustesse, par exemple "ordinateur" doit trouver "Ordinateur Portable").
    *   Si le produit n'est pas trouvé, la fonction doit retourner une valeur indiquant l'absence (par exemple `None`, `null`, ou un message spécifique).
2.  **Test de la recherche :**
    *   Dans votre programme principal, appelez cette fonction pour rechercher un produit existant et un produit inexistant. Affichez le résultat de la recherche.

#### Partie 3 : Tri du Catalogue par Sélection

L'algorithme de tri par sélection consiste à trouver le plus petit (ou le plus grand) élément dans la partie non triée du tableau et à l'échanger avec le premier élément de cette partie non triée. On répète l'opération jusqu'à ce que tout le tableau soit trié.

1.  **Tri par prix (ordre croissant) :**
    *   Écrivez une fonction `trier_catalogue_par_prix(catalogue)` qui implémente l'algorithme de tri par sélection pour trier le tableau de produits en fonction de leur `prix` par ordre croissant.
    *   La fonction doit modifier le tableau `catalogue` directement (tri "in-place").
2.  **Tri par nom (ordre alphabétique) :**
    *   Écrivez une deuxième fonction `trier_catalogue_par_nom(catalogue)` qui utilise le même principe de tri par sélection, mais cette fois pour trier les produits par leur `nom` par ordre alphabétique.
3.  **Tests des tris :**
    *   Affichez le catalogue initial.
    *   Appelez `trier_catalogue_par_prix` puis affichez le catalogue trié par prix.
    *   Appelez `trier_catalogue_par_nom` (sur le catalogue potentiellement déjà trié par prix) puis affichez le catalogue trié par nom.

#### Partie 4 : Intégration et Démonstration

1.  **Programme principal :**
    *   Organisez votre code dans une fonction `main()` ou un bloc principal.
    *   Le programme devra :
        *   Initialiser le catalogue.
        *   Afficher le catalogue initial.
        *   Demander à l'utilisateur un nom de produit à rechercher, puis afficher le résultat de la recherche.
        *   Trier le catalogue par prix et l'afficher.
        *   Trier le catalogue par nom et l'afficher.

### Partie 5 : Réflexion et Amélioration (Très Important !)

Cette partie est essentielle pour valider votre compréhension et votre esprit critique.

1.  **Utilisation de l'IA :**
    *   Si vous avez utilisé une IA (ChatGPT, Copilot, etc.) pour vous aider dans la rédaction du code ou la compréhension des algorithmes, décrivez précisément quelles parties du code ou de la logique vous avez générées ou adaptées.
    *   Expliquez comment vous avez vérifié et validé le code fourni par l'IA. Avez-vous trouvé des erreurs ? Des améliorations possibles ?
2.  **Performance de la recherche :**
    *   Pour un catalogue de 100 000 produits, quel serait l'impact sur les performances de votre fonction `rechercher_produit_par_nom` actuelle ? Expliquez pourquoi.
    *   Proposez une idée d'amélioration pour la recherche si le catalogue était très grand et *souvent trié* (sans implémenter le code, juste le principe).
3.  **Efficacité du tri par sélection :**
    *   Le tri par sélection est-il l'algorithme de tri le plus efficace en général ? Citez un autre algorithme de tri que vous connaissez (ou que vous avez recherché) et expliquez brièvement son principe et pourquoi il pourrait être plus ou moins efficace que le tri par sélection dans certains cas.
4.  **Robustesse du gestionnaire :**
    *   Comment pourriez-vous rendre votre gestionnaire de catalogue plus robuste ? (Par exemple, gérer les entrées utilisateur invalides, les produits en double, la suppression de produits, etc.)

---

### Consignes Générales

*   Choisissez le langage de programmation avec lequel vous êtes le plus à l'aise (Python, Java, C#, JavaScript, C++, etc.).
*   Commentez votre code pour en faciliter la lecture et la compréhension.
*   Structurez votre code de manière claire (fonctions/méthodes bien définies).
*   N'hésitez pas à poser des questions si vous rencontrez des difficultés. L'objectif est d'apprendre et de comprendre.

### Rendu

Vous devrez remettre :
1.  Le code source de votre programme.
2.  Un court rapport (fichier texte ou PDF) répondant aux questions de la "Partie 5 : Réflexion et Amélioration".

Bon courage !