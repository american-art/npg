# NPGDimsParsedUpdate1Nov.csv

## Add Column

## Add Node/Literal

## PyTransforms
#### _ObjectURI_
From column: _ObjectID_
``` python
return "object/"+getValue("ObjectID")
```

#### _DimensionClean_
From column: _Dimension_
``` python
return str(int(float(getValue("Dimension"))*10)/10.0)
```

#### _PartURI_
From column: _DimItemElemXrefID_
``` python
return UM.uri_from_fields(getValue("ObjectURI")+"/",getValue("Element"))
```

#### _DimensionURI_
From column: _Element_
``` python
return getValue("PartURI")+"/dimension/"+getValue("DimensionsID")
```

#### _TypeURI_
From column: _ElementRank_
``` python
return UM.uri_from_fields("thesauri/dimension_type/",getValue("DimensionType"))
```

#### _UnitURI_
From column: _PrimaryUnit_
``` python
return UM.uri_from_fields("thesauri/dimension_unit/",getValue("PrimaryUnit"))
```

#### _DimensionTextURI_
From column: _DisplayDimensions_
``` python
return getValue("ObjectURI")+"/dimension_text"
```


## Selections

## Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _DimensionClean_ | `rdf:value` | `crm:E54_Dimension1`|
| _DimensionTextURI_ | `uri` | `crm:E33_Linguistic_Object1`|
| _DimensionType_ | `skos:prefLabel` | `crm:E55_Type1`|
| _DimensionURI_ | `uri` | `crm:E54_Dimension1`|
| _DisplayDimensions_ | `rdf:value` | `crm:E33_Linguistic_Object1`|
| _Element_ | `rdfs:label` | `crm:E18_Physical_Thing1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _PartURI_ | `uri` | `crm:E18_Physical_Thing1`|
| _PrimaryUnit_ | `skos:prefLabel` | `crm:E58_Measurement_Unit1`|
| _TypeURI_ | `uri` | `crm:E55_Type1`|
| _UnitURI_ | `uri` | `crm:E58_Measurement_Unit1`|


## Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E18_Physical_Thing1` | `crm:P43_has_dimension` | `crm:E54_Dimension1`|
| `crm:E22_Man-Made_Object1` | `crm:P46_is_composed_of` | `crm:E18_Physical_Thing1`|
| `crm:E22_Man-Made_Object1` | `crm:P67i_is_referred_to_by` | `crm:E33_Linguistic_Object1`|
| `crm:E54_Dimension1` | `crm:P2_has_type` | `crm:E55_Type1`|
| `crm:E54_Dimension1` | `crm:P91_has_unit` | `crm:E58_Measurement_Unit1`|
