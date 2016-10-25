## NPGExhibitions2_Sheet1

### PyTransforms
#### _ExhibitionURI_
From column: _ExhibitionID_
>``` python
return "exhibition/"+getValue("ExhibitionID")
```

#### _ActivityType_
From column: _ExhTitle_
>``` python
if getValue("ExhTitle"):
    return "Exhibit"
else:
    return ''
```

#### _ActivityTypeURI_
From column: _ActivityType_
>``` python
if getValue("ActivityType"):
    return "thesauri/activity_type/exhibit"
else:
    return ''
```

#### _BeginISODateXSDFormat_
From column: _BeginISODate_
>``` python
if getValue("BeginISODate") == 'NULL':
    return ''
else:
    date = getValue("BeginISODate").split('/')
    date = [int(d) for d in date]
    if len(date) == 3:
        if date[2] < 17:
            date[2] += 2000
        else:
            date[2] += 1900
        if date[0] < 10:
            date[0] = "0{0}".format(date[0])
        if date[1] < 10:
            date[1] = "0{0}".format(date[1])
        return "{0}-{1}-{2}".format(date[2], date[0], date[1])
    else:
        return "{0}-01".format(getValue("BeginISODate"))
```

#### _ExhibitionUsageURI_
From column: _ExhibitionURI_
>``` python
return "exhibition/"+getValue("ExhibitionID") + "/usage"
```

#### _EndISODateXSDFormat_
From column: _EndISODate_
>``` python
if getValue("EndISODate") == 'NULL':
    return ''
else:
    date = getValue("EndISODate").split('/')
    date = [int(d) for d in date]
    if len(date) == 3:
        if date[2] < 17:
            date[2] += 2000
        else:
            date[2] += 1900
        if date[0] < 10:
            date[0] = "0{0}".format(date[0])
        if date[1] < 10:
            date[1] = "0{0}".format(date[1])
        return "{0}-{1}-{2}".format(date[2], date[0], date[1])
    else:
        return "{0}-01".format(getValue("EndISODate"))
```


### Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _Acquisition_ | `rdfs:label` | `crm:E55_Type3`|
| _AcquisitionURI_ | `uri` | `crm:E55_Type3`|
| _ActivityType_ | `rdfs:label` | `crm:E55_Type1`|
| _ActivityTypeURI_ | `uri` | `crm:E55_Type1`|
| _AltLabel_ | `rdfs:label` | `crm:E35_Title2`|
| _BeginISODateURI_ | `crm:P82a_begin_of_the_begin` | `crm:E52_Time-Span1`|
| _Classification_ | `rdfs:label` | `crm:E55_Type1`|
| _ClassificationURI_ | `uri` | `crm:E55_Type1`|
| _DateBeginValid_ | `crm:P82a_begin_of_the_begin` | `crm:E52_Time-Span1`|
| _DateEndValid_ | `crm:P82b_end_of_the_end` | `crm:E52_Time-Span1`|
| _Dated_ | `rdfs:label` | `crm:E52_Time-Span1`|
| _DimensionStringType_ | `rdfs:label` | `crm:E55_Type4`|
| _DimensionStringTypeURI_ | `uri` | `crm:E55_Type4`|
| _DimensionURI_ | `uri` | `crm:E54_Dimension1`|
| _Dimensions_ | `crm:P3_has_note` | `crm:E54_Dimension1`|
| _EndISODateXSDFormat_ | `crm:P82b_end_of_the_end` | `crm:E52_Time-Span1`|
| _ExhTitle_ | `rdfs:label` | `crm:E41_Appellation1`|
| _ExhTitle_ | `rdfs:label` | `crm:E41_Appellation1`|
| _ExhibitionURI_ | `uri` | `crm:E7_Activity1`|
| _ExhibitionURI_ | `uri` | `crm:E7_Activity1`|
| _ExhibitionUsageURI_ | `uri` | `crm:PC16_used_specific_object1`|
| _ExhibitionUsageURI_ | `uri` | `crm:PC16_used_specific_object1`|
| _Medium_ | `crm:P3_has_note` | `crm:E55_Type2`|
| _Medium_ | `crm:P3_has_note` | `crm:E57_Material1`|
| _MediumURI_ | `uri` | `crm:E57_Material1`|
| _MediumURI_ | `uri` | `crm:E55_Type2`|
| _ObjectNumber_ | `rdfs:label` | `crm:E42_Identifier1`|
| _ObjectNumberURI_ | `uri` | `crm:E42_Identifier1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _PreferredLabel_ | `rdfs:label` | `crm:E35_Title1`|
| _PrimaryTitleURI_ | `uri` | `crm:E35_Title1`|
| _ProductionDateURI_ | `uri` | `crm:E52_Time-Span1`|
| _ProductionURI_ | `uri` | `crm:E12_Production1`|
| _TitleTranslateType_ | `rdfs:label` | `crm:E55_Type2`|
| _TitleURI_ | `uri` | `crm:E35_Title2`|


### Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E7_Activity1` | `crm:P1_is_identified_by` | `crm:E41_Appellation1`|
| `crm:E7_Activity1` | `crm:P4_has_time-span` | `crm:E52_Time-Span1`|
| `crm:PC16_used_specific_object1` | `crm:P16.1_mode_of_use` | `crm:E55_Type1`|
| `crm:PC16_used_specific_object1` | `crm:P02_has_range` | `crm:E7_Activity1`|
