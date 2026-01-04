# Types de données et expressions  
## Priorité des opérateurs  
### Règles de priorité dans les expressions pour garantir la bonne évaluation

La **priorité des opérateurs** est un concept essentiel en algorithmique et en programmation. Elle détermine l'ordre dans lequel les différentes opérations dans une expression sont évaluées. Sans règles claires de priorité, une même expression pourrait être interprétée différemment, ce qui peut produire des résultats incorrects.

---

## 1. Pourquoi la priorité des opérateurs est-elle importante ?

Lorsqu’une expression contient plusieurs opérateurs, l’évaluation ne se fait pas forcément de gauche à droite. Par exemple :

```
3 + 4 * 5
```

Si on évalue de gauche à droite, on obtient `(3 + 4) * 5 = 7 * 5 = 35` ; mais avec la bonne priorité, la multiplication ayant la priorité sur l’addition, on calcule d’abord `4 * 5 = 20` puis `3 + 20 = 23`.  

---

## 2. Règles générales de priorité (du plus prioritaire au moins prioritaire)

| Niveau | Opérateurs                           | Description                      |  
|--------|------------------------------------|----------------------------------|  
| 1      | `()`                               | Parenthèses, forcent l’évaluation |  
| 2      | `!`                                | Négation logique (NOT)            |  
| 3      | `*`, `/`, `%`                      | Multiplication, division, modulo  |  
| 4      | `+`, `-`                           | Addition, soustraction             |  
| 5      | `==`, `!=`, `<`, `<=`, `>`, `>=`  | Comparaisons                      |  
| 6      | `&&`                              | ET logique (AND)                  |  
| 7      | `\|\|`                            | OU logique (OR)                   |  

---

## 3. Parenthèses : contrôle explicite de la priorité

Les **parenthèses** permettent de modifier l’ordre naturel d’évaluation et sont souvent utilisées pour clarifier une expression ou garantir un calcul voulu.

### Exemple

```
(3 + 4) * 5  = 7 * 5 = 35
```

Ici, la priorité naturelle de la multiplication est dépassée par la parenthèse. On calcule d’abord la somme puis la multiplication.

---

## 4. Exemples illustrés

- Expression :  

```  
a + b * c - d / e  
```

   Évaluation :  
   1. Multiplication `b * c`  
   2. Division `d / e`  
   3. Addition `a + (b*c)`  
   4. Soustraction `(a + b*c) - (d/e)`

- Expression avec parenthèses :  

```
(a + b) * (c - d) / e  
```

   Évaluation :  
   1. Somme `(a + b)`  
   2. Soustraction `(c - d)`  
   3. Multiplication des deux résultats  
   4. Division par `e`

---

## 5. Diagramme Mermaid illustrant la priorité

```mermaid
graph TD
    Start[Expression composite] --> P1[Parenthèses ()]
    P1 --> P2[Négation !]
    P2 --> P3[Multiplication *, Division /, Modulo %]
    P3 --> P4[Addition +, Soustraction -]
    P4 --> P5[Comparaisons ==, !=, <, <=, >, >=]
    P5 --> P6[ET logique &&]
    P6 --> P7[OU logique ||]
```

---

## 6. Impact sur l’écriture des algorithmes

- Une expression mal comprise ou mal parenthésée peut produire des erreurs logiques difficiles à déceler.
- Utiliser des parenthèses même quand elles ne sont pas strictement nécessaires améliore la lisibilité.
- En programmation, respecter les règles de priorité garantit que le code exécutera les calculs dans l’ordre attendu.

---

## Sources utilisées

- [OpenClassrooms - Priorité et associativité des opérateurs](https://openclassrooms.com/fr/courses/6204541-initiez-vous-a-lalgorithmique/6262566-les-expressions-et-operateurs#priority)  
- [Wikipedia - Priorité des opérateurs](https://fr.wikipedia.org/wiki/Priorit%C3%A9_des_op%C3%A9rateurs)  
- [Developpez.com - Priorité des opérateurs en C/C++](https://cpp.developpez.com/cours/syntaxe/?page=priorite)  

---

La maîtrise des règles de priorité des opérateurs garantit une évaluation correcte des expressions dans les algorithmes, évitant erreurs d’interprétation et assurant la fiabilité des résultats.