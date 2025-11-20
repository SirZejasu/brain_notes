---
source01: https://discussions.unity.com/t/how-to-tie-scriptable-objects-file-name-with-a-name-field-in-a-scriptable-object/190039
---
```
string assetPath = AssetDatabase.GetAssetPath(item.GetInstanceID());
                        item.ItemIdentifiers.ItemName = Path.GetFileNameWithoutExtension(assetPath);
```
