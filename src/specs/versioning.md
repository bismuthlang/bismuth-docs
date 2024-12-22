 # Versioning
 
 <div class="warning">

Bismuth is currently in its alpha stage of development (versions `1.4+`). [Versions](versioning.md#alpha) in this stage follow a `1.major.minor` naming scheme. 

As such, version changes that would otherwise be considered minor (i.e., `1.4.X` to `1.5.X`) are to be considered major and potentially breaking.  
</div>


 The following outlines the versioning system for Bismuth.
 
## Overview
 
| Versions			| Name 	  | Format | Description 	            	|
|-------------------------------|---------|--------| -----------------------------------|
| `3+.X.X`	  | Release 	          | `Major.Minor.Patch`|
| `2.X.X` 	  | Beta	 	  | `2.Major.Minor` |				|
| `1.4.X`–`1.X.X` | Alpha	 	  | `1.Major.Minor` | 			 	|
| `1.0`–`1.3.X`	  | Pre-Alpha/Bismuth 	  | `1.Major.Minor` |				|
| `0.1.X.X`       | Pre-Alpha/WPL 	  | `0.(WPL Version)`|				| 

## Alpha 

## Pre-Alpha

Pre-Alpha releases of Bismuth are those which, roughly, pre-date the release of Bismuth's scource code or stem from work that Bismuth 
was based on. To this extent, Pre-Alpha versions are split into two groups: 
* Pre-Alpha/Bismuth (versions `1.0`–`1.3.X`) which describe the former category of releases and, 
* Pre-Alpha/WPL (`0.1.0.0`–`0.1.1.0`) which identify releases in the original project Bismuth was forked from[^wpl].

### Bismuth 

Given Pre-Alpha/WPL's use of versions starting with 0, Pre-Alpha/Bismuth uses versions that start with 1. 

 
### WPL

While Bismuth was created as a separate repository from WPL, given the cose ties between the initial commit in Bismuth's repository (which only started to introduce changes in transitioning from WPL to Bismuth) and WPL's `v1.1.0`, Bismuth's versioning scheme contains a means to refer to the initial WPL releases—though, at this point, they are largely disjoint from current development and cannot be found in the Bismuth repository. 

To account for WPL using three-digit version numbers starting with 1 (i.e., `1.1.0`), we refer to these as `WPL/(version number)` or `0.(version number)` when discussing them 
in the context of Bismuth. 


[^wpl]: The project Bismuth was forked from, [ahfriedman/WPL](https://github.com/ahfriedman/wpl), was Alex's final project for *CS544 Compiler Construction*, taught by Professor Gary Pollice, based on the course's programming language WPL. Thank you Professor Pollice for allowing me to do this for my final project and allowing me to open source Bismuth, my version of WPL, and related course materials. 
