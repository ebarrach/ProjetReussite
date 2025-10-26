# TP 3 - Tests structurels et mocking

## Exercice 1

Analysez les exigences décrites dans `docs/scenarios.md` et dérivez une table de décision pour les collisions dans JPacman.  
Dans cette table de décision, vous encodez les conséquences des collisions entre deux entités.  
Vous pouvez ignorer les collisions qui ne peuvent pas arriver (par exemple, deux `Pellet` qui se rentrent dedans).

Construisez votre table de décision en vous basant sur le modèle ci-dessous.  
Attention : ce tableau est incomplet et peut avoir trop ou pas assez de colonnes.

|                 |        |       |        |    |
|-----------------|--------|-------|--------|----|
| **Collisionneur (Collider)**    | Ghost  | ??    | ??     | ?? |
| **Cible (Collidee)**            | Pellet | Ghost | Pellet | ?? |
| **Conséquence**                 | ??     | ??    | ??     | ?? |

À partir de cette table de décision, dérivez une suite de tests JUnit pour la classe `level.PlayerCollisions`, en utilisant à la fois :
- le cadre de **tests basés sur la spécification** (voir le fichier `analysis-template.md`)
- et le cadre de **tests structurels**.

Vous devez être aussi rigoureux que possible :
- Couvrez les collisions qui ont un effet visible (par ex. le joueur meurt, ramasse un pellet, etc.).
- Couvrez aussi les collisions où « il ne se passe rien ».

Exemple de choses à vérifier dans vos tests :
- Joueur ↔ Fantôme : le joueur meurt ?
- Joueur ↔ Pellet : le score augmente et le pellet disparaît ?
- Fantôme ↔ Pellet : rien ne se passe ?
- Deux fantômes : rien ne se passe ?
- etc.

Votre suite de tests doit donc vérifier chaque ligne/colonne de la table de décision.

## Exercice 2

La classe `PlayerCollisions` n’est pas idéale : elle ne passe pas bien à l’échelle si on complexifie les règles de collision.

Une alternative est `DefaultPlayerInteractionMap`, qui utilise la classe (plus générale) `CollisionInteractionMap`.

Réorganisez donc votre suite de tests de l’exercice 1 pour qu’elle puisse s’exécuter **à l’identique** sur :
- un objet `PlayerCollisions`
- et un objet `DefaultPlayerInteractionMap`.

Idée : factorisez les scénarios de collision dans des méthodes communes ou via une classe de test abstraite.  
Ensuite, créez deux classes de test concrètes qui héritent de cette base et fournissent l’implémentation à tester.

## BONUS

Écrivez une suite de tests pour la classe `nl.tudelft.jpacman.level.MapParser`.

1. Commencez par les cas « beau temps » :
    - la carte contient uniquement des caractères attendus ;
    - le parser construit bien le niveau (pas d’exception).

2. Ajoutez ensuite les cas « mauvais temps » :
    - la carte contient un caractère inconnu ;
    - la carte est invalide d’une autre façon ;
    - dans ces cas, le parser doit lever la bonne exception.

**Bonus avancé :**
- Utilisez Mockito pour mocker les *factories* utilisées par `MapParser`.
- Vérifiez, avec `verify`, que pour une carte donnée le parser appelle les bonnes méthodes des factories (par exemple création de murs, création de joueurs, etc.).
