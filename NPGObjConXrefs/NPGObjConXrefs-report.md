

### Python Transformations
#### ObjectURI:
*PyTransform* 
```
return “object/"+getValue("ObjectID")
```
*Explanation* 

This URI will then be concatenated to the museum URI (base URI) to form the complete Object URI. 




#### ArtistURI:
*PyTransform* 
```
if getValue("Prefix") == 'Artist:':
    return "person-institution/" + getValue("ConstituentID")
```
*Explanation* 

This URI will then be concatenated to the museum URI (base URI) to form the complete Artist URI. The set of Artist URI is a subset of Constituent URI.



#### SitterURI:
*PyTransform* 
```
if getValue("Prefix") == 'Sitter:':
    return "person-institution/" + getValue(“ConstituentID")
```
*Explanation* 

This URI will then be concatenated to the museum URI (base URI) to form the complete Sitter URI. The set of Sitter URI is a subset of Constituent URI.
