# Fixed-Length Arrays T[N] {.code}
Fixed-length arrays represent a single resource which stores `N` elements of type `T`. 


## Functions

### self.length : [int](./int.md) {.code}
Returns the length of the array. 

Example: 
```bismuth 
int[5] a := ....; 
int a_len := a.length; // 5
```

## Operators

### self[[int](./int.md)] : (T + [Unit](./Unit.md)) {.code}
Looks up a value in the vector. If it is within bonds, the value of type T stored at the index is returned. If not, Unit is returned. 

### self[[int](./int.md)] := T {.code}
Attempts to assign T to the value at the specified index. 


## Specifications 
* Size: N * Sizeof T
* Default Location: Stack 
* Default Modifiers: Non-linear 



