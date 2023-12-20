# str {.code}
Strs represent constant string literals in code. Strings are defined by the text between unescaped quotation marks within the code. Strs do not *yet* have any methods associated with them; however, they can still be usefil (e.g., with printf statements). 


Example: 
```
str s1 := "This is a string";
str s2 := "This string contains a new line \n and a quote! \"";  
```

## Specifications 
* Size: Depends on string length 
* Default Location: Data section of program file 
* Default Modifiers: Non-linear 
