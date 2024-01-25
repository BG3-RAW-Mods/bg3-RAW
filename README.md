# BG3 RAW addon

This mod is an addon to [Zerd's Rules As Written](https://github.com/ZerdBG3/RAW) for Baldur's Gate 3.
Every changes will be proposed as a pull request to Zerd's repository. If accepted, they will be removed from this addon.

It follows the same principles than Zerd's RAW and tries to be as close as possible to D&D 5th edition ruleset.
While it can be used without the former, it is highly encouraged to use it.

## Requirement

- [Norbyte's Baldur's Gate 3 Script Extender](https://www.nexusmods.com/baldursgate3/mods/2172)
- [Community Library](https://www.nexusmods.com/baldursgate3/mods/1333)
- [Compatibility Framework](https://www.nexusmods.com/baldursgate3/mods/1933)

I'm doing my best to improve compatibility with other mods. CF is a fantastic way to prevent mod conflicts.

## Features

### Racials

I have restored races abilities and traits, pretty much like it was before release. This is now as close as possible to PHB.

#### Half-Elf

Half-Elf subraces are a shortcut to PHB, which results in missing choices. I have added Half-Elf Versatility with subraces. Not the best implementation, but the most user-friendly considering the limitations of character creation:
- Skill Versatility (General). You gain proficiency in two skills of your choice.
- Elf Weapon Training (High or Wood Elf Heritage). You have proficiency with the longsword, shortsword, shortbow, and longbow.
- Cantrip (High Elf Heritage). You know one cantrip of your choice from the wizard spell list. Intelligence is your spellcasting ability for it.
- Fleet of Foot (Wood Elf Heritage). Your base walking speed increases to 35 feet (10.5m).
- Drow Magic (Dark Elf Heritage). You know the Dancing Lights cantrip. When you reach 3rd level, you can cast Faerie Fire once, and it recharges after a long rest. When you reach 5th level, you can cast  Darkness once, and it recharges after a long rest. Charisma is your spellcasting ability for these spells.

#### Variant Human

Variant Human has been added as human's subrace. Most feats are available. For half-feat, I have chosen the most relevant ability score increase. It may not fit everyone and it is possible to create 2 versions. For example, Athlete Strength, Athlete Dexterity.

Please note that these requirements are not listed in description. I might add them in a future release:

| Feat                      | Requirement                       |
| ------------------------- | --------------------------------- |
| Defensive Duelist         | Dexterity: 13+                    |
| Moderately Armored        | Light Armor proficiency           |
| Heavily Armored           | Medium Armor proficiency          |
| Heavy Armor Master        | Heavy Armor proficiency           |
| Medium Armor Master       | Medium Armor proficiency          |

Human racials have been transfered to standard human's subrace. However, this created an issue for all other humans that would loose their racials.
As Human only get +1 to all ability scores, I have put this in Human race. Then, Variant Human get -1 to all ability scores. I think it is easier this way, instead of changing every race references by standard human subrace.

### Jump

I didn't implement Long and High Jump because it would make jumps too complex and high jump would probably be useless in BG3. However, this is still something I might consider in a future release. With High Jump "neutralized", it would make Fly and Teleport more powerful. They were already powerful, but Jump was so powerful that it could almost do the same thing for free.

For now, I have updated Jump to match Long Jump Range. On top of that, Jump now cost movement instead of bonus action. 

As a result, Jump range is roughly divided by 2, there are many jumps you won't make without a ritual spell like Enhanced Leap.
Even high strength characters won't fly over the battlefield. While Enhanced Leap would allow them to jump about 20 meters, they are still limited by their movement speed. 9 meters by default for most, 18 with dash. It opens a possibility for a 18m jump using dash and enhanced leap.

Please note there are several jumps that now impossible without Enhanced Leap.

Remarkable Athlete has been toned down from 3 to 1.5m, because it is supposely 1 feet per strength modifier, which is more likely to be 4 or 5 feet at this point. Of course, if you play a dexterity champion, this makes no sense.

Athlete feat has been changed. In RAW, you can make a long jump after moving 1.5m instead of 3. Since it is not implemented, it increases jump range by 1.5m.

Barbarian Tiger Jump has been changed from 4.5 to 3m.

### Spell changes

- Mage Hand, 10 turns duration
- Knowledge of the Ages, proficiency in one skill for 100 turns
- Astral Knowledge, proficiency in one skill until long rest

Concentration has been added to these spells:
- Flame Blade
- Conjure Minor Elemental
- Conjure Woodland Being
- Conjure Elemental

### Class adjustements

#### Sorcerer

- Sorcerers gain two Metamagic options of your choice at level 3. You gain another one at 10th.
- Tempestuous Magic, fly range reduced to 3m
- Dragon Wings, distance is based on movement speed, without armor, and at level 14 (so removed from game)
- Draconic Blood, ancestry's spell removed
- Storm Sorcerey, level 6 free spells removed

#### Warlock

- Repelling Blast, distance is 3m, not 4.5m

### Cleric

- Warding Flare uses wisdom modifier (instead of unlimited uses)

### Bard

- Bardic Inspiration uses charisma modifier (instead of a set number)

### Weapon Range

I have made changes to make it closer to RAW:

| Weapon         | WR BG3 | DR BG3 | WR RAW | DR RAW | WR Diff | WR Mod | DR Mod |
| -------------- | ------ | ------ | ------ | ------ | ------- | ------ | ------ |
| Throw weapon   | 18     |        | 6      |        |  12     | 6      |        |
| Dart           | 12     | 30     | 6      | 18     |   6     | 6      | 18     |
| Sling          | 14     | 30     | 9      | 36     |   5     | 9      | 30     |
| Hand Crossbow  | 14     | 30     | 9      | 36     |   5     | 9      | 30     |
| Light Crossbow | 18     | 30     | 24     | 97     |  -6     | 18     | 30     |
| ShortBow       | 18     | 30     | 24     | 97     |  -6     | 18     | 30     |
| Heavy Crossbow | 22     | 30     | 30     | 121    |  -8     | 22     | 30     |
| LongBow        | 25     | 30     | 45     | 182    | -20     | 30     | 30     |

WR: Weapon Range, DR: Damage Range (max range with disadvantage)
Last columns show chosen values.

Maximum range will be kept at 30 to prevent AI issue.

### Item weights

I have adjusted most items to RAW valuess:

| Item             | Game | RAW (kg) | Diff |
| ---------------- | ---- | -------- | ---- |
| Plate            | 20   | 29,48    | 9,48 |
| Scale mail       | 12   | 20,41    | 8,41 |
| Splint           | 19   | 27,21    | 8,21 |
| Chain mail       | 18   | 24,94    | 6,94 |
| Half plate       | 12   | 18,14    | 6,14 |
| Silver metal bar | 1    | 4,54     | 3,54 |
| Ring mail        | 17   | 18,14    | 1,14 |
| Bronze metal bar | 1    | 1,81     | 0,81 |
| Shield           | 2    | 2,72     | 0,72 |
| Crossbow hand    | 0,9  | 1,36     | 0,46 |
| Thieves Tool     | 0,2  | 0,45     | 0,25 |
| Trap Disarm      | 0,2  | 0,45     | 0,25 |
| Arrow            | 0,1  | 0,23     | 0,13 |
| Grenade          | 0,1  | 0,23     | 0,13 |
| Potion           | 0,1  | 0,23     | 0,13 |

Additionally, Flame Blade and Pact weapons will their corresponding item weight.

### Carry weight

BG3 is very far from RAW and I think it was for QoL reason. Still, I was choked to see how easy it is to wear heavy armor, even for a 8 strength mage with one dip into any heavy armor class.
Your party can loot a whole dungeon without any carrying issue so carry weight almost become a non issue.

Your carrying capacity is your Strength score multiplied by 6.8 (RAW). This is in kg (metric used by default in game), PHB says 15 with imperial measure. System measurement Metric (in BG3 option) is the most accurate because Imperial conversion rate is wrong. Fortunately, game's data use metric.

Compared to vanilla, this is roughly 50% less in carry weight.

BG3 partially use Variant: Encumbrance optional rule.

Encumbered status have been updated to match RAW:
| Status              | BG3                                                            | RAW                                        |
| ------------------- | -------------------------------------------------------------- | ------------------------------------------ |
| Lightly encumbered  | Movement cost 50% more, Jumping distance halve, Walk           | Movement distance reduced by 3m            |
| Heavily encumbered* | Movement cost 200% more, Jumping distance reduced to 0, Stroll | Movement distance reduced by 6m, Walk**    |

* already applied by BG3: disadvantage on ability checks, attack rolls, and saving throws that use Strength, Dexterity, or Constitution.

** RAW doesn't specify that you can't run while beeing heavily encumbered, but I think it should be obvious.

### Encumbrance

There are 3 options here, numbers are relative to carry weight:
- Standard is mostly RAW, but since BG3 also partly use variant encumbrance, I have set the same ratio
- Variant is Variant: Encumbrance rule. This is very difficult to play, I have tried it !
- Mix is an alliegiated Variant rule with added Heavy Armor requirement. I think it is the best compromise.

| Encumbrance | Lightly encumbered | Heavily encumbered | Comment                                                                          |
| ----------- | ------------------ | ------------------ | -------------------------------------------------------------------------------- |
| Standard    | 81%                | 93%                | Strength requirement for Heavy Armor, encumbrance ratio are identical to vanilla |
| Variant     | 33%                | 66%                | No strength requirement for heavy armor but these ratio are really hard          |
| Mix         | 51%                | 81%                | Strength requirement for Heavy Armor, adjusted ratio to make it playable         |

### Feats

- Actor gives advantage instead of proficiency with expertise

### Miscellaneous changes

- Potions now use an action

### Monsters

Restored PHB abilities and stats. I also made my own version of weak monsters in Nautiloid, which will prove to be much more challenging. As an example, Imp regained most of their dexterity and all resistances. So they are harder to hit, more difficult to kill and damage you a lot more:
- Imp
- Intellect Devourer
- Hell Boar

### Custom Ruleset defaults

RAW changes:
- Hide NPC health
- Hide failed perception rolls
- Hide passive rolls in dialogues
- Hide difficulty class during rolls

Other changes:
- Enemy aggression: Tactician
- Camp cost multiplier: 1.5
- Trader price multiplier: 3

## Future plans

### High level class abilities

Many high level class abilities were introduced in the game, either in their true form, either in a toned down form.
Following RAW, I have removed all of them. But it could be an optional rule. 
Also, it seem to be a random pick, maybe based on class performance. Draconic Sorcerer got his Wings at level 11 instead of 14, but Evocation Wizard didn't get Overchannel which is also a level 14 ability.

### Monk

Damage progression table:
| Level | BG3 Ki | RAW Ki | BG3 DMG | RAW DMG |
| ----- | ------ | ------ | ------- | ------- |
|  1    |  2     |  0     | 1d4     | 1d4     |
|  2    |  3     |  2     | 1d4     | 1d4     |
|  3    |  4     |  3     | 1d6     | 1d4     |
|  4    |  5     |  4     | 1d6     | 1d4     |
|  5    |  6     |  5     | 1d6     | 1d6     |
|  6    |  7     |  6     | 1d6     | 1d6     |
|  7    |  8     |  7     | 1d6     | 1d6     |
|  8    |  9     |  8     | 1d6     | 1d6     |
|  9    | 10     |  9     | 1d8     | 1d6     |
| 10    | 11     | 10     | 1d8     | 1d6     |
| 11    | 12     | 11     | 1d8     | 1d8     |
| 12    | 13     | 12     | 1d8     | 1d8     |

- Flurry of Blows: requires an attack first as Martial Arts, unlock at level 2
- Step of the Wind: you can spend 1 ki point to take the Disengage or Dash action as a bonus action on your turn, **and your jump distance is doubled for the turn**.
- Patient Defense: The status is removed if you're either incapacitated or **immobilized**. BG3 doesn't have a Dodge action but it does have a Dodge status which is missing immobilized removal condition.
- Deflect Missiles: If you reduce the damage to 0, you can catch the missile if it is small enough for you to hold in one hand and you have at least one hand free. If you catch a missile in this way, you can spend 1 ki point to make a ranged attack with a range of 6/18m. **BG3 uses 18m radius, so no disadvantage at 7-18 radius**
- Slow Fall: you can use your reaction when you fall to reduce any falling damage you take by an amount equal to five times your monk level. **BG3 uses a flat 50% reduction, it is fixed by 5e Monk 5e Adjustments**
- Stillness of Mind: you can use your action to end one effect on yourself that is causing you to be charmed or frightened. **BG3 removes it with a reaction**
- Unarmored Movement: you gain the ability to move along vertical surfaces and across liquids on your turn without falling during the move. **BG3 hasn't implemented vertical surfaces, and gives immunity to difficult terrain. On top of that, it upgrades jump distance by 6m**. It should allow Monk to climb wall or cliffs. It should not give immunity to all difficult terrains, only deep water, grease, and maybe ice.

Open Hand:
- Flurry of Blows Push: push distance is 4.5m, **has been rounding up at 5m in BG3**.
- Wholeness of Body: As an action, you can regain hit points equal to three times your monk level. You must finish a long rest before you can use this feature again. **BG3 also restores Ki Points**
- Removes Manifestation of Body, Manifestation of Mind, and Manifestation of Soul that don't exist in PHB.
- Tranquility: you gain the effect of a Sanctuary spell that lasts until the start of your next long rest. **BG3 only lasts 100 turns**
- Ki Resonation (level 9) is a weaker version of Quivering Palm (level 17)
    Ki Blast: 1 Ki to apply Resonation status with an unarmed attack. Blast: 3D6 force damage AOE 5m (DEX saves for none)
    Quivering Palm: 3 Ki to apply vibrations with an unarmed attack. Blast: kill target (CON saves for 10d10 necrotic damage)

Shadow:
- Removes Shadow Arts: Hide, doesn't exist in PHB
- Cloak of Shadows is granted at level 11, not 5
- Remove Shadow Strike, doesn't exist in PHB

## Credits

- BG3 Discord Modding community (lostsoul, Velnir, Athera, ghostboats, hinikuya)
- Zerd, for RAW which gave me inspiration, and its config system.
- Community Library and Compatibility Framework