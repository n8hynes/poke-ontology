# poke-ontology
Pokemon-focused ontology for INFO 6540

## Class Hierarchy

Described in `class-hierarchy.md`

## Object Properties

* evolvesTo
    * Domain: Pokemon
    * Range: Pokemon
    * Inverse: evolvesFrom
* evolvesBy
    * Domain: Pokemon
    * Range: EvolutionMethod
    * Inverse: isEvolutionMethodOf
* hasPokemonType
    * Domain: Pokemon
    * Range: PokemonType
    * Inverse: isTypeOfPokemon
* hasMoveType:
    * Domain: PokemonMove
    * Range: PokemonType
    * Inverse: isTypeOfMove
* canLearn:
    * Domain: Pokemon
    * Range: PokemonMove
    * Inverse: canBeLearnedBy
* teachesMove:
    * Domain: Machine
    * Range: Move
    * Inverse: isTaughtBy
* doesDoubleDamageTo:
    * Domain: PokemonType
    * Range: PokemonType
    * Inverse: takesDoubleDamageFrom
* doesHalfDamageTo:
    * Domain: PokemonType
    * Range: PokemonType
    * Inverse: takesHalfDamageFrom
* doesNoDamageTo:
    * Domain: PokemonType
    * Range: PokemonType
    * Inverse: takesNoDamageFrom
