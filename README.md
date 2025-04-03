# Runtrack-C



## 🏆 **Job 2 - Jour 1 : my_strlen**
📖 **Qu'est-ce que my_strlen doit faire ?**

La fonction my_strlen calcule la longueur d'une chaîne de caractères en comptant combien de lettres il y a avant le caractère '\0', qui marque la fin de la chaîne.

Exemple avec "Bonjour" en mémoire :

| B	| o |	n |	j |	o |	u	| r |	\0 | 
|-----|---|---|-----|-----|------|---|----|

Ici, la fonction doit renvoyer 7.

⚙️ **Comment fonctionne my_strlen ?**
On démarre au début de la chaîne
→ On initialise un compteur à 0.

On avance lettre par lettre
→ Tant qu'on ne rencontre pas '\0', on incrémente le compteur.

On s’arrête à '\0'
→ On retourne le compteur, qui contient la longueur de la chaîne.


## 🏆 **Job 3 - Jour 1 : Vérification des chiffres**  

### **🎯 Objectif du Job**  

Ce job consiste à écrire deux fonctions en C :  

1. **`char_is_digit`**  
   - Vérifie si un caractère est un chiffre (`'0'` à `'9'`).  
   - Retourne `1` si c'est un chiffre, sinon `0`.  

2. **`str_is_digit`**  
   - Vérifie si une chaîne **ne contient que des chiffres**.  
   - Retourne `1` si **tous** les caractères sont des chiffres, sinon `0`.  

---

### **📝 Étape 1 : Fonction `char_is_digit`**  

#### **Comment savoir si un caractère est un chiffre ?**  

En C, chaque caractère est représenté par un code ASCII :  

| Caractère | Code ASCII |
|-----------|------------|
| `'0'` | 48 |
| `'1'` | 49 |
| ... | ... |
| `'9'` | 57 |

Un caractère est un **chiffre** si son code ASCII est **entre** `48` et `57`, ou plus simplement entre `'0'` et `'9'`.


#### **Explications ligne par ligne :**
1. **`int char_is_digit(char c)`** :
   - La fonction prend un caractère `c` en paramètre.
   - Elle retourne un entier (`int`) : `1` ou `0`.

2. **`if (c >= '0' && c <= '9')`** :
   - Cette condition vérifie si le caractère `c` est compris entre `'0'` et `'9'`.
   - `'0'` et `'9'` sont des caractères, mais en C, ils sont comparés à leurs codes ASCII.

3. **`return 1;`** :
   - Si la condition est vraie, cela signifie que `c` est un chiffre, donc on retourne `1`.

4. **`return 0;`** :
   - Si la condition est fausse, cela signifie que `c` n'est pas un chiffre, donc on retourne `0`.

---

### **Étape 2 : Fonction `str_is_digit`**

#### **Comment vérifier si une chaîne contient uniquement des chiffres ?**

Pour vérifier si une chaîne contient uniquement des chiffres :
1. Parcourir chaque caractère de la chaîne.
2. Utiliser la fonction `char_is_digit` pour vérifier si chaque caractère est un chiffre.
3. Si un seul caractère n'est pas un chiffre, on retourne `0`.
4. Si tous les caractères sont des chiffres, on retourne `1`.

#### **Code de `str_is_digit`**

Voici comment écrire cette fonction dans un fichier `str_is_digit.c` :

```c
#include "char_is_digit.c"

int str_is_digit(char *str) {
    int i = 0; // Index pour parcourir la chaîne

    while (str[i] != '\0') { // Tant qu'on n'a pas atteint la fin de la chaîne
        if (!char_is_digit(str[i])) { // Si un caractère n'est pas un chiffre
            return 0; // La chaîne n'est pas composée uniquement de chiffres
        }
        i++; // Passe au caractère suivant
    }

    return 1; // Tous les caractères sont des chiffres
}
```

#### **Explications ligne par ligne :**
1. **`int str_is_digit(char *str)`** :
   - La fonction prend une chaîne de caractères `str` en paramètre.
   - Elle retourne un entier (`int`) : `1` ou `0`.

2. **`int i = 0;`** :
   - On initialise un index `i` à `0` pour parcourir la chaîne.

3. **`while (str[i] != '\0')`** :
   - Cette boucle parcourt la chaîne caractère par caractère.
   - Elle s'arrête quand elle rencontre `'\0'`, qui marque la fin de la chaîne.

4. **`if (!char_is_digit(str[i]))`** :
   - On utilise la fonction `char_is_digit` pour vérifier si le caractère `str[i]` est un chiffre.
   - Si ce n'est pas un chiffre (`!` signifie "non"), on retourne `0`.

5. **`i++;`** :
   - On passe au caractère suivant.

6. **`return 1;`** :
   - Si la boucle se termine sans trouver de caractère non numérique, on retourne `1`.

---

### **Étape 3 : Tester les fonctions**

Pour tester ces fonctions, crée un fichier main.c :

```c
#include <stdio.h>
#include "char_is_digit.c"
#include "str_is_digit.c"

int main() {
    char c = '5';
    char str1[] = "12345";
    char str2[] = "123a5";

    // Test de char_is_digit
    if (char_is_digit(c)) {
        printf("'%c' est un chiffre.\n", c);
    } else {
        printf("'%c' n'est pas un chiffre.\n", c);
    }

    // Test de str_is_digit
    if (str_is_digit(str1)) {
        printf("\"%s\" contient uniquement des chiffres.\n", str1);
    } else {
        printf("\"%s\" ne contient pas uniquement des chiffres.\n", str1);
    }

    if (str_is_digit(str2)) {
        printf("\"%s\" contient uniquement des chiffres.\n", str2);
    } else {
        printf("\"%s\" ne contient pas uniquement des chiffres.\n", str2);
    }

    return 0;
}
```

---

### **Étape 4 : Compiler et exécuter**

1. Compile les fichiers avec la commande suivante :

   ```bash
   gcc -o test main.c char_is_digit.c str_is_digit.c
   ```

2. Exécute le programme avec :

   ```bash
   ./test
   ```

---

### **Résultat attendu**

Si tout fonctionne correctement, le programme doit afficher :

```
'5' est un chiffre.
"12345" contient uniquement des chiffres.
"123a5" ne contient pas uniquement des chiffres.
```

---

### **Résumé de la logique**

1. **`char_is_digit` :**
   - Vérifie si un caractère est un chiffre en comparant sa valeur ASCII.

2. **`str_is_digit` :**
   - Parcourt une chaîne de caractères et utilise `char_is_digit` pour vérifier chaque caractère.

3. **Programme principal (`main.c`) :**
   - Teste les deux fonctions avec différents cas.

---



