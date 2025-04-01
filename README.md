# Runtrack-C



🏆 Job 2 - Jour 1 : my_strlen
📖 Qu'est-ce que my_strlen doit faire ?
La fonction my_strlen calcule la longueur d'une chaîne de caractères en comptant combien de lettres il y a avant le caractère '\0', qui marque la fin de la chaîne.

Exemple avec "Bonjour" en mémoire :
----------------------------------
| B	| o |	n |	j |	o |	u	| r |	\0 | 
----------------------------------
Ici, la fonction doit renvoyer 7.

⚙️ Comment fonctionne my_strlen ?
On démarre au début de la chaîne
→ On initialise un compteur à 0.

On avance lettre par lettre
→ Tant qu'on ne rencontre pas '\0', on incrémente le compteur.

On s’arrête à '\0'
→ On retourne le compteur, qui contient la longueur de la chaîne.
