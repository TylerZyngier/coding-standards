# These standards are geared towards Unity development as that is my main C# use case

## Variables

### Access Modifiers

#### Order access modifiers as seen below Use '[SerializeField] private' rather than 'public' modifier as often as possible
```C#
public static varType varName;
    
public varType varName;

[SerializeField] private varType varName

internal varType varName;
    
private varType _varName;
```

### Naming Conventions
    
#### Do not use Hungarian notation or any other type identification in identifiers

```C#
// Correct
int name;
string name;

// Avoid
int iName;
string strName;
```

#### Do not use screaming caps
*This includes 'const' and 'readonly' variables*

```C#
// Correct
public static const string StringName = "StringValue";

// Avoid
public static const string STRINGNAME = "StringValue";
```

#### Avoid using Abbreviations.

***Exceptions:** abbreviations commonly used as names, such as Id, rb, and anim*

```C#
// Correct
WeaponType weaponType;
EnemyType enemyType;

// Avoid
WeaponType wpnType;
EnemyType enmyType;

// Exceptions
ItemId itemId;
Rigidbody2D rb;
Animator anim;

// There are of course other exceptions that I can't think of right now
```

#### Do not use Underscores in identifiers. 
**Exceptions:* you can prefix private variables with an underscore.*

```C#
// Correct
public WeaponType weaponType;
public EnemyType enemyType;

// Avoid
public WeaponType weapon_Type;
public EnemyType enemy_Type;

// Exceptions
private WeaponType _weaponType;
```

#### Use predefined type names instead of system type names like Int16, Single, UInt64, etc     
```C#
// Correct
string firstName;
int lastIndex;
bool isSaved;

// Avoid
String firstName;
Int32 lastIndex;
Boolean isSaved;
```

## Namespaces

### Namespace structure
Namespaces should follow file-system structure aka. file folder names

```C#
// Example of a file at 'Enemy.cs' at 'Scripts/Entities/Enemies/' would have the namespace [RootNamespace]/Entities.Enemies
namespace Slinky.Entities.Enemies {

}
```

### Imported namespace structure
Imported namespaces should be grouped from top to bottom as follows: 'System', 'Unity', 'User Defined' namespaces.  
Groupings should be seperated by a whitespace, ordered from top to bottom shortest to longest, and grouped with other namespaces of the same root

```C#
using System;
using System.Collections;

using UnityEngine;
using UnityEngine.SceneManagement;

using GameManagement;
using LevelManagement;
using LevelLoading.Editor;
using LevelLoading.ScriptableObjects;
```

## Classes

## Methods