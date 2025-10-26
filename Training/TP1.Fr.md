# TP 1 - Début du projet

## Exercice 1
Ouvrez `board.DirectionTest` et créez des méthodes de test supplémentaires pour, par exemple, les directions sud, est et ouest.

## Exercice 2
Ouvrez la classe `board.OccupantTest` et implémentez les 3 tests vides :
1. Le test `noStartSquare()` vérifie qu’une unité n’a pas de case de départ, c’est-à-dire qu’une unité « n’a pas de case » au début.
2. Le test `testOccupy()` vérifie que l’unité a bien la case cible comme base après occupation. En d’autres termes, si une unité occupe une case basique (quelle qu’elle soit), l’une doit contenir l’autre.
3. Le test `testReoccupy()` vérifie que l’unité a bien la case cible comme base après une double occupation.

## Exercice 3
Ouvrez la classe `board.BoardTest` et implémentez les tests suivants :
1. `verifyWidth()` vérifie que la largeur du plateau est **égale à** sa largeur maximale.
2. `verifyHeight()` vérifie que la hauteur du plateau est **égale à** sa hauteur maximale.
3. Le test `testSquareAt` vérifie que les coordonnées X et Y sont bien sur le plateau.

**Remarque : le plateau (`Board`) est déjà déclaré dans la classe de test (voir la variable `board`), utilisez-le pour vos vérifications.  
Il se peut également que vous ayez besoin d’importer les assertions nécessaires depuis le module AssertJ, par exemple :  
`import static org.junit.jupiter.api.Assertions.__`  
Voici un lien vers la documentation d’AssertJ : [https://assertj.github.io/doc/#assertj-core-assertions-guide](https://assertj.github.io/doc/#assertj-core-assertions-guide)  
et pour JUnit : [https://docs.junit.org/5.0.1/api/org/junit/jupiter/api/Assertions.html](https://docs.junit.org/5.0.1/api/org/junit/jupiter/api/Assertions.html)**
