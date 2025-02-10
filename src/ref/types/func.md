# func {.code}
Functions are synchronous snippets of code that can take parameters and return a value. Currently, functions do not support capturing outside variables (they are not closures) thus, any resources they use must be provided explicitly as arguments. As functions are synchronous, arguments are passed as reference values (as opposed to programs/channels wherein data is either copied or moved). 


## Syntax 

Functions can either be anonymous (defined in-place) or named. Anonymous funcs are defined using the syntax where `T_i` represents the type of the ith parameter which is named `N_n`, `T_r` is the type of data returnd by the function, and the code between the `{}` braces defines the body of the function:

```bismuth 
(T_1 N_1, ... , T_n N_n) -> T_r {...}
```

For example, an anonymous function to square a number could be defined as follows: 
```bismuth
(int i) -> int { return i * i; }
```

Functions can be stored as values or called in-line with their anonymous definition as shown below: 
```bismuth 
(int) -> int square := (int i) -> int { return i * i; }
int result1 := (int i) -> int { return i * i; }(2); // 4
int result2 := square(2); // 4
```

Functions can also be defined with a name to enable recursive use: 
```bismuth 
func fib(int n) -> int {
  if(n == 0 | n == 1) {
    return n;
  }

  return fib(n - 1) + fib(n - 2);
}
```

## Specifications 
* Default Location: Text/Code segment of the executable file 
* Default Modifiers: Non-linear 



