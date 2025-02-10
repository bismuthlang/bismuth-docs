# Box\<T\> {.code}

Boxes represent a pointer to data of a specified type, `T`, that is being stored on the heap. 

## Functions

### Box\<T\>::init(e : T) -> Box\<T\> {.code} 

Creates a new value of type `Box<T>` by storing the result of evaluating the expression `e : T`. 

Example: 
```bismth 
Box<int> box := Box<int>::init(5); // Pointer to a value of 5 stored on the heap. 
```
## Operators

### *self : T {.code}

The dereference expression allows one to gain access to the value the box points to on the heap.

Example: 
```bismuth 
Box<int> box := ...; 

*box := 5; // Stores a value of 5 in the box
int a := *box; // Retreives the value stored in the box. 
```

### self == Box\<T\> : [boolean](./boolean.md)

Returns true if two boxes point to the same memory address and false otherwise. 

### self != Box\<T\> : [boolean](./boolean.md)

Returns true if the two boxes point to different memory addresses. 


## Specifications 
* Size: Pointer Size (depends on architecture) on Stack + sizeof T on the heap 
* Default Location: Mixed 
* Default Modifiers: Non-linear 



