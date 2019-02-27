# poke-ontology
Pokemon-focused ontology for INFO 6540

## Class Hierarchy

* Pokemon
    * Bulbasaur
    * Ivysaur
    * Venusaur
    * Charmander
    * Charmeleon
    * Charizard
    * Squirtle
    * Wartortle
    * Blastoise
* PokemonType
    * NormalType
    * FightingType
    * FlyingType
    * PoisonType
    * GroundType
    * RockType
    * BugType
    * GhostType
    * FireType
    * WaterType
    * GrassType
    * ElectricType
    * PsychicType
    * IceType
    * DragonType
* PokemonMove
    *  Mega Punch
    *  Razor Wind
    *  Swords Dance
    *  Whirlwind
    *  Mega Kick
    *  Cut
    *  Fly
    *  Surf
    *  Strength
    *  Flash
* Machine
    * TechnicalMachine
        * TM01
        * TM02
        * TM03
        * TM04
        * TM05
    * HiddenMachine
        * HM01
        * HM02
        * HM03
        * HM04
        * HM05
* EvolutionMethod
    * LevelUp
    * Trade
    * UseItem

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
