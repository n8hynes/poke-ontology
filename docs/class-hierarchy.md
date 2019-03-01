# Class Hierarchy

The hierarchy was built to relate Pokemon to some of their core attributes: the moves they can learn, and the types of the pokemon and their moves. For brevity on this assignment, only a selection of given Pokemon, Moves, and Machines were chosen. Specifically, only the first 9 numbered Pokemon (the 3 starter Pokemon of this generation and their evolutions), the first 5 numbered TMs and HMs, and the moves associated with those Machines. The structure for remaining Pokemon, Moves, and Machines would be similar to the current existing classes. 

All Pokemon types introduced in Generation I are represented as subclasses of PokemonType. Note that while types are associated with both Pokemon and Moves, the simpler class name "Type" was unavailable due to it being a protected term in this context.

Additional annotations:
* Each Pokemon has annotations to record the metadata: Pokedex number, height, and weight. 
* Each TM and HM has annotations to record the metadata: location, purchase price, sell price, and required badge (if applicable).
* Each Move has annotations to record the metadata: accuracy, power, and PP (if applicable).

## Hierarchy:

List level indicates subclasses.

* Pokemon
    * *Defined class:* DualTypePokemon
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
