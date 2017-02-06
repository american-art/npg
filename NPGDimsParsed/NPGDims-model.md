# NPGDimsParsedUpdate2May.csv

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
return getValue("ObjectURI")+"/element"
```

#### _DimensionURI_
From column: _Element_
``` python
return getValue("PartURI")+"/dimension"
```

#### _TypeURI_
From column: _ElementRank_
``` python
return getValue("DimensionURI")+"/"+getValue("DimensionType").lower()
```


## Selections

## Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _DimensionClean_ | `rdf:value` | `crm:E54_Dimension1`|
| _DimensionPart_ | `uri` | `crm:E18_Physical_Thing1`|
| _DimensionType_ | `skos:prefLabel` | `crm:E55_Type1`|
| _DimensionURI_ | `uri` | `crm:E54_Dimension1`|
| _Element_ | `rdfs:label` | `crm:E18_Physical_Thing1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _TypeURI_ | `uri` | `crm:E55_Type1`|


## Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E18_Physical_Thing1` | `crm:P43_has_dimension` | `crm:E54_Dimension1`|
| `crm:E22_Man-Made_Object1` | `crm:P46_is_composed_of` | `crm:E18_Physical_Thing1`|
| `crm:E54_Dimension1` | `crm:P2_has_type` | `crm:E55_Type1`|
