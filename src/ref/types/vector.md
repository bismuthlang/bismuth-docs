# Dynamic-Length Arrays (Vectors) T[] {.code}
Ints represents a 32-bit signed data type.  



## Functions


### self.length : [u32](./u32.md) {.code}

### self.capacity : [u32](./u32.md) {.code}
FIXME: UNIMPLEMENTED

## Operators

### self[u32] : (T + [Unit](./Unit.md)) {.code}
Looks up a value in the vector. If it is within bonds, the value of type T stored at the index is returned. If not, Unit is returned. 

### self[u32] := T : [boolean](./boolean.md) {.code}
Attempts to assign T to the value at the specified index. If the index is out of bounds, the operation fails and false is returned. Otherwise, true is returned. 

FIXME: NOT IMPLEMENTED; INSTEAD WE CURRENTLY PROPAGATE THE VALUE!

### int + int : int {.code}

Performs a "No Signed Wrap (NSW)" addition of two integers. 


### int - int : int {.code}

### int < int : [boolean](./boolean.md) {.code}

### int <= int : [boolean](./boolean.md) {.code}

### int > int : [boolean](./boolean.md) {.code}

### int >= int : [boolean](./boolean.md) {.code}

### int == int : [boolean](./boolean.md) {.code}

### int != int : [boolean](./boolean.md) {.code}

### int * int : int {.code}

### int / int : int {.code}

### int % int : int {.code}


## Specifications 
* Size: Sizeof Pointer + 64 bits (stack), capacity * sizeof stored data type (heap)
* Default Value: 0 
* Default Location: Mixed 
* Default Modifiers: Non-linear 



