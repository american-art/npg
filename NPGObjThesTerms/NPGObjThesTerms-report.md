### Model ScreenShot

[Click here to view the model screenshot](https://github.com/american-art/npg/blob/master/model_graphviz_pdf/NPGObjThesTerms_Sheet1.model.pdf)


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
