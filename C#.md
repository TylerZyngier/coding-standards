## These standards are geared towards Unity development
*//... is just used here as filler for actual code*

# Variables

### Access Modifiers
Access modifiers should be ordered as seen below  
Use the '**[SerializeField] private**' modifier rather than the '**public**' modifier as often as possible

```C#
public static varType varName;
    
public varType varName;

[SerializeField] private varType varName

internal varType varName;
    
private varType _varName;
```

### Naming Conventions
Do not use Hungarian notation or any other type identification in identifiers

```C#
// Correct
int name;
string name;

// Avoid
int iName;
string strName;
```

Do not use screaming caps  
*This includes 'const' and 'readonly' variables*

```C#
// Correct
public static const string StringName = "StringValue";

// Avoid
public static const string STRINGNAME = "StringValue";
```

Avoid using Abbreviations  
***Exceptions:** abbreviations commonly used as names, such as Id, rb, and anim*

```C#
// Correct
WeaponType weaponType;
EnemyType enemyType;

// Avoid
WeaponType wpnType;
EnemyType enmyType;

// Exceptions
Rigidbody2D rb;
Animator anim;
// More general exceptions include: id, sfx, ui, max, min
```

Do not use Underscores in identifiers. 
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

# Namespaces

### Namespace structure
Namespaces should follow file-system structure aka. file folder names

```C#
// Example of a file at 'Enemy.cs' at 'Scripts/Entities/Enemies/' would have the namespace [RootNamespace]/Entities.Enemies
namespace Slinky.Entities.Enemies 
{
    //...
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

# Classes

### Class sectioning
Classes are sectioned off into 2 major sections Variables and Methods   
The 'Methods' section is divided into 2 sub-categories, Unity Methods and Custom Methods  
Sections are defined by commenting '/// <Description> *Section Name* </Description>'

```C#
/// <Description> Variables </Description>

public static LevelLoader instance;

public static Action OnLoadingStarted;
public static Action OnLoadingFinished;

private bool loadingLevel;

/// <Description> Methods </Description>
/// <Description> Unity Methods </Description>

private void Awake()
{
    //...
}

private void Update()
{
    //...
}

/// <Description> Custom Methods </Description>

public void LoadNextLevel(bool loadingScreen = true)
{
    int nextSceneIndex = Utils.GlobalFunctions.GetActiveSceneIndex() + 1;

    LoadLevel(nextSceneIndex, loadingScreen);
}
```

# Methods

### Single Line Methods
Methods with only one line of code should be written two lines and use the shorthand lambda expression "=>"  
This includes code with a return type such as bool, int, float, etc.

```C#
private void MethodName()
    => //...

private bool MethodName()
    => //...
```

# General Code

### Return
Statements that just return something should all be on the same line

```C#
// Do this
if (gameObject == null) return;

public Vector3 MethodName(GameObject originObject, Target targetObject) 
{
    if (originObject == null) return Vector3.zero;

    return originObject.transform.position - targetObject.transform.position;
}


// Avoid this
if (gameObject == null) 
    return;

if (gameObject == null) 
{
    return;
}

public Vector3 MethodName(GameObject originObject, Target targetObject) 
{
    if (originObject == null) 
    {
        return Vector3.zero;
    }

    return originObject.transform.position - targetObject.transform.position;
}
```

Statements that contain 