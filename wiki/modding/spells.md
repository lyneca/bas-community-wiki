# Creating Spells

## JSON Files

### Spell

This JSON defines your spell and its behaviour. It links to your `SpellCastCharge`, and contains all of the parameters - both custom and default - of your spell.

```json
{
  "$type": "MyNamespace.MySpellClass, MyDLLName",
}
```

### Spell Item

This JSON is required to create an entry in the player's inventory for the spell.

```json
```

### Player Default Container

This JSON file tells the game that the player should, by default, spawn with the spell in their inventory.
Without this file, your spell won't appear in the spell wheel.

```json
```

## Effect JSON files

If you want your spell to have any kind of visual or audible effects, you'll probably want to create a B&S Effect.
Effects are defined by JSON files and can be spawned and played. Creating a JSON for an effect is a bit of work, but less than you might think - and doing it this way gives you access to heaps of nice tools and functionalities that B&S provides:

- Effects are pooled, meaning they are pre-spawned instead of spawned when needed - this is a big performance bump
- You can use a set of functions to control parameters of the effect, like gradients, source, target, intensity, speed etc.
- You can set parts of your effect to play at the start or end of your effect, or to play continuously while the effect is active.
- You can fine-tune effect parameters via defining curves in JSON.

```json
{
  "$type: ThunderRoad.EffectData, ThunderRoad",
  "id": "MyEffectName",
  "modules": [
    // add your effect modules here
  ]
}
```

## Coding your Spell
