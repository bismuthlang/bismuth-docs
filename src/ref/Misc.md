# Misc

This page outlines some of the various statements, expressions, and keywords that have not yet found their way into the other documentation pages. 


## \<type\> (\<identifier 1\>, ..., \<identifier n\> := e)* {.code}
Used to define a variable. For example: 
```bismuth 
int a := 5; 
int b, c := 6; // Both b and c equal 6 (Note: the expression for variables to be assigned to may be re-evalued for each identifier they are bound to. 
int d = 7, e = 8;
```

## var {.code}

The keyword `var` can be used in place of a type name in a variable declaration. Doing so will cause the type to be inferred. 

Example: 
```bismuth 
var a := 5; // a will be inferred as having type int 
var b := false; // b will be inferred as having type bool 
var c := exec Program<P>; // c will be inferred as having type Channel<dual P> 
```

## asChannel(e : T[]) -> Channel<!+T> {.code .mb-0}
## asChannel(e : T[N}) -> Channel<!+T> {.code .m-0}
## asChannel(e : T) -> Channel<!+T> {.code .m-0}
* Since: `1.3.4` 
Given an expression `e`, `asChannel` will evaluate it and return the reuslts as a channel that can be iterated through. 

Example: 
```bismuth
int [5] a := [1, 2, 3, 4, 5];

var c2 := asChannel(a); 

# Will result in us printing "1, 2, 3, 4, 5"
accept(c2){
	int val := c2.recv();
	printf("%u ", val);
}
printf("\n");
```

## copy(e : T) -> T {.code} 
Given any non-linear expression `e`, `copy` will return a deep copy of the expression. Note: parenthesis around the expression to be copied are optional. 

Example: 
```bismuth 
var a := copy(5); // a will be equal to 5
var b := copy false; // b will be false

var ptr := Box<int>::init(a); 

var c := copy ptr; // c will be a deep copy of ptr
```

## extern \<Identifier\> (T_1, ... T_n) -> T_r {.code}

Allows one to import a function from another file/the C standard library whose name is `<Identifier>`, has the return type `T_r`, and has the arguments `T_1, ..., T_n`. This function is likely to be deprecated in favor of an easier system for importing resources—including other types (e.g., programs, structs, enums, etc).  

## import \<Identifier\> (:: \<Identifier\>)+ (as \<Identifier\>)? {.code}
Imports the specified definition from another file into the current file. By default, this allows one to refer to the definition via its original identifier; however, an optional identifier can be provided to rename it.

Example: 
```bismuth
# Optional can now be used within the current scope; without
# this line, we would have to refer to it asbsl::lib::Optional::Optional
import bsl::lib::Optional::Optional; 

# Allows one to use llMap to refer to bsl::lib::Lists::map
import bsl::lib::Lists::map as llMap;
```


