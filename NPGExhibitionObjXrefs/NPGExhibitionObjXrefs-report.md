
### Python Transformations
#### ObjectURI:
*PyTransform* 
```
return “object/"+getValue("ObjectID")
```
*Explanation* 

This URI will then be concatenated to the museum URI (base URI) to form the complete Object URI. 



#### DimensionURI:
*PyTransform* 
```
return getValue(“ObjectURI")+"/dimensions"
```
*Explanation* 

This URI will then be concatenated to the museum URI (base URI) to form the complete Dimension URI. 




#### Acquisition:
*PyTransform* 
```
if getValue("CreditLine"):
    return getValue("CreditLine").split(";")[1]
else:
    return “"
```
*Explanation* 

The Acquisition information is acquired by extracting the first part of CreditLine paragraph.



#### AcquisitionURI:
*PyTransform* 
```
return getValue(“ObjectURI")+"/acquisition"

```
*Explanation* 

The Acquisition information is acquired by extracting the first part of Acauisition paragraph.





