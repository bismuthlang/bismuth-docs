# int {.code}
Ints represents a 32-bit signed data type.  

## Operators

### self + int : int {.code}

Performs a "No Signed Wrap (NSW)" addition of two integers. 
Example: 

```bismuth 
int a := 1 + 2; // 3
```

### self - int : int {.code}

Subtracts the given integer from some other integer.

Example: 

```bismuth 
int a := 5 - 3; // 2 
```

### self < int : [boolean](./boolean.md) {.code}

Determines if the given integer is less than some other integer. 

Example: 

```bismuth 
boolean a := 1 < 2; // true
boolean b := 2 < 2; // false 
boolean c := 3 < 2; // false 
```

### self <= int : [boolean](./boolean.md) {.code}

Determines if the given integer is less than or equal to some other integer. 

Example: 
```bismuth 
boolean a := 1 <= 2; // true 
boolean b := 2 <= 2; // true 
boolean c := 3 <= 3; // false
```

### self > int : [boolean](./boolean.md) {.code}

Determiens if the given integer is greater than some other integer. 

Example: 
```bismuth 
boolean a := 1 > 2; // false 
boolean b := 2 > 2; // false 
boolean c := 3 > 2; // true
```

### self >= int : [boolean](./boolean.md) {.code}

Determines if the given integer is greater than or equal to some other specified integer. 

Example: 
```bismuth 
boolean a := 1 >= 2; // false 
boolean b := 2 >= 2; // true 
boolean c := 3 >= 2; // true
```

### self == int : [boolean](./boolean.md) {.code}

Determines if the given integer is equal to some other specified integer. 

Example: 
```bismuth 
boolean a := 1 == 2; // false
boolean b := 2 == 2; // true
boolean c := 3 == 2; // false 
```

### self != int : [boolean](./boolean.md) {.code}

Determiens if the given integer is not equal to some other specified integer. 

Example: 
```bismuth 
boolean a := 1 != 2; // true 
boolean b := 2 != 2; // false 
boolean c := 3 != 2; // true 
```

### self * int : int {.code}

Multiplies the given integer with some specified integer. 

Example: 
```bismuth 
int a := 3 * 2; // 6 
```

### self / int : int {.code}

Divides the given integer by some other integer. 

Example: 
```bismuth 
int a := 20 / 5; // 4 
```

### self % int : int {.code}

Modulus of the given integer by some other specified integer. 

Example: 
```bismuth 
int a := 21 % 20; // 1
```

## Specifications 
* Size: 32-bits
* Default Value: 0 
* Default Location: Stack 
* Default Modifiers: Non-linear 



