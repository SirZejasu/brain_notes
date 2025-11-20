---
tags: ""
---
# [AssetDatabase](https://docs.unity3d.com/ScriptReference/AssetDatabase.html).FindAssets
## Declaration

public static string[] FindAssets(string filter);

## Declaration

public static string[] FindAssets(string filter, string[] searchInFolders);

### Parameters

| Parameter       | Description                                                                                                                                                                           |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| filter          | The filter string can contain search data. See below for details about this string.                                                                                                   |
| searchInFolders | The folders to perform the search in. Unity searches within this folder and any child folders. If unspecified, Unity searches in the `Assets` and `Packages` folders of your project. |

### Returns

**string[]** An array containing the GUIDs of any matching assets in string format. If no matching assets were found, returns empty array.

### Description

Search the asset database using the search filter string.

FindAssets allows you to search for Assets. The `string` argument can provide names, labels or types (classnames). The filter string can include:  
  
**Name**: Filter assets by their filename (without extension). Words separated by a space are treated as separate name searches. For example, `"test asset"`, is for two name searches, one looking for a match with `test` and the other with `asset`. You can also perform partial searches. For example, you can match `MyAwesomeTexture` by searching for `awesome`.  
  
**Labels (l:)**: Assets can have labels attached to them. Use the keyword `'l:'` before each label to search for assets by their labels.  
  
**Types (t:)**: Use the keyword `'t:'` to find assets by their type. If more than one type is included in the filter `string` then assets that match one class will be returned. Types can either be built-in types such as `Texture2D` or user created script classes. User created classes are assets created from a ScriptableObject class in the project. If all assets are wanted use `Object` as the type because all assets derive from Object. Specifying one or more folders using the `searchInFolders` argument limits the searching to these folders and their child folders. This is faster than searching all assets in all folders.  
  
**AssetBundles (b:)**: Use the keyword `'b:'` to find assets which are part of an AssetBundle.  
  
**Area (a:)** : Find assets in a specific **area** of a project. Valid values are `"all"`, `"assets"` and `"packages"`. Use this to make your query more specific using the `'a:'` keyword followed by the area name to speed up searching.  
  
**Globbing (glob:)**: Use globbing to match specific rules. The keyword `glob:` is followed by the query. For example, `glob:Editor` will find all Editor folders in a project, `glob:(Editor|Resources)` will find all Editor and Resources folders in a project, `glob:Editor/*` will return all Assets inside Editor folders in a project, while `glob:Editor/**` will return all Assets within Editor folders recursively.  
  
**Note:**  
Searching is case insensitive.  
  
Use [AssetDatabase.GUIDToAssetPath](https://docs.unity3d.com/ScriptReference/AssetDatabase.GUIDToAssetPath.html) to get asset paths and [AssetDatabase.LoadAssetAtPath](https://docs.unity3d.com/ScriptReference/AssetDatabase.LoadAssetAtPath.html) to load an asset.

```c#
using UnityEngine;
using UnityEditor;

public class Example
{
    [MenuItem("Example/FindAssets Example")]
    static void ExampleScript()
    {
        // Find all assets labelled with 'architecture' :
        string[] guids1 = AssetDatabase.FindAssets("l:architecture", null);

        foreach (string guid1 in guids1)
        {
            Debug.Log(AssetDatabase.GUIDToAssetPath(guid1));
        }

        // Find all Texture2Ds that have 'co' in their filename, that are labelled with 'architecture' and are placed in 'MyAwesomeProps' folder
        string[] guids2 = AssetDatabase.FindAssets("co l:architecture t:texture2D", new[] {"Assets/MyAwesomeProps"});

        foreach (string guid2 in guids2)
        {
            Debug.Log(AssetDatabase.GUIDToAssetPath(guid2));
        }
    }
}
```