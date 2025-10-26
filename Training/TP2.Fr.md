# TP 2 - Tests basés sur la spécification

On va se concentrer sur les mouvements des fantômes. Pour les exercices 1 et 2, utilisez la classe `GhostMapParser` pour écrire vos tests JUnit. N’hésitez pas à regarder comment fonctionne la classe parente `Ghost`.

## Exercice 1
Ouvrez la classe `npc.ghost.Clyde` et implémentez au moins 4 tests JUnit pour la méthode `Optional<Direction> nextAiMove()` dans une classe de test `ClydeTest`.  
Le principe du test basé sur la spécification est de dériver des cas de test à partir du comportement attendu, sans devoir tout comprendre de l’implémentation interne (voir le fichier `analysis-template.md`).

> Instancier un `Clyde` et l’ajouter sur une carte demande un peu de compréhension de JPacman. Voici un coup de pouce, basé sur la classe `GhostMapParser` :
> - Dans les tests, on doit construire un niveau à partir d’une carte. Cette carte doit être conçue en fonction du scénario que l’on veut tester. Par exemple, si la carte est une liste de chaînes comme :  
    >   `{"############", "#P________C#", "############"}`  
    >   (les caractères `_` doivent être remplacés par des espaces dans le code), alors PacMan (`P`) et Clyde (`C`) sont sur la même ligne, séparés de 8 colonnes.
> - La méthode fournie `GhostMapParser#parseMap()` reçoit la carte et renvoie un `Level` basé sur cette carte.
> - Si votre test implique un joueur sur la carte, n’oubliez pas de le créer (`PlayerFactory#createPacMan`), de l’enregistrer dans le niveau (`Level#registerPlayer`) et de définir sa direction (`Player#setDirection`).
> - Vous devez vérifier la direction que le fantôme choisit en fonction de sa position actuelle dans le niveau. Pour cela, vous devez récupérer le fantôme qui existe réellement dans le niveau créé. On vous fournit pour ça la méthode `Navigation#findUnitInBoard`.

## Exercice 2
Ouvrez la classe `npc.ghost.Inky` et regardez comment ce fantôme se comporte, en particulier sa méthode `nextAiMove`. Réfléchissez en termes de partitions / cas possibles : quels scénarios faut-il couvrir pour garantir que ce fantôme fonctionne correctement ?  
Lisez sa documentation et son code source. Utilisez toutes les infos disponibles et appliquez le cadre de test basé sur la spécification.

Implémentez au moins 5 tests JUnit (2 cas « beau temps » où tout est normal, et 3 cas « mauvais temps » où certaines conditions ne sont pas réunies) pour la méthode `Optional<Direction> nextAiMove()` dans une classe de test `InkyTest`.

## Exercice 3
La méthode `squaresAheadOf` dans la classe `Unit` n’est pas testée. Rédigez au moins 3 tests pour cette méthode en suivant la même approche de tests basés sur la spécification.

## BONUS
Il y a des TODOs dans la méthode `Optional<Direction> nextAiMove()` de la classe `npc.ghost.Blinky`.  
Implémentez ces TODOs, puis écrivez des tests pour vérifier le nouveau comportement.
