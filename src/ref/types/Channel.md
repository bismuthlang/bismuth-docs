# Channel\<P\> {.code}
Channels allow asynchronous type-safe communication between two processes. Channels are templated by a [Session Type](../types.html#session-types), P, to specify what operations are allowed on them at any given time. 

## Functions

### self.send(e : T) : Unit {.code}
* Given: `self : -T;P`
* Action: Sends the result of evaluating expression `e : T` to the remote process. If `e` is linear, the sent value will be copied. If it is non-linear, then the value will be moved to the remote process.
* Result: `self : P`

### self.recv() :  T {.code}
* Given: `self : +T;P`
* Action: Receives a value of type `T` from the remote processs.
* Result: `self : P`

### unfold(self) : Unit {.code}
* Given: `self : ?P_1;P_2`
* Action: Unfolds an interation of `P_1` from `?P_1`. 
* Result: `self : P_1;?P_1;P_2`

### unfold(self) : Unit {.code}
* Given: `self : *?P_1;P_2`
* Action: Unfolds an interation of `P_1` from `*?P_1` (`P_1` is guarded). 
* Result: `self : P_1;*?P_1;P_2`

### more(self) : Unit {.code}
*Deprecated; See unfold.*

### more(self) : Unit {.code}
*Deprecated; See unfold.*

### weaken(self) : Unit {.code}
* Given: `self : ?P_1T;P_2`
* Action: Finishes loop `?P_1`. 
* Result: `self : P_2`

### self[P_i] : Unit {.code}
* Given: `self : InternalChoice<P_1, ..., P_n>`
* Action: Selects protocol `P_i` from the internal choice to follow. 
* Result: `self : P_i`


## Channel-Specific Control Flow Operations

### acccept(self) {...} {.code} 
* Given: `self : !P_1;P_2`
* Action: Allows us to repeat the loop body as many times as are requested by the remote process to fulfill `!P_1`. Outside of the loop, the channel thus continues as `c : P_2`.
* See [here](https://bismuth-lang.org/ahf-CommunicatingProcessCalculus.pdf#subsubsection.7.3.1) for details.

### acceptWhile(self, e : boolean) {...} {.code}
* Given: `self : !P_1;P_2` or `self : *!P_1;P_2`
* Action: Allows us to repeat the loop body as many times as are requested by the remote process so long as `e` evaluates to `true`. Outside of the loop, the channel thus continues as `c : !P_1;P_2` or `self : *!P_1;P_2` (the session is returned to its state before the `acceptWhile`).
* See [here](https://bismuth-lang.org/ahf-CommunicatingProcessCalculus.pdf#subsubsection.7.3.1) for details.

### acceptIf(self, e : boolean) {...} {.code}
* Given: `self : !P_1;P_2` or `self : *!P_1;P_2`
* Action: Allows us to unfold a single iteration of the of course loop so long as the remote process requests it of us and `e` evaluates to `true`. After the `acceptIf`, the channel thus continues as `c : !P_1;P_2` or `self : *!P_1;P_2` (the session is returned to its state before the `acceptIf`)
* Details forthcoming; however, the original Bismuth [paper](https://bismuth-lang.org/ahf-CommunicatingProcessCalculus.pdf#subsubsection.7.3.1) may be useful.

### offer self (| P_i => ...)* {.code}
* Given: `self : ExternalChoice<P_1, ..., P_n>`
* Action: Allows us to perform a case analysis on each offered session type to allow for us to branch to a program which follows the selected session type. 

Example:
```bismuth 
// Given c : ExternalChoice<-int, +boolean;-boolean>

offer c 
  | -int => c.send(5);
  | +boolean => {
  	boolean b := c.recv(); 
  	c.send(!b);
    }
```

## Specifications 
* Size: TODO
* Default Location: FIXME 
* Default Modifiers: Temporal, Linear


