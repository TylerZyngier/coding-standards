### Class variable naming conventions
### Use [Serialize Field] on same line preceding variable
    const varType VarName;
    public varType varName;
    private varType _varName;
    internal varType varName;
    
    [Seralize Field] private varType varName;

### Seperate class variable groupings by whitespace
    const varType VarName;
    const varType VarName;
    const varType VarName;
    
    public varType varName;
    public varType varName;
    
    private varType _varName;
    
    internal varType varName;
    internal varType varName;
    internal varType varName;
    
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
### Use same line brackets
    namespace SlinkyUtils.Player.Combat {
        public class ClassName {
            public void MethodName() {
                //...
            }
            public void MethodName() {
                //...
            }
        }
    }

### Use camelCasing for local variables and method arguments
### Use var keyword over specific variable type in local variables
    public void MethodName(VarType varName) {
        var itemCount = varName.Items.Count;
    }
