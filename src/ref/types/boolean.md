# boolean {.code}
Booleans represent a value that is either `true` or `false`.

## Operators

### !self : boolean {.code}

Negates the given boolean expression. 

Example: 
```bismuth 
boolean a := !true;  // false 
boolean b := !false; // true 
```

### self == boolean : boolean {.code}

Determines if two boolean expressions are equal. 

Example: 
```bismuth 
boolean a := true == true;   // true 
boolean b := true == false;  // false
boolean c := false == true;  // false 
boolean d := false == false; // true
```

### self != boolean : boolean {.code}

Determines if two boolean expressions are different. 

Example: 
```bismuth 
boolean a := true != true;   // false 
boolean b := true != false;  // true 
boolean c := false != true;  // true 
boolean d := false != false; // false
```

### self && boolean : boolean {.code}

Ands two boolean expressions with short-circuiting. 

Example:
```bismuth
boolean a := true & true;   // true 
boolean b := false & false; // false 
boolean c := false & true;  // false 
```

### self || boolean : boolean {.code}

Ors two boolean expressions with short-circuiting. 

Example: 
```bismuth 
boolean a := true | true;   // true 
boolean b := false | false; // false 
boolena c := false | true;  // true
```

## Specifications 
* Size: 1 bit
* Default Value: `false` (0) 
* Default Location: Stack 
* Default Modifiers: Non-linear 



