# titancraft-enchantments

A repository for documenting the behaviours of Titancraft's custom enchantments

Currently this is a work-in-progress, currently documenting these Tool enchantments that change block drops:

- Extract
- Hydrate
- Forge
- Green Thumb
- Bleach
- Pulverize
- Chisel

Philia and Oxidise are planned to be added.
I do not currently have plans for enchantment types (armour, fishing rods, etc.), but may do so in future.

The tool enchantments are documented in this format:

```json
{
    "blocks": {
        "block_1": {
            "extract": "grass", // an item name indicates 1 of these items is dropped
            "hydrate": false, // false indicates that the enchantment has no effect, i.e. the block drops what it would've without the enchantment
            "forge": "", // "" (an empty string) indicates that this enchantment causes the block to drop *nothing*, where it would normally drop something (e.g. using the `pulverise` enchantment on a `damaged_anvil`)
            "green_thumb": {
                "quantity": 2, // a quantity indicates that more than one item is dropped
                "item": "nether_star"
            },
            "bleach": [ // an array of items indicates that a random item from the list could drop (does not guarrantee all items have an equal chance of dropping)
                "iron_nugget",
                "gold_nugget",
                "copper_nugget"
            ],
            "pulverise": {
                "quantity": [// an array of quantities indicates that a random number of items from this list could drop
                    1,
                    2,
                    3,
                    4
                ],
                "item": "iron_ingot"
            },
        },
        "block_2": {
            ["..."]
        },
    }
}
```
