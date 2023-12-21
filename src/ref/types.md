 # Types 
Bismuth has both data types for describing the type of a resource in a program (e.g., a variable) as well as session types which represent the communication protocols that programs use to communicate via channels with. The former of these is often represented by an uppercase `T` when referring to any data type. The latter is often represented by a `P` when referring to any session type. These are each ellaborated in their respective sections on this page. 

## Data Types

| Type Name 			| Version |	Description 			  |
|-------------------------------|---------|---------------------------------------|
| [int](./types/int.md) 				| `0.0.1` | A 32-bit signed integer		  |
| [boolean](./types/boolean.md) 			| `0.0.1` | A 1-bit boolean value 		  | 
| [str](./types/str.md) 				| `0.0.1` | A constant string literal 		  | 
| [Box\<T\>](./types/Box.md) 				| `0.0.1` | A pointer to data allocated on the heap | 
| [Unit](./types/Unit.md) 				| `0.0.1` | The type which only has one value 	  | 
| [T[N]](./types/array.md)				| `0.0.1` | An array of type T of fixed length N  | 
| [T[]](./types/vector.md) 				| `1.3.4` | An array of type T dynamically sized  |
| [enum](./types/enum.md) 				| `0.0.1` | (AKA. Sum Type, Tagged Union) A type of data which can store one of multiple specified data types | 
| [struct](./types/struct.md) 			| `0.0.1` | (AKA. Product Type) A type of data which can store multiple pre-specified types of data simultaneously |  
| [func](./types/func.md) 				| `0.0.1` | A synchronous function 	          |
| [Program](./types/Program.md)			| `0.0.1` | A program which can be executed asynchronously | 
| [Channel\<P\>](./types/Channel.md)			| `0.0.1` | A channel which allows for communicating to another program | 


## Session Types


|  Protocol Name                | Syntax |Version| Description                 |
|-------------------------------|--------|-------|-----------------------------|
| Send			        |  `-T`  |`0.0.1`| Send data of type `T` to the other process. 		|
| Recieve			|  `+T`  |`0.0.1`| Recieve data of type `T` from the other process. 	|
| Sequence			|`P_1;P_2` |`0.0.1`|Follow protocol `P_1`, then `P_2`.		   	|
| Why not			|  `?P`  |`0.0.1`| Repeat protocol `P` any number of times as chosen by the local process.|
| Of course			|  `!P`  |`0.0.1`| Repeat protocol `P` a number of times chosen by the other process.|
| Internal Choice		|`InternalChoice<P_1, P_2, ...>` |`0.0.1`| The local process gets to determine which of the provided protocols (`P_1`, `P_2`, etc) to follow) |
| External Choice		|`ExternalChoice<P_1, P_2, ...>`|`0.0.1`| The other process gets to determine which of the provided protocols (`P_1`, `P_2`, etc) to follow) |
| Cancelable			| `Cancelable<P>` | `1.3.4` | Allows the protocol `P` to be canceled by either party privy to the protocol at any time. |
