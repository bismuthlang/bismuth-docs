 # Types 


| Type Name 			| Version |	Description 			  |
|-------------------------------|---------|---------------------------------------|
| [int](./types/int.md) 				| `0.0.1` | A 32-bit signed integer		  |
| [boolean](./types/boolean.md) 			| `0.0.1` | A 1-bit boolean value 		  | 
| [str](./types/str.md) 				| `0.0.1` | A constant string literal 		  | 
| [Box\<T\>](./types/Box.md) 				| `0.0.1` | A pointer to data allocated on the heap | 
| [Unit](./types/Unit.md) 				| `0.0.1` | The type which only has one value 	  | 
| [T[N]](./types/array.md)				| `0.0.1` | An array of type T of fixed length N  | 
| [T[]](./types/vector.md) 				| `1.3.4` | An array of type T dynamically sized  |
| enum 				| `0.0.1` | (AKA. Sum Type, Tagged Union) A type of data which can store one of multiple specified data types | 
| struct 			| `0.0.1` | (AKA. Product Type) A type of data which can store multiple pre-specified types of data simultaneously |  
| func 				| `0.0.1` | A synchronous function 	          |
| Program			| `0.0.1` | A program which can be executed asynchronously | 
| [Channel](./types/Channel.md)			| `0.0.1` | A channel which allows for communicating to another program | 
