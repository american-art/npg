# NPGObjThesTerms2.csv

## Add Column

## Add Node/Literal
#### Literal Node: `http://vocab.getty.edu/aat/300179869`
Literal Type: ``
<br/>Language: ``
<br/>isUri: `true`


## PyTransforms
#### _ObjectURI_
From column: _ObjectID_
``` python
return "object/"+getValue("ObjectID")
```

#### _MaterialURI_
From column: _ThesXrefType_
``` python
if getValue("ThesXrefType") in ["Medium","Support"]:
    return UM.uri_from_fields("thesauri/material/",getValue("Term"))
else:
    return ""
```

#### _ClassificationURI_
From column: _ThesXrefType_
``` python
if getValue("ThesXrefType")=="Other Classification":
    return getValue("ObjectURI")+"/classification_event"
else:
    return ""
```

#### _SubjectURI_
From column: _ThesXrefType_
``` python
if getValue("ThesXrefType") in ["Place depicted","Portrait Objects", "Related Place"]:
    return UM.uri_from_fields("thesauri/subject/",getValue("Term"))
else:
    return ""
```

#### _ProductionURI_
From column: _ObjectURI_
``` python
if getValue("ThesXrefType")=="Execution place":
    return getValue("ObjectURI")+"/production"
else:
    return ""
```

#### _PlaceURI_
From column: _ThesXrefType_
``` python
if getValue("ThesXrefType")=="Execution place":
    return UM.uri_from_fields("thesauri/place/",getValue("Term"))
else:
    return ""
```

#### _Place_
From column: _PlaceURI_
``` python
if getValue("ThesXrefType")=="Execution place":
    return getValue("Term")
else:
    return ""
```

#### _MaterialValue_
From column: _MaterialURI_
``` python
if getValue("ThesXrefType") in ["Medium","Support"]:
    return getValue("Term")
else:
    return ""
```

#### _SubjectLabel_
From column: _MaterialValue_
``` python
if getValue("ThesXrefType") in ["Place depicted","Portrait Objects", "Related Place"]:
    return getValue("Term")
else:
    return ""
```

#### _ClassificationTypeURI_
From column: _ClassificationURI_
``` python
if getValue("ThesXrefType")=="Other Classification":
    v = getValue("Term")
    try:
        uri = AATTerm.get_aat_uri("npg",v)
        return uri
    except:
        return UM.uri_from_fields("thesauri/type/",v)
else:
    return ""
```

#### _TypeLabel_
From column: _ClassificationTypeURI_
``` python
if getValue("ThesXrefType")=="Other Classification":
    return getValue("Term")
else:
    return ""
```


## Selections

## Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _ClassificationTypeURI_ | `uri` | `crm:E55_Type1`|
| _ClassificationURI_ | `uri` | `crm:E17_Type_Assignment1`|
| _MaterialURI_ | `uri` | `crm:E57_Material1`|
| _MaterialValue_ | `skos:prefLabel` | `crm:E57_Material1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _Place_ | `rdfs:label` | `crm:E53_Place1`|
| _PlaceURI_ | `uri` | `crm:E53_Place1`|
| _ProductionURI_ | `uri` | `crm:E12_Production1`|
| _SubjectLabel_ | `rdfs:label` | `owl:Thing1`|
| _SubjectURI_ | `uri` | `owl:Thing1`|
| _TypeLabel_ | `rdfs:label` | `crm:E55_Type1`|


## Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E12_Production1` | `crm:P7_took_place_at` | `crm:E53_Place1`|
| `crm:E17_Type_Assignment1` | `crm:P42_assigned` | `crm:E55_Type1`|
| `crm:E17_Type_Assignment1` | `crm:P21_had_general_purpose` | `http://vocab.getty.edu/aat/300179869`|
| `crm:E22_Man-Made_Object1` | `crm:P108i_was_produced_by` | `crm:E12_Production1`|
| `crm:E22_Man-Made_Object1` | `crm:P41i_was_classified_by` | `crm:E17_Type_Assignment1`|
| `crm:E22_Man-Made_Object1` | `crm:P45_consists_of` | `crm:E57_Material1`|
| `crm:E22_Man-Made_Object1` | `crm:P62_depicts` | `owl:Thing1`|
| `crm:E22_Man-Made_Object1` | `crm:P2_has_type` | `crm:E55_Type1`|
