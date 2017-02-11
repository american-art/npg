# NPGObjects2.csv

## Add Column

## Add Node/Literal

## PyTransforms
#### _ObjectURI_
From column: _ObjectID_
``` python
return UM.uri_from_fields("object/", getValue("ObjectID"))
```

#### _RepositoryTermsURI_
From column: _ObjectID_
``` python
return "aat:300404621"
```

#### _ObjectIDURI_
From column: _ObjectID_
``` python
return UM.uri_from_fields("object/id/", getValue("ObjectID"))
```

#### _ObjectIDCopy_
From column: _ObjectID_
``` python
return getValue("ObjectID")
```

#### _PreferredTermsURI_
From column: _ObjectNumber_
``` python
if getValue("ObjectNumber"):
    return "aat:300404670"
else:
    return ''
```

#### _PreferredIDURI_
From column: _ObjectNumber_
``` python
return UM.uri_from_fields("object/preferred_id/", getValue("ObjectNumber"))
```

#### _ObjectNumberCopy_
From column: _ObjectNumber_
``` python
return getValue("ObjectNumber")
```

#### _ClassificationURI_
From column: _Classification_
``` python
if getValue("Classification"):
    return UM.uri_from_fields("thesauri/classification/", getValue("Classification"))
else:
    return ''
```

#### _ClassificationEventURI_
From column: _Classification_
``` python
if getValue("Classification"):
    prefix = getValue("ObjectURI") + "/classification_event"
    return prefix
else:
    return ''
```

#### _VisualWorksURI_
From column: _Classification_
``` python
if getValue("Classification"):
    return "http://vocab.getty.edu/aat/300179869"
else:
    return ''
```

#### _MaterialComponentsURI_
From column: _Medium_
``` python
if getValue("Medium") != 'NULL':
    return "http://vocab.getty.edu/aat/300264237"
else:
    return ''
```

#### _MediumURI_
From column: _Medium_
``` python
if getValue("Medium"):
    return getValue("ObjectURI") + "/medium_text"
else:
    return ''
```

#### _DateBeginValid_
From column: _DateBegin_
``` python
if getValue("DateBegin") == 0:
    return ''
return "01-01-" + getValue("DateBegin")
```

#### _DateEndValid_
From column: _DateEnd_
``` python
if getValue("DateEnd") == 0:
    return ''
return "12-31-" + getValue("DateEnd")
```

#### _ProductionURI_
From column: _ObjectURI_
``` python
return getValue("ObjectURI") + "/production"
```

#### _ProductionTimeSpanURI_
From column: _Dated_
``` python
return getValue("ProductionURI") + "/timespan"
```

#### _DimensionsAAT_
From column: _Dimensions_
``` python
if getValue("Dimensions"):
    return "http://vocab.getty.edu/aat/300266036"
else:
    return ''
```

#### _DimensionsTextURI_
From column: _Dimensions_
``` python
if getValue("Dimensions"):
    return getValue("ObjectURI") + "/dimensions_text"
else:
    return ''
```

#### _AcknowledgementsURI_
From column: _CreditLine_
``` python
if getValue("CreditLine"):
    return "http://vocab.getty.edu/aat/300026687"
else:
    return ''
```

#### _CreditLineURI_
From column: _CreditLine_
``` python
if getValue("CreditLine"):
    return getValue("ObjectURI") + "/credit_line"
else:
    return ''
```


## Selections

## Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _AcknowledgementsURI_ | `uri` | `crm:E55_Type7`|
| _Classification_ | `rdfs:label` | `crm:E55_Type3`|
| _ClassificationEventURI_ | `uri` | `crm:E17_Type_Assignment1`|
| _ClassificationURI_ | `uri` | `crm:E55_Type3`|
| _CreditLine_ | `rdf:value` | `crm:E33_Linguistic_Object3`|
| _CreditLineURI_ | `uri` | `crm:E33_Linguistic_Object3`|
| _DateBeginValid_ | `crm:P82a_begin_of_the_begin` | `crm:E52_Time-Span1`|
| _DateEndValid_ | `crm:P82b_end_of_the_end` | `crm:E52_Time-Span1`|
| _Dated_ | `rdfs:label` | `crm:E52_Time-Span1`|
| _Dimensions_ | `rdf:value` | `crm:E33_Linguistic_Object2`|
| _DimensionsAAT_ | `uri` | `crm:E55_Type6`|
| _DimensionsTextURI_ | `uri` | `crm:E33_Linguistic_Object2`|
| _MaterialComponentsURI_ | `uri` | `crm:E55_Type5`|
| _Medium_ | `rdf:value` | `crm:E33_Linguistic_Object1`|
| _MediumURI_ | `uri` | `crm:E33_Linguistic_Object1`|
| _ObjectIDCopy_ | `rdf:value` | `crm:E42_Identifier1`|
| _ObjectIDURI_ | `uri` | `crm:E42_Identifier1`|
| _ObjectNumber_ | `rdfs:label` | `crm:E42_Identifier2`|
| _ObjectNumberCopy_ | `rdf:value` | `crm:E42_Identifier2`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _PreferredIDURI_ | `uri` | `crm:E42_Identifier2`|
| _PreferredTermsURI_ | `uri` | `crm:E55_Type2`|
| _ProductionTimeSpanURI_ | `uri` | `crm:E52_Time-Span1`|
| _ProductionURI_ | `uri` | `crm:E12_Production1`|
| _RepositoryTermsURI_ | `uri` | `crm:E55_Type1`|
| _VisualWorksURI_ | `uri` | `crm:E55_Type4`|


## Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E12_Production1` | `crm:P4_has_time-span` | `crm:E52_Time-Span1`|
| `crm:E17_Type_Assignment1` | `crm:P42_assigned` | `crm:E55_Type3`|
| `crm:E17_Type_Assignment1` | `crm:P21_had_general_purpose` | `crm:E55_Type4`|
| `crm:E22_Man-Made_Object1` | `crm:P108i_was_produced_by` | `crm:E12_Production1`|
| `crm:E22_Man-Made_Object1` | `crm:P41i_was_classified_by` | `crm:E17_Type_Assignment1`|
| `crm:E22_Man-Made_Object1` | `crm:P67i_is_referred_to_by` | `crm:E33_Linguistic_Object1`|
| `crm:E22_Man-Made_Object1` | `crm:P67i_is_referred_to_by` | `crm:E33_Linguistic_Object2`|
| `crm:E22_Man-Made_Object1` | `crm:P67i_is_referred_to_by` | `crm:E33_Linguistic_Object3`|
| `crm:E22_Man-Made_Object1` | `crm:P1_is_identified_by` | `crm:E42_Identifier1`|
| `crm:E22_Man-Made_Object1` | `crm:P1_is_identified_by` | `crm:E42_Identifier2`|
| `crm:E22_Man-Made_Object1` | `crm:P2_has_type` | `crm:E55_Type3`|
| `crm:E33_Linguistic_Object1` | `crm:P2_has_type` | `crm:E55_Type5`|
| `crm:E33_Linguistic_Object2` | `crm:P2_has_type` | `crm:E55_Type6`|
| `crm:E33_Linguistic_Object3` | `crm:P2_has_type` | `crm:E55_Type7`|
| `crm:E42_Identifier1` | `crm:P2_has_type` | `crm:E55_Type1`|
| `crm:E42_Identifier2` | `crm:P2_has_type` | `crm:E55_Type2`|
