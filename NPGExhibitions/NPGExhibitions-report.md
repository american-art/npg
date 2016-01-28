### Model ScreenShot

[Click here to view the model screenshot](https://github.com/american-art/npg/blob/master/model_graphviz_pdf/NPGExhibitions_Sheet1.model.pdf)


### Python Transformations
#### ExhibitionURI:
*PyTransform* 
```
return “exhibition/"+getValue("ExhibitionID")
```
*Explanation* 

This URI will then be concatenated to the museum URI (base URI) to form the complete Exhibition URI. 

