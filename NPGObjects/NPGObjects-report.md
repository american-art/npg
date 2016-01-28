### Model ScreenShot

[Click here to view the model screenshot](https://github.com/american-art/npg/blob/master/model_graphviz_pdf/NPGObjects_Sheet1.model.pdf)


### Python Transformations
#### ObjectURI:
*PyTransform* 
```
return “object/"+getValue("ObjectID")
```
*Explanation* 

This URI will then be concatenated to the museum URI (base URI) to form the complete Object URI. 



#### ClassificationURI:
*PyTransform* 
```
if getValue("Classification"):
    return "thesauri/classification/"+getValue("Classification").replace(" ","-")
else:
    return “"
```



#### ProductionURI:
*PyTransform* 
```
return getValue("ObjectURI")+"/production"
```
*Explanation* 

This URI will then be concatenated to the museum URI (base URI) to form the complete Production URI. 




#### ProductionDateURI:
*PyTransform* 
```
return getValue("ObjectURI")+"/production/date"
```
*Explanation* 

This URI will then be concatenated to the museum URI (base URI) to form the complete Production Date URI. 




#### DimenstionURI:
*PyTransform* 
```
return getValue(“ObjectURI")+"/dimensions"
```
*Explanation* 

This URI will then be concatenated to the museum URI (base URI) to form the complete Production Date URI. 