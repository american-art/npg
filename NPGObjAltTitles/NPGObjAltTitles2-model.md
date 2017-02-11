# NPGObjTitles2.csv

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
return UM.uri_from_fields("thesauri/title/", getValue("Title"))
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

#### _AlternateTitleType_
From column: _DisplayOrder_
``` python
return "Alternate Title"
```

#### _AltTitleTypeURI_
From column: _DisplayOrder_
``` python
return getValue("TitleURI")+"/title_type"
```


## Selections
#### _DEFAULT_TEST_
From column: _ObjectID_
<br>Operation: `Union`
``` python
return getValue("DisplayOrder")=="1"
```


## Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _AltTitleTypeURI_ | `uri` | `crm:E55_Type1`|
| _AlternateTitleType_ | `skos:prefLabel` | `crm:E55_Type1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _PreferredTitleCopy_ | `rdf:value` | `crm:E35_Title1`|
| _TitleURI_ | `uri` | `crm:E35_Title1`|


## Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E22_Man-Made_Object1` | `crm:P102_has_title` | `crm:E35_Title1`|
| `crm:E35_Title1` | `crm:P2_has_type` | `crm:E55_Type1`|
