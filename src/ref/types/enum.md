# enum {.code}
Enums (AKA. Sum Type, Tagged Union) respresent a type of data which stores a value of one of several possible types. For example, the sum type `(int + boolean)` would permit a resource with this type to store either an [`int`](./int.md) or [`boolean`](./boolean.md). 

The value of an enum can then be used via pattern matching. 


## Syntax 

Enums can either be anonymous (defined in-place) or named. Anonymous enums are defined using the syntax `(T_1 + ... + T_n)` wherein `T_1`, ..., `T_n` are the possible types that could be stored in the sum. Note, the order of the types as specified in the enum do not matter. For example, `(int + boolean)` and `(boolean + int)` are treated as the same type. 

Named enums are defined using the following syntax: 
```bismuth 
define enum <NAME> {
    T_1, 
    ..., 
    T_n
}
```

Unlike anonymous enums which are equivalent based on the types they can contain, named enums are seen as equal based on instance of the defined type. For example: 

```bismuth
define enum Foo { int, boolean }

define enum Bar { int, boolean } 

Foo f := 5; 
Bar b := 5; 

if(f == b) {} // Semantic Error: Foo and Bar are different types

Foo f2 := 5; 

if (f == f2) {} // Condition will evaluate to true 
```


## Specifications 
* Size: 32-bit tag (to track type of stored value) + sizeof largest stored type
* Default Location: Stack 
* Default Modifiers: Non-linear 



