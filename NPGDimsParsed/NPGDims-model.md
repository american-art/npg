# NPGObjDimsParsed3.csv

## Add Column

## Add Node/Literal
#### Literal Node: `http://vocab.getty.edu/aat/300266036`
Literal Type: ``
<br/>Language: ``
<br/>isUri: `true`


## PyTransforms
#### _ObjectURI_
From column: _ObjectID_
``` python
return "object/"+getValue("ObjectID")
```

#### _DimensionTextURI_
From column: _DisplayDimensions_
``` python
return getValue("ObjectURI")+"/dimension_text"
```

#### _PartURI_
From column: _Element_
``` python
return UM.uri_from_fields(getValue("ObjectURI")+"/",getValue("Element"))
```

#### _DimensionURI_
From column: _DimensionID_
``` python
return getValue("PartURI")+"/dimension/"+getValue("DimensionID") + ""
```

#### _DimensionTypeURI_
From column: _DimensionType_
``` python
return UM.uri_from_fields("thesauri/dimension_type/",getValue("DimensionType"))
```

#### _Dimension_clean_
From column: _Dimension_
``` python
return str(int(float(getValue("Dimension"))*10)/10.0)
```

#### _UnitURI_
From column: _PrimaryUnitID_
``` python
return UM.uri_from_fields("thesauri/dimension_unit/",getValue("PrimaryUnitID"))
```


## Selections

## Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _DimensionTextURI_ | `uri` | `crm:E33_Linguistic_Object1`|
| _DimensionType_ | `skos:prefLabel` | `crm:E55_Type1`|
| _DimensionTypeURI_ | `uri` | `crm:E55_Type1`|
| _DimensionURI_ | `uri` | `crm:E54_Dimension1`|
| _Dimension_clean_ | `rdf:value` | `crm:E54_Dimension1`|
| _DisplayDimensions_ | `rdf:value` | `crm:E33_Linguistic_Object1`|
| _Element_ | `rdfs:label` | `crm:E18_Physical_Thing1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _PartURI_ | `uri` | `crm:E18_Physical_Thing1`|
| _PrimaryUnitID_ | `skos:prefLabel` | `crm:E58_Measurement_Unit1`|
| _UnitURI_ | `uri` | `crm:E58_Measurement_Unit1`|


## Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E18_Physical_Thing1` | `crm:P43_has_dimension` | `crm:E54_Dimension1`|
| `crm:E22_Man-Made_Object1` | `crm:P46_is_composed_of` | `crm:E18_Physical_Thing1`|
| `crm:E22_Man-Made_Object1` | `crm:P67i_is_referred_to_by` | `crm:E33_Linguistic_Object1`|
| `crm:E33_Linguistic_Object1` | `crm:P2_has_type` | `http://vocab.getty.edu/aat/300266036`|
| `crm:E54_Dimension1` | `crm:P2_has_type` | `crm:E55_Type1`|
| `crm:E54_Dimension1` | `crm:P91_has_unit` | `crm:E58_Measurement_Unit1`|
