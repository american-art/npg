### Model ScreenShot

[Click here to view the model screenshot](https://github.com/american-art/npg/blob/master/model_graphviz_pdf/NPGObjTitles_Sheet1.model.pdf)


### Python Transformations
#### ObjectURI:
*PyTransform* 
```
return “object/"+getValue("ObjectID")
```
*Explanation* 

This URI will then be concatenated to the museum URI (base URI) to form the complete Object URI. 




#### TitleURI:
*PyTransform* 
```
return getValue("ObjectURI")+"/title/displayOrder/"+getValue("DisplayOrder")
```
*Explanation* 

Since an object might have multiple titles, the Title URI is therefore formed by specifying the DisplayOrder of the titles. 




#### PreferredLabel:
*PyTransform* 
```
if getValue("DisplayOrder") == '1':
    return getValue("Title")
```
*Explanation* 

When an object has multiple titles, we take the title with DisplayOrder=1 as the preferred title.



#### AltLabel:
*PyTransform* 
```
if getValue("DisplayOrder") != '1':
    return getValue("Title")
```
*Explanation* 

When an object has multiple titles, all titles with DisplayOrder not equal to 1 are considered as alternative titles.



