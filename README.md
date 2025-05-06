# Exploration des tailles de données en C

## Introduction

Comprendre la taille des différents types de données est fondamental en programmation C. Cet exercice vous permettra d'explorer comment les types de variables occupent différentes quantités de mémoire et comment cela affecte la portée des valeurs que vous pouvez stocker. Cette connaissance est essentielle pour optimiser l'utilisation de la mémoire et comprendre les limites de chaque type de données.

## Exercice

### Partie 1 : Découverte des tailles de types fondamentaux

Créez un programme C qui affiche la taille en octets de chacun des types de données fondamentaux suivants :

- `char`
- `int`
- `float`
- `double`
- `long`
- `long long`
- `short`
- `unsigned int`

Utilisez l'opérateur `sizeof()` pour déterminer la taille de chaque type.

Voici un exemple pour commencer :

```c
#include <stdio.h>

int main() {
    // Exemple pour le type char
    printf("Taille de char : %zu octets\n", sizeof(char));

    // Ajoutez le code pour les autres types de données ici

    return 0;
}
```

### Partie 2 : Exploration des valeurs limites

Modifiez votre programme pour afficher les valeurs minimales et maximales que peuvent stocker les types entiers suivants :

- `char`
- `unsigned char`
- `int`
- `unsigned int`

Pour ce faire, vous pouvez utiliser des valeurs numériques ou bien calculer ces limites en utilisant les propriétés des types (nombre de bits).

### Partie 3 : Démonstration de dépassement (overflow)

Créez une démonstration simple qui montre ce qui se passe lorsqu'un type de donnée dépasse sa valeur maximale. Votre programme devrait :

1. Déclarer une variable de type `unsigned char`
2. L'initialiser à sa valeur maximale
3. Incrémenter cette valeur
4. Afficher le résultat avant et après l'incrémentation

## Résultat attendu

Votre programme doit afficher un résultat similaire à celui-ci :

```
TAILLES DES TYPES DE DONNÉES :
Taille de char : 1 octet(s)
Taille de int : 4 octet(s)
Taille de float : 4 octet(s)
Taille de double : 8 octet(s)
Taille de long : 8 octet(s)
Taille de long long : 8 octet(s)
Taille de short : 2 octet(s)
Taille de unsigned int : 4 octet(s)

VALEURS LIMITES :
char : min = -128, max = 127
unsigned char : min = 0, max = 255
int : min = -2147483648, max = 2147483647
unsigned int : min = 0, max = 4294967295

DÉMONSTRATION DE DÉPASSEMENT :
Valeur avant incrémentation (unsigned char à max) : 255
Valeur après incrémentation : 0
```

## Astuces

- Les tailles des types de données peuvent varier selon l'architecture de votre système et le compilateur. Il est donc important de vérifier ces tailles sur votre propre machine.
- Pour les limites des types entiers, vous pouvez soit les coder en dur, soit les calculer en utilisant le nombre de bits dans le type (par exemple, 2^n - 1 pour la valeur maximale d'un type unsigned de n bits).
- Le comportement de dépassement est défini pour les types non signés (retour à zéro), mais est indéfini pour les types signés en C.
- Notez que le terme français "octet" correspond au terme anglais "byte". Dans la documentation en anglais, vous verrez souvent "byte" à la place d'"octet", mais ils désignent tous deux une unité de 8 bits.

## Pour aller plus loin

Si vous souhaitez approfondir ce sujet, vous pourriez explorer :

- L'utilisation des types de données de la bibliothèque `<stdint.h>` (comme `int8_t`, `uint32_t`) qui garantissent une taille précise indépendamment de la plateforme
- La création de structures personnalisées et le calcul de leur taille (qui peut inclure du "padding")
- L'exploration de l'alignement mémoire et comment il affecte la taille des structures

---

_Comprendre les tailles et les limites des types de données vous aidera à éviter des bugs subtils et à optimiser l'utilisation de la mémoire dans vos applications._
