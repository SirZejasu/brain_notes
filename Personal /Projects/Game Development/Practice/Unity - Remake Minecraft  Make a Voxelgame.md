---
aliases:
  - Remake Minecraft / Make a Voxelgame
---
# Tutorial
https://www.youtube.com/watch?v=h66IN1Pndd0&list=PLVsTSlfj0qsWEJ-5eMtXsYp03Y9yF1dEn

# Tasks
- [x] Create methods to generate and store Cube-Metadata 
- [ ] Adjust World Script to generate Chunks
- [ ] Adjust Player Settings
- [ ] Do the Tutorial mentioned above
- [ ] Experiment with Procedural Generation , see [[Procedural Generation#Minecraft - Using simple Math]] for help and inspiration
- [ ] Interaction / Fight: Spawn Actors, Initiate Fighting scene

# How to store data?
Unreal Engine has Data Tables. What ways are there to store data in Unity?
## C (Data) Classes
Storing raw data in Classes that we can access.
```c#
public class DataOnlyClass {
public string itemName = "Powerful_Item";
public int powerLevel = 22
// ...

}
```

```c#
// Lets you create Attr
[CreateAssetMenu(fileName = "BiomeAttributes", menuName = "MinecraftTutorial/Biome Attribute")]  
public class BiomeAttributes : ScriptableObject {  
  
    public string biomeName;  
  
    public int solidGroundHeight;  
    public int terrainHeight;  
    public float terrainScale;  
  
    public Lode[] lodes;  
  
}

// ...
```
![[Pasted image 20251019195622.png|100 px]]

- JSON
- XML

JSON and XML are good for compatibility issues.
I am going to use a C# Script with an array of objects.

For Minecraft Blocks I will try to visually categorize them so I can easily add them through the inspector.