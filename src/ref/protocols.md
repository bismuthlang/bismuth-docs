# Protocols
In Bismuth, processes interact through channels whose operations are described through protocols. FIXME-ELABORATE

|  Protocol Name                | Syntax |Version| Description                 |
|-------------------------------|--------|-------|-----------------------------|
| Send			        |  `-t`  |`0.0.1`| Send data of type `t` to the other process. 		|
| Recieve			|  `+t`  |`0.0.1`| Recieve data of type `t` from the other process. 	|
| Sequence			|`p_1;p_2` |`0.0.1`|Follow protocol `p_1`, then `p_2`.		   	|
| Why not			|  `?p`  |`0.0.1`| Repeat protocol `p` any number of times as chosen by the local process.|
| Of course			|  `!p`  |`0.0.1`| Repeat protocol `p` a number of times chosen by the other process.|
| Internal Choice		|`InternalChoice<p_1, p_2, ...>` |`0.0.1`| The local process gets to determine which of the provided protocols (`p_1`, `p_2`, etc) to follow) |
| External Choice		|`ExternalChoice<p_1, p_2, ...>`|`0.0.1`| The other process gets to determine which of the provided protocols (`p_1`, `p_2`, etc) to follow) |
| Cancelable			| `Cancelable<p>` | `1.3.4` | Allows the protocol `p_1` to be canceled by either party privy to the protocol at any time. |



