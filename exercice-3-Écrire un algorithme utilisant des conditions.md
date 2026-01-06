Bonjour à toutes et à tous,

Ce TP est conçu pour vous permettre de manipuler les structures conditionnelles, un pilier fondamental de la programmation. L'objectif n'est pas seulement d'écrire du code, mais de comprendre comment les programmes prennent des décisions logiques.

---

## TP : Classificateur Numérique Interactif

### Objectif du TP

*   Appliquer les structures conditionnelles (`if`, `elif`, `else`) pour classifier des données numériques.
*   Développer une approche structurée de résolution de problème, de la conception à l'implémentation.
*   Comprendre l'importance de la validation des entrées utilisateur.

### Contexte et Enjeu

Dans le domaine des structures de données et des algorithmes, la capacité à analyser et à catégoriser des informations est essentielle. Que ce soit pour trier des éléments, filtrer des données ou prendre des décisions basées sur des valeurs, les conditions sont omniprésentes. Ce mini-projet vous mettra en situation de créer un petit outil d'analyse numérique simple, mais dont les principes sont applicables à des systèmes bien plus complexes.

### Énoncé du Mini-Projet : "Classificateur Numérique Interactif"

Vous devez écrire un algorithme qui réalise les actions suivantes :

1.  **Initialisation :** Demander à l'utilisateur combien de nombres il souhaite analyser.
2.  **Saisie et Classification :** Pour chaque nombre demandé :
    *   Demander à l'utilisateur de saisir un nombre entier.
    *   Vérifier si ce nombre est positif, nul ou négatif.
    *   Afficher immédiatement le résultat de cette classification (par exemple : "Le nombre 5 est positif.").
    *   Tenir à jour un compte du nombre total de positifs, de négatifs et de zéros rencontrés.
3.  **Rapport Final :** Une fois tous les nombres saisis et classifiés, afficher un récapitulatif :
    *   Le nombre total de nombres positifs.
    *   Le nombre total de nombres négatifs.
    *   Le nombre total de nombres nuls.
4.  **Gestion des Erreurs (Optionnel mais recommandé) :** Si l'utilisateur saisit autre chose qu'un nombre (texte, etc.), le programme devrait l'informer de l'erreur et lui redemander une saisie valide pour le nombre courant.

### Instructions Détaillées

#### Étape 1 : Conception de l'Algorithme (Avant le code)

Avant de vous lancer dans l'écriture du code, prenez un moment pour réfléchir à la logique.

*   **Pseudocode ou Organigramme :** Esquissez les étapes principales de votre algorithme.
    *   Comment allez-vous demander le nombre de saisies ?
    *   Comment allez-vous répéter l'action de saisie et de classification ? (Indice : une boucle est nécessaire)
    *   Quelles conditions utiliserez-vous pour déterminer si un nombre est positif, nul ou négatif ?
    *   Comment allez-vous stocker les comptes (positifs, négatifs, zéros) ?
    *   Comment gérerez-vous les entrées invalides ?

#### Étape 2 : Implémentation (Avec ou Sans l'aide de l'IA)

C'est le moment de traduire votre conception en code. Vous êtes libre d'utiliser l'outil de programmation de votre choix (Python est souvent un bon point de départ pour ce type d'exercice).

**Approche recommandée avec l'IA :**

L'utilisation d'outils d'IA est une compétence précieuse. Voici comment vous pouvez l'intégrer de manière constructive dans ce TP :

1.  **Formulez des requêtes précises :**
    *   Au lieu de demander "Écris-moi le code pour le TP", essayez des requêtes plus ciblées :
        *   "Comment puis-je demander à l'utilisateur de saisir un nombre entier en Python et le stocker dans une variable ?"
        *   "Montre-moi un exemple de structure `if-elif-else` pour vérifier si un nombre est positif, négatif ou nul."
        *   "Comment puis-je créer une boucle qui se répète un certain nombre de fois en Python ?"
        *   "Comment gérer une erreur si l'utilisateur saisit du texte au lieu d'un nombre en Python ?"
2.  **Analysez le code généré :**
    *   **Ne copiez-collez pas aveuglément.** Lisez attentivement chaque ligne de code proposée par l'IA.
    *   **Expliquez le code :** Pour chaque partie significative (boucle, condition, gestion d'erreur), essayez d'expliquer à voix haute ou par écrit ce qu'elle fait. C'est le meilleur moyen de vérifier votre compréhension.
    *   **Identifiez les structures conditionnelles :** Mettez en évidence les `if`, `elif`, `else` et expliquez pourquoi ils sont utilisés à ces endroits précis.
3.  **Adaptez et personnalisez :**
    *   Le code généré par l'IA est un point de départ. Modifiez les messages affichés à l'utilisateur pour les rendre plus conviviaux.
    *   Ajoutez des commentaires pour expliquer votre propre logique ou les parties complexes.
    *   Si l'IA n'a pas inclus la gestion des erreurs, essayez de l'ajouter vous-même ou demandez à l'IA comment l'implémenter.
4.  **Comparez et apprenez :** Si vous avez d'abord essayé d'écrire le code vous-même, comparez votre solution avec celle de l'IA. Qu'est-ce qui est différent ? Y a-t-il des approches plus élégantes ou plus robustes ?

#### Étape 3 : Tests et Validation

Une fois votre code écrit, testez-le rigoureusement :

*   **Cas standards :**
    *   Saisissez uniquement des nombres positifs.
    *   Saisissez uniquement des nombres négatifs.
    *   Saisissez uniquement des zéros.
    *   Saisissez un mélange de positifs, négatifs et zéros.
*   **Cas limites :**
    *   Que se passe-t-il si l'utilisateur veut analyser 0 nombre ? (Votre programme devrait gérer cela élégamment, peut-être en affichant un message et en terminant).
    *   Que se passe-t-il si l'utilisateur saisit un très grand nombre ou un très petit nombre ?
*   **Gestion d'erreurs (si implémentée) :**
    *   Saisissez du texte au lieu d'un nombre. Le programme réagit-il comme attendu ?

### Livrables

Vous devrez soumettre les éléments suivants :

1.  **Votre pseudocode ou organigramme** (format texte, image ou PDF).
2.  **Le code source de votre programme** (fichier `.py`, `.js`, etc., selon le langage choisi).
3.  **Un court rapport (quelques paragraphes)** expliquant :
    *   Votre démarche générale pour résoudre le problème.
    *   Comment vous avez utilisé les structures conditionnelles (`if`, `elif`, `else`).
    *   Si vous avez utilisé une IA, décrivez comment elle vous a aidé, quelles requêtes vous avez faites, et surtout, comment vous avez analysé et adapté le code qu'elle a généré. Mettez en avant ce que vous avez appris grâce à cette interaction.

### Critères d'Évaluation

*   **Fonctionnalité :** Le programme répond-il à toutes les exigences de l'énoncé ?
*   **Correctitude :** Les classifications sont-elles exactes ? Les comptes sont-ils corrects ?
*   **Clarté du code :** Le code est-il lisible, bien structuré et commenté si nécessaire ?
*   **Compréhension :** Votre rapport démontre-t-il une bonne compréhension des concepts (conditions, boucles, gestion d'erreurs) ?
*   **Utilisation de l'IA (si applicable) :** L'IA a-t-elle été utilisée comme un outil d'apprentissage et non comme un simple générateur de solutions ? Votre analyse critique du code généré est-elle pertinente ?

---

N'hésitez pas à expérimenter et à poser des questions. L'objectif est de comprendre et de maîtriser ces concepts fondamentaux. Bon courage !