* enum are constants with fields and methods 
* used in conditions and switch cases
* all fields are public static final by default
* enum can implement interfaces
* enum implicitly extend java.lang.Enum ( so default it has methods - values(),valueOf(Str),name(),ordinal(),compareTo(Enum)
* 

Enum with Fields

* Each enumeration constant has its own field. ie. each enumeration constant is an object of its enumeration type
* 

public enum Site {
JAVA(101),
DOTNET(102),
PHP(103);

private int numberOfTutorials;
}


With Methods :
usefulness can be understood with above implicit methods like values().


USE CASES:(When to use)

