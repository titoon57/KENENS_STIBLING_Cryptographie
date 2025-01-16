# Exercice de Cryptographie : Implémentation de KeyExpansion pour AES

Ce projet implémente l'expansion de clé pour l'algorithme de chiffrement AES (Advanced Encryption Standard). L'expansion de clé est une étape cruciale de l'AES où la clé d'entrée est transformée en plusieurs sous-clés utilisées pour chaque tour de chiffrement.

## Structure du Code

### Variables Importantes
- **Nb** : Nombre de colonnes dans l'état (toujours 4 pour AES).
- **Nk** : Nombre de mots dans la clé d'entrée (4 pour une clé de 128 bits).
- **Nr** : Nombre de tours de chiffrement (Nk + 6).

### Tables Utilisées
- **SBox** : Table de substitution utilisée pour remplacer les octets dans la transformation `SubWord`.
- **Rcon** : Tableau des constantes de tour, utilisées pour l'opération XOR lors de l'expansion de clé.

### Fonctions Principales
1. **`SubWord(word)`** :
   - Remplace chaque octet d'un mot par son équivalent dans la table `SBox`.

2. **`RotWord(word)`** :
   - Effectue une rotation circulaire à gauche des octets d'un mot.

3. **`KeyExpansion(key)`** :
   - Génère les clés étendues utilisées pour chaque tour de l'AES.
   - Divise d'abord la clé d'entrée en mots de 4 octets.
   - Étend ces mots pour générer un tableau de mots, en appliquant `SubWord`, `RotWord`, et XOR avec `Rcon`.

## Exécution du Code

### Étapes
1. **Clé d'entrée** : La clé de chiffrement est spécifiée sous la forme d'un tableau d'octets.
   - Exemple : `[0x2b, 0x7e, 0x15, 0x16, 0x28, 0xae, 0xd2, 0xa6, 0xab, 0xf7, 0x15, 0x88, 0x09, 0xcf, 0x4f, 0x3c]`.

2. **Génération des clés étendues** :
   - Appelle la fonction `KeyExpansion` pour générer les clés étendues nécessaires pour AES.

3. **Sortie** :
   - Le programme affiche les clés étendues dans la console.

### Commande pour Exécuter
Assurez-vous d'avoir [Node.js](https://nodejs.org/) installé sur votre machine, puis exécutez :

```bash
node index.js
