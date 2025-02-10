# struct {.code}
Structs (AKA. Product types) respresent a type of data which stores a value that has labeled fields of specified types.


## Syntax 

Structs are defined using the following syntax where `T_i` represents the type of the data stored by the field labeled by `N_i`: 
```bismuth 
enum <NAME> {
    T_1 N_1;  
    ..., 
    T_n N_n; 
}
```

For example, a linked list of integers could be defined as follows: 
```bismuth 
enum ListNode {
    int value; 
    (Unit + Box<ListNode>) next; 
}
```

Structs are then initialized using the syntax `<NAME>::init(e_1 : T_1, ..., e_n : T_n)` where `e_i : T_i` represents an expression `e_i` of type `T_i` whose value will be used to initialize the ith element in the struct. For example, the previous ListNode could be initialized as follows: 

```bismuth 
ListNode root := ListNode::init(1, Unit::init());
ListNode ele2 := ListNode::init(2, Unit::init()); 
```

Each field in the struct can then be accessed via the `self.<FIELD NAME>` notation. For example: 
```bismuth 
root.next := ele2; 
```


## Specifications 
* Size: Sum of the size of each element in the struct (padded as needed to have proper alignment)
* Default Location: Stack 
* Default Modifiers: Non-linear 



