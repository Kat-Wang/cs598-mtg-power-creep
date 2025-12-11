# Magic: The Gathering Power Creep Analysis Data Dictionary
Many descriptions are taken from the card and set model documentation from MTGJSON and are marked accordingly. 

Card Model: https://mtgjson.com/data-models/card/card-atomic/

Set Model: https://mtgjson.com/data-models/set/


## name
- **Type:** String
- **Description (MTGJSON; Card):** The name of the card. Cards with multiple faces are given a // delimiter.

## type
- **Type:** String
- **Description (MTGJSON; Card):** Type of the card as visible, including any supertypes and subtypes and are given a - delimiter if appropriate.
- **Additional Description:** Cards can have different types (creature, land, planeswalker, etc.), each associated with different gameplay roles and mechanics.

## rarity
- **Type:** String
- **Description (MTGJSON; Card):** The card printing rarity. Rarity bonus relates to cards that have an alternate availability in booster packs, while special relates to "Timeshifted" cards.

## setName
- **Type:** String
- **Description (MTGJSON; Set):** The name of the set.

## setCode
- **Type:** String (computed)
- **Description:** Short letter code representing which set the card was released in.

## isUniversesBeyond
- **Type:** Boolean (computed)
- **Description:** Boolean flag indicating whether card belongs to a Universes Beyond set.

## releaseDate
- **Type:** Date
- **Description (MTGJSON; Set):** The original release date in ISO 8601 format for a promotional card printed outside of a cycle window, such as Secret Lair Drop promotions.

## year
- **Type:** Int (computed)
- **Description:** Release year extracted from the card's release date.

## keywords
- **Type:** String[]
- **Description (MTGJSON; Card):** A list of keywords found on the card.

## keywordCount
- **Type:** Int (computed)
- **Description:** Count of keyword abilities found on the card.

## manaValue
- **Type:** Int
- **Description (MTGJSON; Card):** The mana value of the card.
- **Additional Description:** Numeric converted mana cost (CMC) of the card, equal to the total value of all mana symbols in its cost.

## power
- **Type:** Int
- **Description (MTGJSON; Card):** The power of the card.
- **Additional Description:** The attacking value of the card.

## toughness
- **Type:** Int
- **Description (MTGJSON; Card):** The toughness of the card.
- **Additional Description:** The health point value of the card.

## coreStats
- **Type:** Int (computed)
- **Description:** Computed aggregate measure combining mana value, power, and toughness to approximate baseline card strength

## defense
- **Type:** Int
- **Description (MTGJSON; Card):** The defense of the card. Used on battle cards.
- **Additional Description:** Defense value used by Battle cards, Planeswalkers, or other designs with defensive stats.

## colors
- **Type:** String[]
- **Description (MTGJSON; Card):** A list of all the colors in manaCost and colorIndicator properties. Some cards may not have values, such as cards with "Devoid" in its text.

## isMulticolor
- **Type:** Boolean  
- **Description (MTGJSON; Card):** Boolean flag indicating whether the card has more than one color.

## text
- **Type:** String
- **Description (MTGJSON; Card):** The rules text of the card.

## commanderLegal
- **Type:** Boolean (computed)
- **Description:** Boolean indicating whether the card is legal for use in the Commander format; Calculated from thewhich was filtered from the final dataset. The Commander format is a casual playing format where players build a 100 card deck with no duplicates (except for basic land cards) centered around one Commander type card. Commander legal means the card is allowed to be played in the Commander format. There are also formats like Tournament, Standard, Pioneer, etc. 

## edhrecRank
- **Type:** Int
- **Description (MTGJSON; Card):** The card rank on EDHRec.
- **Additional Description:** Popularity ranking from EDHREC, indicating how frequently the card appears in Commander decklist.