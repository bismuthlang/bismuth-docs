# While {.code}
While loops allow a block of code to be repeated to long as the loop's boolean condition evaluates to true. 

Upon entering a loop, any existing linear resources become guarded and, within loops, all non-guarded linear resources must be used. This ensures the type safe use of linear resources despite the loop's repitition. More details are forthcoming; however, the original Bismuth [paper](https://bismuth-lang.org/ahf-CommunicatingProcessCalculus.pdf#subsubsection.7.3.1) may be useful.

## Syntax 

While loops follows the following syntax: 

```bismuth
while(e : boolean) { // Note, parenthesis around contion are optional
  // Loop body code
}
```

For example, a while loop that repeats 10 times could be written as: 
```bismuth 
int i := 0; 

while i < 10 {
  i := i + 1; 
}
```


