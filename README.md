### SUBMISSION FOR MATCHBOXDAO HACKATHON on 09-OCT-2022

Background

We are proposing to build an expansion module named “Monsters” on Realms Eternum.


Features Completed
1. Monsters can be minted and it spawns randomly across the 8000 realms.    
2. Monster can attack the realm which it is spawned on and reduce the realms' raidable resources
    2.1 Monster fights the defending army of the realm
    2.2 Monster reduces its HP and increases its XP depending on the battle outcome
    2.3 Monster is dead when HP reduces below zero
3. All game state (Monsters' statistics) and game logic are on-chain
4. All game state changes are accompanied with Events being emited
5. View the demo video at https://youtu.be/GusnqytZNB8
6. Visit http://202.172.56.233:3000/ for the demo site

Additional learnings:
1. Implemented imageUrl as a long string for our Monsters' pictures
2. Modified random number generator method for a random value based on minimum and maximum parameters
3. Made use of protostar test (/realms-contracts/tests/protostar/settling_game/monsterrampage/test_monster_combat.cairo) 
    by returning the value of a variable instead of just an assert statement


Files added for various repositories:

Repository 1
realms-contracts
├── contracts
│   ├── settling_game
│   │   ├── interfaces
│   │   │   └── IMonsters.cairo   (interface contract to Monsters_ERC721_Mintable.cairo)
│   │   ├── modules
│   │   |   ├── monsterrampage
│   │   │   |   └── constants.cairo         (constants used in Monster Rampage module)
│   │   │   |   └── library.cairo           (library which contains the logic in Monster Rampage module)
│   │   │   |   └── MonsterRampage.cairo    (contract for Monster Rampage module)
│   │   ├── tokens
│   │   │   └── Monsters_ERC721_Mintable.cairo  (contract which stores the game state for our Monsters statistics)
├── tests
│   ├── protostar
│   │   ├── settling_game
│   │   |   ├── monsterrampage
│   │   │   |   └── test_monster_rampage.cairo  (test file used in Monster Rampage module)
└── Monsters-README.txt                 (readme file detailing work done for this hackathon)
└── Monsters-Contract-Interaction.pdf   (diagram showing the interaction between the various contracts)

Repository 2
realms-react
├── atlas
│   ├── src
│   │   ├── components
│   │   |   ├── cards
│   │   |   |   ├── monsters
│   │   │   |   |   └── MonsterCard.tsx   (monster details showing its statistics)
│   │   |   ├── filters
│   │   │   |   └── MonstersFilter.tsx
│   │   |   ├── panels
│   │   |   |   ├── Monsters
│   │   |   |   |   ├── details
│   │   │   |   |   |   └── index.tsx
│   │   │   |   |   |   └── Overview.tsx
│   │   │   |   └── MonstersPanel.tsx
│   │   |   ├── tables
│   │   │   |   └── MonsterOverviews.tsx
│   │   ├── constants
│   │   |   └── monster.ts
│   │   ├── context
│   │   |   └── MonsterContext.tsx
│   │   ├── graphql
│   │   |   ├── Monster
│   │   |   |    └── GetMonster.graphql
│   │   |   |    └── GetMonsters.graphql
│   │   |   |    └── Monster.fragment.graphql
│   │   ├── hooks
│   │   |   ├── settling
│   │   |   |    └── useMonsterRampage.tsx
│   │   |   |    └── useMonsters.tsx
│   │   ├── pages
│   │   |   ├── monster
│   │   |   |    └── index.tsx
│   │   ├── shared
│   │   |   ├── Getters
│   │   |   |    └── Monster.tsx

Repository 3
starknet-indexer
├── app
│   ├── entities
│   │   ├── settling
│   │   │   └── Monsters.ts   (monster model)
│   ├── indexer
│   │   ├── settling
│   │   │   └── MonsterIndexer.ts   (listener for all monster events and update graphql database)
│   ├── resolver
│   │   ├── settling
│   │   │   └── MonsterResolver.ts  (populate the data for fields in the schema)
│   │   ├── types
│   │   |   ├── settling
│   │   │   |   └── MonstersFilterInput.ts
│   │   │   |   └── MonsterInputs.ts
│   │   │   |   └── MonsterOrderByInput.ts


Additional features which can be implemented:
1. Monsters have the ability to regenerate HP over time
2. Monsters able to move to adjacent realms to attack
3. Instead of user-controlled Monsters, we can introduce auto minting of Monsters and Monsters roam across the realms randomly based on radius to rampage resources
4. Monsters can be summoned (using VRGDA) and the monster is spawned only on opposing Orders to raid their resources
5. World Boss can be resurrected from the depths of Hell
    5.1 Armies and Adventurers band together to fight the World Boss regardless of which Order they belong to.
    5.2 Slayers of the World Boss will be bestowed an Ancient Relic.


Any questions please contact Aralekor#0010 or velarXneo#8711 in Discord.

Thank you.
