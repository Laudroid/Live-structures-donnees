Bonjour à toutes et à tous,

Ce TP est conçu pour renforcer votre compréhension des expressions en programmation, en mettant l'accent sur la priorité des opérateurs et la gestion des types de données. Ces concepts sont fondamentaux pour écrire du code fiable et prédictible, et ils sont la base de manipulations de données plus complexes que vous rencontrerez dans les structures de données.

---

### **TP : Expressions, Types et Priorités - Calcul de Moyenne Pondérée**

**Contexte & Objectif :**
Dans le développement logiciel, la manipulation correcte des données est fondamentale. Cela inclut la capacité à écrire des expressions mathématiques ou logiques qui respectent non seulement la syntaxe du langage, mais aussi l'ordre d'exécution des opérations et la cohérence des types de données.

L'objectif de ce TP est de vous entraîner à écrire des expressions claires et correctes, en portant une attention particulière à la priorité des opérateurs et à la gestion des types, à travers un cas pratique de calcul de moyenne pondérée.

**Prérequis :**
*   Connaissances de base en programmation (déclaration de variables, affectation, types numériques).
*   Un environnement de développement configuré pour le langage de votre choix (Python, Java, C#, C++, JavaScript, etc.).

---

**Énoncé du Mini-Projet : Gestion des Notes de Module**

Vous devez développer un petit programme permettant de calculer la note finale d'un module pour un étudiant. Cette note est calculée à partir de trois évaluations, chacune ayant un coefficient différent :

*   **Note de TP :** Coefficient 2
*   **Note de Projet :** Coefficient 3
*   **Note d'Examen Final :** Coefficient 5

Toutes les notes sont sur 20. La note finale doit être affichée avec une précision d'au moins deux décimales.

---

**Tâches à Réaliser :**

1.  **Déclaration et Initialisation des Variables :**
    *   Déclarez trois variables pour stocker les notes (par exemple, `note_tp`, `note_projet`, `note_examen`).
    *   Déclarez trois variables pour leurs coefficients respectifs (par exemple, `coef_tp`, `coef_projet`, `coef_examen`).
    *   Choisissez les types de données appropriés pour ces variables (entiers ou flottants, selon votre interprétation initiale et les contraintes du langage).
    *   Initialisez-les avec des valeurs de votre choix (par exemple : Note TP = 15, Note Projet = 12.5, Note Examen = 18).

2.  **Écriture de l'Expression de Calcul :**
    *   Écrivez l'expression qui calcule la moyenne pondérée. Rappelez-vous que la moyenne pondérée est la somme des produits (note \* coefficient) divisée par la somme des coefficients.
    *   **Point d'attention :** Assurez-vous d'utiliser les parenthèses nécessaires pour garantir que les multiplications sont effectuées avant les additions, et que la somme pondérée est divisée par la somme des coefficients.

3.  **Gestion des Types et Précision :**
    *   Exécutez votre programme. Observez le résultat affiché pour la moyenne.
    *   Si la moyenne est affichée comme un entier (par exemple, `14` au lieu de `14.35`), identifiez la cause (souvent liée à la division entière entre entiers) et corrigez-la pour obtenir un résultat flottant.

4.  **Affichage du Résultat :**
    *   Affichez la note finale de manière claire et conviviale, en indiquant par exemple : "La note finale du module est : XX.YY".
    *   Assurez-vous que la note est affichée avec au moins deux décimales de précision.

5.  **Expérimentation et Vérification (avec l'aide de l'IA) :**
    *   **Priorité des opérateurs :** Modifiez volontairement l'expression de calcul en retirant certaines parenthèses que vous jugiez importantes. Que se passe-t-il ? Le résultat est-il le même ? Pourquoi ?
    *   **Tests :** Demandez à l'IA de générer un jeu de valeurs de notes et coefficients pour lequel le calcul manuel est facile à vérifier (par exemple, toutes les notes à 10, ou des coefficients simples comme 1, 1, 1). Utilisez ces valeurs pour tester votre programme.

---

**Consignes Générales :**

*   Choisissez un langage de programmation que vous maîtrisez ou que vous souhaitez explorer.
*   Commentez votre code pour expliquer les étapes importantes, notamment l'expression de calcul et les ajustements de type.
*   Testez votre programme avec différentes valeurs de notes pour vérifier sa robustesse.
*   Soyez attentifs aux messages d'erreur ou aux avertissements de votre compilateur/interpréteur ; ils sont souvent de bons indicateurs de problèmes de type ou de syntaxe.

---

Ce TP vous aidera à solidifier votre compréhension des bases essentielles de la programmation, qui sont cruciales pour aborder des concepts plus avancés en structures de données. Bon courage !