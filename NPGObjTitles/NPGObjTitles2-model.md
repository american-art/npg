# NPGObjTitles2_Sheet1

## Add Column

## Add Node/Literal

## PyTransforms
#### _PreferredTermsURI_
From column: _Title_
``` python
if getValue("DisplayOrder") == '1':
    return "http://vocab.getty.edu/aat/300404670"
else:
    return ''
```

#### _TitleURI_
From column: _Title_
``` python
if getValue("DisplayOrder") == '1':
    return UM.uri_from_fields("thesauri/title/", getValue("Title"))
else:
    return ''
```

#### _PreferredTitle_
From column: _Title_
``` python
if getValue("DisplayOrder") == '1':
    return getValue("Title")
else:
    return ''
```

#### _PreferredTitleCopy_
From column: _PreferredTitle_
``` python
return getValue("PreferredTitle")
```

#### _ObjectURI_
From column: _ObjectID_
``` python
return UM.uri_from_fields("object/", getValue("ObjectID"))
```


## Selections

## Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _PreferredTermsURI_ | `uri` | `crm:E55_Type1`|
| _PreferredTitle_ | `rdfs:label` | `crm:E22_Man-Made_Object1`|
| _PreferredTitleCopy_ | `rdf:value` | `crm:E35_Title1`|
| _TitleURI_ | `uri` | `crm:E35_Title1`|


## Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E22_Man-Made_Object1` | `crm:P102_has_title` | `crm:E35_Title1`|
| `crm:E35_Title1` | `crm:P2_has_type` | `crm:E55_Type1`|
