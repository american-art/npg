### Model ScreenShot

[Click here to view the model screenshot](https://github.com/american-art/npg/blob/master/model_graphviz_pdf/NPGConstituents_Sheet1.model.pdf)


### Python Transformations
#### ConstituentURI:
*PyTransform* 
```
return “person-institution/"+getValue("ConstituentID")
```
*Explanation* 

This URI will then be concatenated to the museum URI (base URI) to form the complete person/institution URI. 



#### ActorAppellationURI:
*PyTransform* 
```
return “person-institution/"+getValue("ConstituentID")+"/appellation"
```
*Explanation* 

This URI will then be concatenated to the museum URI (base URI) to form the complete Actor Appellation URI. 



#### DisplayPersonInstitutionName:
*PyTransform* 
```
if getValue("DisplayName") == 'NULL':
    return getValue("Institution")
else:
    return getValue(“DisplayName”)
```
*Explanation* 

Since the name of the person is displayed in "DisplayName" column while the name of the institution is displayed in "Institution" column, this class combines both columns so that there's an entry for each person/institution. It is then used as label for ActorAppellation



#### FirstNameURI:
*PyTransform* 
```
if getValue("FirstName") == 'NULL':
    return ""
else:
    return "thesauri/nametype/firstname"
```
*Explanation* 

This is the URI of the type of name, here it's the first name of any person (if exist).



#### FirstNameAppellationURI:
*PyTransform* 
```
if getValue("FirstName") == 'NULL':
    return ""
else:
    return getValue("ConstituentURI")+"/appellation/firstname"
```
*Explanation* 

This URI will then be concatenated to the museum URI (base URI) to form the complete First Name Appellation URI. 




#### MiddleNameURI:
*PyTransform* 
```
if getValue("MiddleName") == 'NULL':
    return ""
else:
    return "thesauri/nametype/middlename"
```
*Explanation* 

This is the URI of the type of name, here it's the middle name of any person (if exist).




#### FirstNameAppellationURI:
*PyTransform* 
```
if getValue("MiddleName") == 'NULL':
    return ""
else:
    return getValue("ConstituentURI")+"/appellation/middlename"
```
*Explanation* 

This URI will then be concatenated to the museum URI (base URI) to form the complete Middle Name Appellation URI. 




#### LastNameURI:
*PyTransform* 
```
if getValue("LastName") == 'NULL':
    return ""
else:
    return "thesauri/name/lastname"
```
*Explanation* 

This is the URI of the type of name, here it's the last name of any person (if exist).




#### LastNameAppellationURI:
*PyTransform* 
```
if getValue("LastName") == 'NULL':
    return ""
else:
    return getValue("ConstituentURI")+"/appellation/lastname"
```
*Explanation* 

This URI will then be concatenated to the museum URI (base URI) to form the complete Last Name Appellation URI. 




#### BirthURI:
*PyTransform* 
```
if getValue("BeginDate"):
    if int (getValue("BeginDate"))>0:
        return getValue("ConstituentURI")+"/birth"
    else:
        return ""
else:
    return ""
```
*Explanation* 

This URI will then be concatenated to the museum URI (base URI) to form the complete Birth URI, if the birth date information exists for the constituent. 



#### BirthDateURI:
*PyTransform* 
```
if getValue("BirthURI"):
    return getValue("BirthURI")+"/date"
else:
    return “"

```
*Explanation* 

This URI will then be concatenated to the museum URI (base URI) to form the complete Birth Date URI, if the birth date information exists for the constituent. 




#### DeathURI:
*PyTransform* 
```
if getValue("EndDate"):
    if int (getValue("EndDate"))>0:
        return getValue("ConstituentURI")+"/death"
    else:
        return ""
else:
    return “"
```
*Explanation* 

This URI will then be concatenated to the museum URI (base URI) to form the complete Death URI, if the death date information exists for the constituent. 




#### DeathDateURI:
*PyTransform* 
```
if getValue("DeathURI"):
    return getValue("DeathURI")+"/date"
else:
    return “"
```
*Explanation* 

This URI will then be concatenated to the museum URI (base URI) to form the complete Death Date URI, if the death date information exists for the constituent. 
