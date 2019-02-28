# Object Properties

* **evolvesTo**: Evolution is a process in which a Pokémon changes into a different species of Pokémon. [(Source)](https://bulbapedia.bulbagarden.net/wiki/Evolution)
    * Domain: Pokemon
    * Range: Pokemon
    * Inverse: evolvesFrom
* **hasPokemonType**: A Pokémon may have either one or two types. [(Source)](https://bulbapedia.bulbagarden.net/wiki/Type)
    * Domain: Pokemon
    * Range: PokemonType
    * Inverse: isTypeOfPokemon
* **hasMoveType**: A move has exactly one type. [(Source)](https://bulbapedia.bulbagarden.net/wiki/Type)
    * Domain: PokemonMove
    * Range: PokemonType
    * Inverse: isTypeOfMove
* **canLearn**: There are three main methods of acquiring moves on a Pokémon: by leveling up, by use of Technical Machines and by use of Hidden Machines. [(Source)](https://bulbapedia.bulbagarden.net/wiki/Move#Learning_and_unlearning)
    * Domain: Pokemon
    * Range: PokemonMove
    * Inverse: canBeLearnedBy
* **teachesMove**: TMs and HMs teach compatible Pokémon a move. [(Source)](https://bulbapedia.bulbagarden.net/wiki/Item#TMs_.26_HMs)
    * Domain: Machine
    * Range: Move
    * Inverse: isTaughtBy
* **doesDoubleDamageTo**: If the type of a move is super effective against a type of its target, the damage done is double the normal amount. [(Source)](https://bulbapedia.bulbagarden.net/wiki/Type#Type_effectiveness)
    * Domain: PokemonType
    * Range: PokemonType
    * Inverse: takesDoubleDamageFrom
* **doesHalfDamageTo**: If the type of a move is not very effective against a type of its target, the damage done is half the normal amount. [(Source)](https://bulbapedia.bulbagarden.net/wiki/Type#Type_effectiveness)
    * Domain: PokemonType
    * Range: PokemonType
    * Inverse: takesHalfDamageFrom
* **doesNoDamageTo**: If the type of a move is not effective against a type of its target, the target is completely immune to it, and the move will deal no damage. [(Source)](https://bulbapedia.bulbagarden.net/wiki/Type#Type_effectiveness)
    * Domain: PokemonType
    * Range: PokemonType
    * Inverse: takesNoDamageFrom
