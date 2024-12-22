# If {.code}
If statements are used to allow code to branch depending on if their [boolean](../types/boolean.md) condition is met. If statments can be followed by an else block to allow for an alternative to occur should the condition be false prior to the control flow merging back together. 

Because of Bismuth having linear resources, type checking ensures that, regardless of how a program may branch, linear resources are used in a manner that is type safe.  More details are forthcoming; however, the original Bismuth [paper](https://bismuth-lang.org/ahf-CommunicatingProcessCalculus.pdf#subsubsection.7.3.1) may be useful as this is similar to how external choices there are handled. 

## Syntax 

If statments follows the following syntax: 

```bismuth
if(e : boolean) // Note, parenthesis around contion are optional
{ 
  // Executed if e is true
}
else // Optional
{
  // Executed if e is false
}
```

## See Also 
* [Select](./select.md)
