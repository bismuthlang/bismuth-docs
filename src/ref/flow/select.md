# Select {.code}
Select allows one to write a series of [boolean](../types/boolean.md) conditions along with an expression. The first boolean expression to evaluate to `true` will have its corresponding expression evalued. This makes it similar to an [if/else](./if.md) statement.


## Syntax 

```bismuth
select {
  e_1: e2
  ...
  e_i: e_j
}
```

For example:
```bismuth
int i := ...;
select {
  i == 1: ... // evaluated if i == 1
  i == 2: ... // evaluated if i == 2
  i == 1: ... // will never be evaluated as it is hidden by prior condition
  i < 5 : ... // evaluated if none of the prior conditions are true and and i < 5
  true: ...   // will be evaluated if none of the prior conditions are true
}
```
