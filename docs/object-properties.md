# Object Properties

The properties chosen for inclusion in this ontology represent all the varying relationships between the classes. 

Many properties and their inverses have no characteristics (i.e. they are not functional, transitive, etc.). Most are not functional as they are one-to-many relations: hasPokemonType, canLearn, and the damage modifications. 

Properties that are functional (and hence their inverses are inverse functional):
- hasMoveType - each Move has exactly one move.
- teachesMove - each Machine teaches exactly one move.

## Properties:

* **evolvesTo**
    * Domain: Pokemon
    * Range: Pokemon
    * Inverse: evolvesFrom
    * Characteristics: None.
* **hasPokemonType**
    * Domain: Pokemon
    * Range: PokemonType
    * Inverse: isTypeOfPokemon
    * Characteristics: None.
* **hasMoveType**
    * Domain: PokemonMove
    * Range: PokemonType
    * Inverse: isTypeOfMove
    * Characteristics: Functional.
* **canLearn**
    * Domain: Pokemon
    * Range: PokemonMove
    * Inverse: canBeLearnedBy
    * Characteristics: None.
* **teachesMove**
    * Domain: Machine
    * Range: PokemonMove
    * Inverse: isTaughtBy
    * Characteristics: Functional.
* **doesDoubleDamageTo**
    * Domain: PokemonType
    * Range: PokemonType
    * Inverse: takesDoubleDamageFrom
    * Characteristics: None.
* **doesHalfDamageTo**
    * Domain: PokemonType
    * Range: PokemonType
    * Inverse: takesHalfDamageFrom
    * Characteristics: None.
* **doesNoDamageTo**
    * Domain: PokemonType
    * Range: PokemonType
    * Inverse: takesNoDamageFrom
    * Characteristics: None.
