# For {.code}
Repeats a portion of code so long as a condition is true which is updated at the end of each iteration

Upon entering a loop, any existing linear resources become guarded and, within loops, all non-guarded linear resources must be used. This ensures the type safe use of linear resources despite the loop's repitition. More details are forthcoming; however, the original Bismuth [paper](https://bismuth-lang.org/ahf-CommunicatingProcessCalculus.pdf#subsubsection.7.3.1) may be useful.

## Syntax 

For loops follows the following syntax: 

```bismuth
for((variableDeclaration | assignmentStatement); condition : boolean; statement) {
     // Loop body code
}
```

For example, a for loop that repeats 10 times could be written as: 
```bismuth 
for(int i := 0; i < 10; i := i + 1) {
  // Loop body code
}
```
This could also be written as 
```bismuth 
int i := ...; 
for(i := 0; i < 10; i := i + 1) {
  // Loop body code
}
```




