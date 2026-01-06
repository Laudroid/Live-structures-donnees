Bonjour à toutes et à tous,

Ce TP vise à renforcer votre maîtrise des boucles, un concept fondamental en programmation. Nous allons explorer leur utilisation à travers le calcul de la factorielle, un problème classique mais riche en enseignements. L'objectif est d'écrire des algorithmes clairs, fonctionnels et de développer une approche critique de votre code.

---

### **TP : Boucles et Factorielle - Du Concept à l'Optimisation**

**Objectif du TP :**
*   Écrire des algorithmes utilisant des boucles (`for` ou `while`).
*   Gérer les cas particuliers et les erreurs potentielles.
*   Développer une approche de test et de validation de code.
*   Réfléchir aux limites des types de données et aux différentes approches algorithmiques.

**Prérequis :**
*   Notions de variables, types de données (entiers).
*   Opérateurs arithmétiques de base.
*   Structures conditionnelles (`if`/`else`).
*   Compréhension de base de la syntaxe d'un langage de programmation (Python, Java, C#, JavaScript, etc., au choix).

---

**Consignes Générales (Utilisation de l'IA) :**

Vous êtes encouragés à utiliser des outils d'IA (ChatGPT, Copilot, etc.) pour vous aider dans ce TP. Cependant, l'objectif n'est pas de copier-coller une solution, mais de **comprendre, d'analyser et d'adapter le code généré**.

Utilisez l'IA comme un assistant intelligent :
*   Pour explorer des concepts ou des syntaxes que vous ne maîtrisez pas.
*   Pour générer des exemples de code que vous devrez ensuite critiquer et améliorer.
*   Pour vous aider à déboguer votre propre code.
*   Pour proposer des alternatives que vous analyserez.

La qualité de votre *compréhension*, de votre *analyse* et de votre *capacité à justifier vos choix* sera évaluée.

---

**Énoncé du TP :**

Écrire un algorithme qui calcule la factorielle d'un nombre entier positif donné en utilisant une boucle.

---

**Partie 1 : Implémentation Initiale**

1.1. **Fonction `calculer_factorielle(n)`**
    *   Créez une fonction (ou une méthode, selon votre langage) qui prend un entier `n` en entrée.
    *   À l'intérieur de cette fonction, utilisez une boucle (`for` ou `while`) pour calculer `n!` (n factorielle).
    *   **Gestion des cas particuliers :**
        *   `0!` doit retourner 1.
        *   Pour les nombres négatifs, la factorielle n'est pas définie dans ce contexte. Votre fonction doit gérer ce cas (par exemple, afficher un message d'erreur et/ou retourner une valeur spécifique comme -1 ou `None`).
    *   La fonction doit retourner le résultat du calcul.

1.2. **Tests Unitaires Simples**
    *   Dans votre programme principal, écrivez quelques appels à votre fonction `calculer_factorielle` avec des valeurs différentes (ex: 0, 1, 5, 10, -3).
    *   Affichez les résultats pour vérifier le bon fonctionnement de votre algorithme.

---

**Partie 2 : Robustesse et Limites**

2.1. **Gestion des Entrées Utilisateur**
    *   Modifiez votre programme pour qu'il demande à l'utilisateur de saisir un nombre entier.
    *   Assurez-vous que l'entrée est bien un entier valide. Si l'utilisateur saisit autre chose (du texte, un nombre décimal), votre programme doit le gérer proprement (par exemple, demander à nouveau la saisie ou afficher un message d'erreur clair).

2.2. **Limites de la Factorielle**
    *   Testez votre fonction avec des nombres de plus en plus grands (ex: 15, 20, 50, 100, 1000).
    *   Observez les résultats. Que se passe-t-il pour les très grands nombres ? Y a-t-il des limites au type de données utilisé par votre langage de programmation pour stocker ces grands nombres (dépassement de capacité ou "overflow") ?
    *   Documentez vos observations dans un petit commentaire ou un fichier texte séparé.

---

**Partie 3 : Réflexion et Analyse**

3.1. **Analyse de Complexité (Optionnel mais recommandé)**
    *   Quelle est la complexité temporelle de votre algorithme (en notation Big O) ? Justifiez votre réponse en fonction du nombre d'opérations effectuées par rapport à la taille de l'entrée `n`.

3.2. **Comparaison avec la Récursion**
    *   La factorielle peut aussi être calculée de manière récursive. Demandez à une IA de vous générer une version récursive de la fonction factorielle.
    *   Comparez les deux approches (boucle vs. récursion) en termes de :
        *   **Lisibilité :** Laquelle trouvez-vous la plus facile à comprendre ?
        *   **Efficacité :** Y a-t-il des différences en termes de consommation mémoire ou de temps d'exécution pour de grands nombres ? (Vous pouvez faire des tests si vous le souhaitez).
        *   **Cas d'usage :** Quand préférer l'une ou l'autre approche pour des problèmes similaires ?

3.3. **Utilisation de l'IA : Votre Expérience**
    *   Décrivez brièvement comment vous avez utilisé l'IA pour ce TP. Quels prompts avez-vous utilisés ? Qu'est-ce qui a été utile ? Qu'est-ce qui a été moins utile ou a nécessité une correction/adaptation de votre part ?
    *   Avez-vous trouvé des erreurs ou des imprécisions dans le code généré par l'IA ? Si oui, comment les avez-vous identifiées et corrigées ?

---

**Rendu :**

*   Un fichier de code source (ex: `factorielle.py`, `Factorielle.java`, `factorielle.cs`, etc.) contenant toutes les parties implémentées (Parties 1 et 2).
*   Un court rapport (fichier texte ou PDF) répondant aux questions de la Partie 3 et documentant vos observations de la Partie 2.2.

---

N'hésitez pas à expérimenter et à poser des questions si vous rencontrez des difficultés. Bon courage et amusez-vous bien !