# Snippets


## U10


#### Spawning a prefab asynchronously from an asset bundle


```csharp
Catalog.InstantiateAsync<GameObject>("myPrefabGameObject", myGameObject => {
  myGameObject.transform.position = whatever;
}, "SpawningMyGameObject");
{{ "{% endhighlight " }}%}  
```