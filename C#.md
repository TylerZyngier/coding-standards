# These standards are geared towards Unity development as that is my main C# use case

## Class variables
### Seperate class variable groupings by whitespace
### Order access modifiers as seen below
### Use '[SerializeField] private' rather than 'public' as often as possible
    public static varType varName;
    
    public varType varName;

    [SerializeField] private varType varName

    internal varType varName;
    
    private varType _varName;

### Seperate 
    
### Do not use Hungarian notation or any other type identification in identifiers
    // Correct
    int name;
    string name;

    // Avoid
    int iName;
    string strName;
  
### Do not use Screaming Caps for constants or readonly variables
    // Correct
    public static const string StringName = "StringValue";

    // Avoid
    public static const string STRINGNAME = "StringValue";
    
### Avoid using Abbreviations. Exceptions: abbreviations commonly used as names, such as Id, rb, and anim
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
    {there are of course other exceptions that I can't think of right now}

### Do not use Underscores in identifiers. Exception: you can prefix private variables with an underscore.
    // Correct
    public WeaponType weaponType;
    public EnemyType enemyType;

    // Avoid
    public WeaponType weapon_Type;
    public EnemyType enemy_Type;

    // Exception
    private WeaponType _weaponType;

### Use predefined type names instead of system type names like Int16, Single, UInt64, etc     
    // Correct
    string firstName;
    int lastIndex;
    bool isSaved;

    // Avoid
    String firstName;
    Int32 lastIndex;
    Boolean isSaved;

### Use PascalCasing for class names, method names and namespaces
### Use next line brackets
    namespace Slinky.Player.Combat 
    {
        public class ClassName 
        {
            public void MethodName() 
            {
                //...
            }
        }
    }


### Local Variables
### Use camelCase for local variables and method arguments
### Use specific variable keywords (ie. 'float', 'bool', 'int', 'GameObject', etc.) rather than 'var' when using local variables
    public void MethodName(VarType varName) {
        var itemCount = varName.Items.Count;
    }


### Use root namespace for all scripts
    namespace Slinky.Player.Combat 
    {
        public class ClassName 
        {
            //...
        }
    }

    namespace Slinky.LevelManagement 
    {
        public class ClassName 
        {
            //...
        }
    }