# Snippets


## U10


#### Spawning a prefab asynchronously from an asset bundle


```csharp
Catalog.InstantiateAsync<GameObject>("myPrefabGameObject", myGameObject => {
  myGameObject.transform.position = whatever;
}, "SpawningMyGameObject");
{{ "{% endhighlight " }}%}  
```

#### Is Player holding an Item with Telekinesis
```csharp
/// <summary>
/// Returns true if the player is TK holding the item
/// </summary>
/// <param name="item"></param>
/// <returns></returns>
public static bool IsPlayerTkHolding( Item item ) {
    if ( item != null ) {
        foreach ( SpellCaster spellCaster in item.tkHandlers ) {
            if ( spellCaster.ragdollHand.creature.isPlayer ) {
                return true;
            }
        }
    }
    return false;
}
```

#### Disable culling for an Item (uses reflection)
```csharp
item.Set("cullingDetectionEnabled", false);
 
public static void Set<T>( this object source, string fieldName, T val ) {
    source.GetType()
        .GetField(fieldName, BindingFlags.NonPublic | BindingFlags.Instance)
        .SetValue(source, val);
}
```


#### Basic U10 LevelModule json
```json
{
  "$type": "ThunderRoad.LevelData, ThunderRoad",
  "id": "Master",
  "version": 3,
  "modes": [
    {
      "name": "Default",
      "modules": [
        {
          "$type": "Namespace.Classname, DLL-Name"
        }
      ]
    }
  ]
}
```

