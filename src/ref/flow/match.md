# Pattern Matching {.code}
Pattern matching can be performed on a [sum type](../types/enum.md) in order to access the value that it stores. Pattern matching must be exhaustive: when pattern matching on a sum, there must be a branch defined for each possible case in the sum. 


## Syntax 

Pattern matching follows the following syntax: 

```bismuth
match e : (T_1 + ... + T_n) 
  | T_1 <name> => ...
  | ...
  | T_n <name> => ...

```

For example, given the sum type `(int + boolean)`, one could pattern match on it as follows:
```bismuth 
(int + boolean) x := ...; 
match x 
  | int i => ... // if x stores an integer, that value can be accessed as i.  
  | boolean b => ...  // if x stores a boolean, that value can be accessed as b.  
```
