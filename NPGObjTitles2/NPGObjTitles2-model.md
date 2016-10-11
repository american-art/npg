## NPGObjTitles2_Sheet1

### PyTransforms
#### _ObjectURI_
From column: _ObjectID_
>``` python
return "object/"+getValue("ObjectID")
```

#### _SecondaryTitleURI_
From column: _Title_
>``` python
if getValue("SecondaryTitle"):
    return "thesauri/title/" + getValue("Title").lower().replace(' ', '_')
else:
    return ''
```

#### _PrimaryTitle_
From column: _DisplayOrder_
>``` python
if getValue("DisplayOrder") == '1':
    return getValue("Title")
```

#### _SecondaryTitle_
From column: _PrimaryTitle_
>``` python
if getValue("DisplayOrder") != '1':
    return getValue("Title")
```

#### _SecondaryTitleTranslateType_
From column: _Title_
>``` python
if getValue("Title"):
    return "Not Translatable"
else:
    return ''
```

#### _SecondaryTitleTranslateTypeURI_
From column: _SecondaryTitleTranslateType_
>``` python
if getValue("Title"):
    return "thesauri/title_translate_type/not_translatable"
else:
    return ''
```

#### _SecondaryTitleType_
From column: _SecondaryTitle_
>``` python
if getValue("SecondaryTitle"):
    return "Secondary Title"
else:
    return ''
```

#### _SecondaryTitleTypeURI_
From column: _SecondaryTitleType_
>``` python
if getValue("SecondaryTitleType"):
    return "thesauri/title_type/secondary_title"
else:
    return ''
```

#### _PrimaryTitleURI_
From column: _PrimaryTitle_
>``` python
if getValue("PrimaryTitle"):
    return "thesauri/title/" + getValue("Title").lower().replace(' ', '_')
else:
    return ''
```

#### _PrimaryTitleType_
From column: _PrimaryTitle_
>``` python
if getValue("PrimaryTitle"):
    return "Primary Title"
else:
    return ''
```

#### _PrimaryTitleTypeURI_
From column: _PrimaryTitleType_
>``` python
if getValue("PrimaryTitleType"):
    return "thesauri/title_type/primary_title"
else:
    return ''
```

#### _PrimaryTitleTranslationType_
From column: _PrimaryTitle_
>``` python
if getValue("PrimaryTitle"):
    return "Not Translatable"
else:
    return ''
```

#### _PrimaryTitleTranslationTypeURI_
From column: _PrimaryTitleTranslationType_
>``` python
if getValue("PrimaryTitle"):
    return "thesauri/title_translate_type/not_translatable"
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
| _ClassificationURI_ | `uri` | `crm:E55_Type1`|
| _DateBeginValid_ | `crm:P82a_begin_of_the_begin` | `crm:E52_Time-Span1`|
| _DateEndValid_ | `crm:P82b_end_of_the_end` | `crm:E52_Time-Span1`|
| _Dated_ | `rdfs:label` | `crm:E52_Time-Span1`|
| _DimensionStringType_ | `rdfs:label` | `crm:E55_Type4`|
| _DimensionStringTypeURI_ | `uri` | `crm:E55_Type4`|
| _DimensionURI_ | `uri` | `crm:E54_Dimension1`|
| _Dimensions_ | `crm:P3_has_note` | `crm:E54_Dimension1`|
| _ExhTitle_ | `rdfs:label` | `crm:E41_Appellation1`|
| _ExhibitionURI_ | `uri` | `crm:E7_Activity1`|
| _ExhibitionUsageURI_ | `uri` | `crm:PC16_used_specific_object1`|
| _Medium_ | `crm:P3_has_note` | `crm:E55_Type2`|
| _Medium_ | `crm:P3_has_note` | `crm:E57_Material1`|
| _MediumURI_ | `uri` | `crm:E57_Material1`|
| _MediumURI_ | `uri` | `crm:E55_Type2`|
| _ObjectNumber_ | `rdfs:label` | `crm:E42_Identifier1`|
| _ObjectNumberURI_ | `uri` | `crm:E42_Identifier1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _PreferredLabel_ | `rdfs:label` | `crm:E35_Title1`|
| _PrimaryTitle_ | `rdfs:label` | `crm:E35_Title1`|
| _PrimaryTitleTranslationType_ | `rdfs:label` | `crm:E55_Type2`|
| _PrimaryTitleTranslationTypeURI_ | `uri` | `crm:E55_Type2`|
| _PrimaryTitleType_ | `rdfs:label` | `crm:E55_Type1`|
| _PrimaryTitleTypeURI_ | `uri` | `crm:E55_Type1`|
| _PrimaryTitleURI_ | `uri` | `crm:E35_Title1`|
| _PrimaryTitleURI_ | `uri` | `crm:E35_Title1`|
| _ProductionDateURI_ | `uri` | `crm:E52_Time-Span1`|
| _ProductionURI_ | `uri` | `crm:E12_Production1`|
| _SecondaryTitle_ | `rdfs:label` | `crm:E35_Title2`|
| _SecondaryTitleTranslateType_ | `rdfs:label` | `crm:E55_Type4`|
| _SecondaryTitleTranslateTypeURI_ | `uri` | `crm:E55_Type4`|
| _SecondaryTitleType_ | `rdfs:label` | `crm:E55_Type3`|
| _SecondaryTitleTypeURI_ | `uri` | `crm:E55_Type3`|
| _SecondaryTitleURI_ | `uri` | `crm:E35_Title2`|
| _TitleTranslateType_ | `rdfs:label` | `crm:E55_Type2`|
| _TitleURI_ | `uri` | `crm:E35_Title2`|


### Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E22_Man-Made_Object1` | `crm:P102_has_title` | `crm:E35_Title1`|
| `crm:E22_Man-Made_Object1` | `crm:P102_has_title` | `crm:E35_Title2`|
| `crm:E35_Title1` | `crm:P2_has_type` | `crm:E55_Type1`|
| `crm:E35_Title1` | `crm:P2_has_type` | `crm:E55_Type2`|
| `crm:E35_Title2` | `crm:P2_has_type` | `crm:E55_Type3`|
| `crm:E35_Title2` | `crm:P2_has_type` | `crm:E55_Type4`|
