# Program {.code}
Programs are asynchronous blocks of code that can be executed and then communicated with via [Channels](./Channel.md). Because program execute asynchronously, data communicated to them via channels is copied if it is non-linear and moved if it is linear. As with [functions](./func.md), because programs are higher-order, they currently do not capture outside resources besides definitions. This means that any resources a program needs to execute must be communicated to it via its channel once it has been executed. 

Currently programs also serve as the main entrypoint to a bismuth program. Specifically, a program named `program` that follows session type `-int` will be seen as the entrypoint. 


## Syntax 

Programs are currently defined using the following syntax: 
```bismuth 
define <NAME> :: <CHANNEL ID> : Channel<<SESSION TYPE>> {
   // Code 
}
```
In this syntax, `<NAME>` represents the name of the program, `<CHANNEL ID>` is the identifier that will be bound to the channel following session type `<SESSION TYPE>` that the program uses to communicate back to the parent process. 

For example consider the following program: 

```bismuth
define foo :: c : Channel<-int> {
  c.send(0); 
}
```
In this example, we define program `foo` which communicates over channel `c` following session type `-int`. 

Programs themselves can be treated as higher order and stored as a variable wherein they are represented by the type `Program<<SESSION TYPE>>` wherein `<SESSION TYPE>` is the session type that the program will follow when executed. For example, extending our previous example, program `foo` could be stored as follows:

```bismuth 
Program<-int> prog := foo; 
```

## Specifications 
* Default Location: Text/Code segment of the executable file 
* Default Modifiers: Non-linear 



