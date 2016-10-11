## NPGObjects2_Sheet1

### PyTransforms
#### _ObjectURI_
From column: _ObjectID_
>``` python
return "object/"+getValue("ObjectID")
```

#### _ClassificationURI_
From column: _Classification_
>``` python
if getValue("Classification"):
    return "thesauri/classification/"+getValue("Classification").lower().replace(' ', '_')
else:
    return ""
```

#### _ProductionURI_
From column: _ClassificationURI_
>``` python
return getValue("ObjectURI") + "/production"

```

#### _DimensionURI_
From column: _Dimensions_
>``` python
return getValue("ObjectURI")+"/dimensions"
```

#### _ProductionDateURI_
From column: _DateEnd_
>``` python
return getValue("ObjectURI")+"/production/date"

```

#### _CreditLineURI_
From column: _CreditLine_
>``` python
if getValue("CreditLine"):
    return getValue("ObjectURI") + "/credit_line"
else:
    return ''
```

#### _CreditLineStringType_
From column: _CreditLineURI_
>``` python
if getValue("CreditLine"):
    return "Credit Line Statement"
else:
    return ""
```

#### _CreditLineStringTypeURI_
From column: _CreditLineStringType_
>``` python
if getValue("CreditLineStringType"):
    return "thesauri/credit_line_string_type/credit_line_statement"
else:
    return ''
```

#### _DateBeginValid_
From column: _DateBegin_
>``` python
if getValue("DateBegin") == '0':
    return ""
else:
    return getValue("DateBegin")
```

#### _DateEndValid_
From column: _DateEnd_
>``` python
if getValue("DateEnd") == '0':
    return ""
else:
    return getValue("DateEnd")
```

#### _MediumURI_
From column: _Medium_
>``` python
if getValue("Medium"):
    return getValue("ObjectURI")+"/medium"
```

#### _ObjectNumberURI_
From column: _ObjectNumber_
>``` python
return getValue("ObjectURI") + "/object_number"
```

#### _DimensionStringType_
From column: _Dimensions_
>``` python
if getValue("Dimensions"):
    return "Dimension Statement"
else:
    return ''
```

#### _DimensionStringTypeURI_
From column: _DimensionStringType_
>``` python
if getValue("DimensionStringType"):
    return "thesauri/dimension_string_type/dimension_statement"
else:
    return ''
```


### Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _Acquisition_ | `rdfs:label` | `crm:E55_Type3`|
| _AcquisitionURI_ | `uri` | `crm:E55_Type3`|
| _AltLabel_ | `rdfs:label` | `crm:E35_Title2`|
| _Classification_ | `rdfs:label` | `crm:E55_Type1`|
| _Classification_ | `rdfs:label` | `crm:E55_Type1`|
| _ClassificationURI_ | `uri` | `crm:E55_Type1`|
| _ClassificationURI_ | `uri` | `crm:E55_Type1`|
| _CreditLineStringType_ | `rdfs:label` | `crm:E55_Type3`|
| _CreditLineStringTypeURI_ | `uri` | `crm:E55_Type3`|
| _DateBeginValid_ | `crm:P82a_begin_of_the_begin` | `crm:E52_Time-Span1`|
| _DateBeginValid_ | `crm:P82a_begin_of_the_begin` | `crm:E52_Time-Span1`|
| _DateEndValid_ | `crm:P82b_end_of_the_end` | `crm:E52_Time-Span1`|
| _DateEndValid_ | `crm:P82b_end_of_the_end` | `crm:E52_Time-Span1`|
| _Dated_ | `rdfs:label` | `crm:E52_Time-Span1`|
| _Dated_ | `rdfs:label` | `crm:E52_Time-Span1`|
| _DimensionStringType_ | `rdfs:label` | `crm:E55_Type2`|
| _DimensionStringType_ | `rdfs:label` | `crm:E55_Type4`|
| _DimensionStringTypeURI_ | `uri` | `crm:E55_Type2`|
| _DimensionStringTypeURI_ | `uri` | `crm:E55_Type4`|
| _DimensionURI_ | `uri` | `crm:E54_Dimension1`|
| _Dimensions_ | `crm:P3_has_note` | `crm:E54_Dimension1`|
| _ExhTitle_ | `rdfs:label` | `crm:E41_Appellation1`|
| _ExhibitionURI_ | `uri` | `crm:E7_Activity1`|
| _ExhibitionUsageURI_ | `uri` | `crm:PC16_used_specific_object1`|
| _Medium_ | `crm:P3_has_note` | `crm:E55_Type4`|
| _Medium_ | `crm:P3_has_note` | `crm:E55_Type2`|
| _Medium_ | `crm:P3_has_note` | `crm:E57_Material1`|
| _MediumURI_ | `uri` | `crm:E55_Type4`|
| _MediumURI_ | `uri` | `crm:E57_Material1`|
| _MediumURI_ | `uri` | `crm:E55_Type2`|
| _ObjectNumber_ | `rdfs:label` | `crm:E42_Identifier1`|
| _ObjectNumber_ | `rdfs:label` | `crm:E42_Identifier1`|
| _ObjectNumberURI_ | `uri` | `crm:E42_Identifier1`|
| _ObjectNumberURI_ | `uri` | `crm:E42_Identifier1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _PreferredLabel_ | `rdfs:label` | `crm:E35_Title1`|
| _PrimaryTitleURI_ | `uri` | `crm:E35_Title1`|
| _ProductionDateURI_ | `uri` | `crm:E52_Time-Span1`|
| _ProductionDateURI_ | `uri` | `crm:E52_Time-Span1`|
| _ProductionURI_ | `uri` | `crm:E12_Production1`|
| _ProductionURI_ | `uri` | `crm:E12_Production1`|
| _TitleTranslateType_ | `rdfs:label` | `crm:E55_Type2`|
| _TitleURI_ | `uri` | `crm:E35_Title2`|


### Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E12_Production1` | `crm:P4_has_time-span` | `crm:E52_Time-Span1`|
| `crm:E22_Man-Made_Object1` | `crm:P108i_was_produced_by` | `crm:E12_Production1`|
| `crm:E22_Man-Made_Object1` | `crm:P48_has_preferred_identifier` | `crm:E42_Identifier1`|
| `crm:E22_Man-Made_Object1` | `crm:P2_has_type` | `crm:E55_Type1`|
| `crm:E22_Man-Made_Object1` | `crm:P3.1_has_type` | `crm:E55_Type2`|
| `crm:E22_Man-Made_Object1` | `crm:P3.1_has_type` | `crm:E55_Type3`|
| `crm:E22_Man-Made_Object1` | `crm:P2_has_type` | `crm:E55_Type4`|
