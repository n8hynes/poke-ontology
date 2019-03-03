# poke-ontology

A pokemon ontology, created for INFO 6540.

## Scope

This ontology centers around the Pokemon species that are found in the first generation of Pokemon games (Pokemon Red and Blue). Within these video games, the players are tasked with catching and training wild creatures called Pokemon. These Pokemon come in various forms with vast differences between species. They can learn attacks ("moves") and are battled against one another. Specifically, the ontology includes information about Pokemon species, moves learned by Pokemon, and the elemental types of those pokemon and moves. 

For brevity on this assignment, only a selection of Pokemon, Moves, and Machines were chosen: The first 9 numbered Pokemon (the 3 starter Pokemon of this generation and their evolutions) and the Eevee evolution family, the first 5 numbered TMs and HMs, and the moves associated with those Machines. A complete ontology would include a total of 151 Pokemon, 165 moves, and 50 Technical Machines. The structure for remaining Pokemon, Moves, and Machines would be similar to the current existing classes.

The chosen Pokemon demonstrate several properties represented by the ontology: Pokemon with both single and dual-types, and the anomoly that is Eevee, the only Pokemon to have a branching evolution path, having the possibility of evolving into one of three other Pokemon.

All Pokemon types introduced in Generation I are represented as subclasses of PokemonType. (Note that while types are associated with both Pokemon and Moves, the simpler class name "Type" was unavailable due to it being a protected term in this context.)

## Class Hierarchy

At the top level of the hierarchy are the four main categories of Things that are defined by this ontology: Machines (the items that teach Pokemon specific moves), Pokemon (the creatures' species), PokemonMove (the moves that can be learned by Pokemon), and PokemonType (the set of elemental types assigned to each Pokemon and Move). Each of these, as well as each set of sibling subclasses, are disjoint, as there is no overlap between these categories.

As subclasses of Pokemon, there are two Defined Classes to categorize Pokemon as either a Single-type or Dual-type pokemon, according to how many types have been assigned to that Pokemon (1 or 2). These classes are also disjoint with one another. 

Additional annotations:
* Each Pokemon has annotations to record the metadata: Pokedex number, height, and weight. 
* Each TM and HM has annotations to record the metadata: location, purchase price, sell price, and required badge (if applicable).
* Each Move has annotations to record the metadata: accuracy, power, and PP (if applicable).

## Object Properties

The Object Properties (/ their inverses) included in this ontology encompass the varying relationships between Pokemon, Moves, Machines, and Types:
* (Pokemon) canLearn (Move) / canBeLearnedBy
* (Type) doesDoubleDamageTo (Type) / takesDoubleDamageFrom
* (Type) doesHalfDamageTo (Type) / takesHalfDamageFrom
* (Type) doesNoDamageTo (Type) / takesNoDamageFrom
* (Pokemon) evolvesTo (Pokemon) / evolvesFrom
* (Move) hasMoveType (Type) / isTypeOfMove
* (Pokemon) hasPokemonType (Type) / isTypeOfPokemon
* (Machine) teachesMove (Move) / isTaughtBy

In cases where the domain and range are disjoint (canLearn, hasMoveType, hasPokemonType, and teachesMove), it follows that the relationships are asymmetric, irreflexive, and not transitive.

The only functional relationships are hasMoveType and teachesMove - for these, each element in the domain is linked to exactly one element in the range (each Move has exactly 1 type, each machine teaches exactly 1 move). Their inverses (isTypeOfMove and isTaughtBy) are therefore inverse functional.

The damage modification properties (doesDoubleDamageTo, doesHalfDamageTo, and doesNoDamageTo) have no relation characteristics as exceptions can be found in each case. These relationships are defined by a specific table [(Found here)](https://bulbapedia.bulbagarden.net/wiki/Type/Type_chart#Generation_I) which does not follow any of these characteristics.

The evolvesTo relationship is not functional, as there exists Pokemon (Eevee) that can evolve into more than one other species of Pokemon (Vaporeon, Jolteon, and Flareon). Depending on the definition of evolvesTo, the relationship could be considered transitive (Bulbasaur evolvesTo Ivysaur, Ivysaur evolvesTo Venusaur, so Bulbasaur evolvesTo Venusaur). However, in this ontology evolvesTo is used as a single step in an evolution chain, and so is not transitive.

## Triples

Each Pokemon in the hierarchy is part of many triples, linking each of them to their types, their evolutions, and the moves they can learn. The higher level "Pokemon" class is also part of triples to limit the number of types linked to a Pokemon in general - a minimum of one and a maximum of two. For the Pokemon types, a closure axiom was used to ensure that the defined subclasses DualTypePokemon and SingleTypePokemon infer their members appropriately. For example, Charizard:
* hasPokemonType exactly 1 FireType
* hasPokemonType exactly 1 FlyingType
* hasPokemonType only (FireType or FlyingType)
These triples, combined with the inherited "hasPokemonType max 2 PokemonType" from the Pokemon class, means that Charizard has exactly 2 types, and so will be inferred to be a DualTypePokemon when the reasoner is run. 

Closure axioms were also used when defining the damage modification properties for the PokemonTypes, to ensure that the relationships between types are consistant and accurate with the data from the Pokemon games.
