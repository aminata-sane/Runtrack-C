# Runtrack-C



## 🏆 **Job 2 - Jour 1 : my_strlen**
📖 **Qu'est-ce que my_strlen doit faire ?**

La fonction my_strlen calcule la longueur d'une chaîne de caractères en comptant combien de lettres il y a avant le caractère '\0', qui marque la fin de la chaîne.

Exemple avec "Bonjour" en mémoire :

| B	| o |	n |	j |	o |	u	| r |	\0 | 

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

