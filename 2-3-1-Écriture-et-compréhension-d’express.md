# Types de données et expressions  
## Expressions arithmétiques et logiques  
### Écriture et compréhension d’expressions arithmétiques et logiques

Un algorithme repose sur des **expressions** permettant de manipuler des données pour produire des résultats. Ces expressions peuvent être **arithmétiques** (calculs numériques) ou **logiques** (conditions booléennes). Savoir les écrire correctement et les comprendre est essentiel pour modéliser un problème et automatiser sa résolution.

---

## 1. Expressions arithmétiques

Les expressions arithmétiques réalisent des opérations mathématiques sur des valeurs numériques (entiers ou réels).

### Opérateurs principaux

| Opérateur | Description             | Exemple         | Résultat       |
|-----------|-------------------------|-----------------|----------------|
| +         | Addition                | 5 + 3           | 8              |
| -         | Soustraction            | 10 - 4          | 6              |
| *         | Multiplication          | 7 * 2           | 14             |
| /         | Division                | 9 / 3           | 3              |
| %         | Modulo (reste division) | 10 % 3          | 1              |

### Priorités opératoires

1. Parenthèses  
2. Multiplication, division, modulo  
3. Addition, soustraction

### Exemple d’expression complexe

```pseudo
resultat = (a + b) * c / d - e % f
```

Cette expression est évaluée en suivant les règles de priorité.

---

## 2. Expressions logiques

Les expressions logiques évaluent à une valeur booléenne : **vrai** ou **faux**. Elles permettent de construire des conditions utiles pour la prise de décision dans un algorithme.

### Opérateurs logiques de base

| Opérateur  | Description                 | Exemple               | Résultat    |
|------------|-----------------------------|-----------------------|-------------|
| ==         | Égalité                    | `x == 5`              | vrai/faux   |
| !=         | Différent                  | `y != 0`              | vrai/faux   |
| <          | Strictement inférieur      | `a < b`               | vrai/faux   |
| <=         | Inférieur ou égal          | `c <= d`              | vrai/faux   |
| >          | Strictement supérieur      | `e > f`               | vrai/faux   |
| >=         | Supérieur ou égal          | `g >= h`              | vrai/faux   |
| && (AND)   | Conjonction logique (ET)   | `(x > 0) && (y < 10)` | vrai/faux   |
| \|\| (OR)  | Disjonction logique (OU)   | `(a == b) \|\| (c > d)`| vrai/faux  |
| !          | Négation (NOT)             | `!(x == 0)`           | vrai/faux   |

### Exemple d’expression logique combinée

```pseudo
est_adulte = (age >= 18) && (pays == "France")
```

Cette expression vérifie que la personne est majeure en France.

---

## 3. Utilisation conjointe dans un algorithme

Les expressions arithmétiques et logiques sont souvent combinées pour gérer des calculs et des prises de décision.

### Exemple : contrôle d’éligibilité à une réduction

```pseudo
variable age : entier
variable revenu : réel
variable eligibilite : booléen

eligibilite = (age >= 18) && (revenu < 20000)
```

Ici, l’algorithme décide si une personne est éligible en fonction de deux critères : son âge et son revenu.

---

## Diagramme Mermaid : structure d’une expression

```mermaid
graph TD
    A[Expression] --> B[Expression arithmétique]
    A --> C[Expression logique]
    B --> D[Opérateurs +, -, *, /, %]
    C --> E[Comparaisons ==, !=, <, >]
    C --> F[Connecteurs &&, ||, !]
```

---

## Sources utilisées

- [OpenClassrooms - Les expressions et opérateurs](https://openclassrooms.com/fr/courses/6204541-initiez-vous-a-lalgorithmique/6262566-les-expressions-et-operateurs)  
- [Wikipedia - Expression (informatique)](https://fr.wikipedia.org/wiki/Expression_(informatique))  
- [Developpez.com - Expressions et opérateurs en programmation](https://cpp.developpez.com/cours/operateurs/?page=les_operateurs_en_c#les_operateurs_en_c)  

---

L’écriture et la compréhension des expressions arithmétiques et logiques conditionnent la capacité d’un algorithme à effectuer des calculs précis et à prendre des décisions adaptées. Ces fondations permettent de construire des programmes fonctionnels et intelligents.