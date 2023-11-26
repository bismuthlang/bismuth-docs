# Channel\<P\> {.code}
Channels allow asynchronous type-safe communication between two processes. Channels are templated by a [Session Type](../protocols.md), P, to specify what operations are allowed on them at any given time. 

## Functions

### {self : -T;P} self.send(e : T) : {self : P} Unit {.code}

### {self : +T;P} self.recv() : {self : P} T {.code}

### {self : ?P_1;P_2} unfold(self) : {self : P_1;?P_1;P2} Unit {.code}

### {self : \*?P_1;P_2} unfold(self) : {self : P_1;\*?P_1;P2} Unit {.code}

### {self : ?P_1;P_2} more(self) : {self : P_1;?P_1;P2} Unit {.code}
*Deprecated; See unfold.*

### {self : \*?P_1;P_2} more(self) : {self : P_1;\*?P_1;P2} Unit {.code}
*Deprecated; See unfold.*

### {self : ?P_1;P_2} weaken(self) : {self : P_2} Unit {.code}


FIXME: WHERE DO ACCEPT + WEAKEN + BRANCHES GO?

## Operators

### !boolean : boolean {.code}

### boolean == boolean : boolean {.code}

### boolean != boolean : boolean {.code}

### boolean & boolean : boolean {.code}

### boolean | boolean : boolean {.code}

## Specifications 
* Size: FIXME
* Default Value: N/A
* Default Location: FIXME 
* Default Modifiers: Temporal, Linear (can be made Lossy via `Channel<Cancelable<P>>`)


