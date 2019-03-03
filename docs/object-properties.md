# Object Properties

* **evolvesTo**
    * Domain: Pokemon
    * Range: Pokemon
    * Inverse: evolvesFrom
    * Characteristics: Asymmetric, Irreflexive.
* **hasPokemonType**
    * Domain: Pokemon
    * Range: PokemonType
    * Inverse: isTypeOfPokemon
    * Characteristics: Asymmetric, Irreflexive.
* **hasMoveType**
    * Domain: PokemonMove
    * Range: PokemonType
    * Inverse: isTypeOfMove
    * Characteristics: Functional, Asymmetric, Irreflexive.
* **canLearn**
    * Domain: Pokemon
    * Range: PokemonMove
    * Inverse: canBeLearnedBy
    * Characteristics: Asymmetric, Irreflexive.
* **teachesMove**
    * Domain: Machine
    * Range: PokemonMove
    * Inverse: isTaughtBy
    * Characteristics: Functional, Asymmetric, Irreflexive.
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
