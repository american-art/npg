
### Python Transformations
#### ObjectURI:
*PyTransform* 
```
return “object/"+getValue("ObjectID")
```
*Explanation* 

This URI will then be concatenated to the museum URI (base URI) to form the complete Object URI. 



#### TermURI:
*PyTransform* 
```
if getValue("Term"):
    return getValue("Path").replace(" “,"-")+getValue("Term"); 
```
*Explanation*  

This URI is formed by formatting the "Path" information and then concatenate with the "Term" value. 
