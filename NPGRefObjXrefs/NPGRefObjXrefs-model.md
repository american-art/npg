## NPGRefObjXrefs_Sheet1

### PyTransforms
#### _ObjectURI_
From column: _ObjectID_
>``` python
return "object/" + getValue("ObjectID")
```

#### _ReferenceURI_
From column: _ReferenceID_
>``` python
return "reference/" + getValue("ReferenceID")
```

#### _RemarksValid_
From column: _Remarks_
>``` python
if getValue("Remarks") != 'NULL':
    return getValue("Remarks")
else:
    return ''
```

#### _PageNumberValid_
From column: _PageNumber_
>``` python
if getValue("PageNumber") != 'NULL':
    return getValue("PageNumber")
else:
    return ''
```

#### _PageNumberURI_
From column: _PageNumberValid_
>``` python
if getValue("PageNumber") != 'NULL':
    return getValue("ReferenceURI") + "/page/" + getValue("PageNumber")
else:
    return ''
```

#### _CatalogueNumberValid_
From column: _CatalogueNumber_
>``` python
if getValue("CatalogueNumber") != 'NULL':
    return getValue("CatalogueNumber")
else:
    return ''
```

#### _CatalogueNumberURI_
From column: _CatalogueNumberValid_
>``` python
if getValue("CatalogueNumber") != 'NULL':
    return getValue("ReferenceURI") + "/catalogue_number/" + getValue("CatalogueNumber")
else:
    return ''
```

#### _FigureNumberValid_
From column: _FigureNumber_
>``` python
if getValue("FigureNumber") != 'NULL':
    return getValue("FigureNumber")
else:
    return ''
```

#### _FigureNumberURI_
From column: _FigureNumberValid_
>``` python
if getValue("FigureNumber") != 'NULL':
    return getValue("ReferenceURI") + "/catalogue_number/" + getValue("FigureNumber")
else:
    return ''
```


### Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _Acquisition_ | `rdfs:label` | `crm:E55_Type3`|
| _AcquisitionURI_ | `uri` | `crm:E55_Type3`|
| _AltLabel_ | `rdfs:label` | `crm:E35_Title2`|
| _BeginDate_ | `crm:P82_at_some_time_within` | `crm:E52_Time-Span1`|
| _BirthURI_ | `uri` | `crm:E67_Birth1`|
| _CatalogueNumberURI_ | `uri` | `crm:E41_Appellation1`|
| _CatalogueNumberValid_ | `rdfs:label` | `crm:E41_Appellation1`|
| _Classification_ | `rdfs:label` | `crm:E55_Type1`|
| _ClassificationURI_ | `uri` | `crm:E55_Type1`|
| _ConstituentURI_ | `uri` | `crm:E39_Actor1`|
| _DateBeginValid_ | `crm:P82a_begin_of_the_begin` | `crm:E52_Time-Span1`|
| _DateEndValid_ | `crm:P82b_end_of_the_end` | `crm:E52_Time-Span1`|
| _Dated_ | `rdfs:label` | `crm:E52_Time-Span1`|
| _DeathDateURI_ | `uri` | `crm:E52_Time-Span2`|
| _DeathURI_ | `uri` | `crm:E69_Death1`|
| _DimensionStringType_ | `rdfs:label` | `crm:E55_Type4`|
| _DimensionStringTypeURI_ | `uri` | `crm:E55_Type4`|
| _DimensionURI_ | `uri` | `crm:E54_Dimension1`|
| _Dimensions_ | `crm:P3_has_note` | `crm:E54_Dimension1`|
| _DisplayName_ | `rdfs:label` | `crm:E41_Appellation5`|
| _DisplayNameURI_ | `uri` | `crm:E41_Appellation5`|
| _DisplayPersonInstitutionName_ | `rdfs:label` | `crm:E82_Actor_Appellation2`|
| _EndDate_ | `crm:P82_at_some_time_within` | `crm:E52_Time-Span2`|
| _ExhTitle_ | `rdfs:label` | `crm:E41_Appellation1`|
| _ExhibitionURI_ | `uri` | `crm:E7_Activity1`|
| _ExhibitionUsageURI_ | `uri` | `crm:PC16_used_specific_object1`|
| _FigureNumberURI_ | `uri` | `crm:E41_Appellation2`|
| _FigureNumberValid_ | `rdfs:label` | `crm:E41_Appellation2`|
| _FirstName_ | `rdfs:label` | `crm:E82_Actor_Appellation3`|
| _FirstNameAppellationURI_ | `uri` | `crm:E82_Actor_Appellation3`|
| _FirstNameURI_ | `uri` | `crm:E41_Appellation1`|
| _LastName_ | `rdfs:label` | `crm:E82_Actor_Appellation4`|
| _LastName_ | `rdfs:label` | `crm:E41_Appellation2`|
| _LastNameAppellationURI_ | `uri` | `crm:E82_Actor_Appellation4`|
| _LastNameURI_ | `uri` | `crm:E41_Appellation2`|
| _Medium_ | `crm:P3_has_note` | `crm:E55_Type2`|
| _Medium_ | `crm:P3_has_note` | `crm:E57_Material1`|
| _MediumURI_ | `uri` | `crm:E57_Material1`|
| _MediumURI_ | `uri` | `crm:E55_Type2`|
| _MiddleName_ | `rdfs:label` | `crm:E82_Actor_Appellation1`|
| _MiddleName_ | `rdfs:label` | `crm:E41_Appellation3`|
| _MiddleNameAppellationURI_ | `uri` | `crm:E82_Actor_Appellation1`|
| _MiddleNameURI_ | `uri` | `crm:E41_Appellation3`|
| _ObjectNumber_ | `rdfs:label` | `crm:E42_Identifier1`|
| _ObjectNumberURI_ | `uri` | `crm:E42_Identifier1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _PageNumberURI_ | `uri` | `crm:E41_Appellation3`|
| _PageNumberValid_ | `rdfs:label` | `crm:E41_Appellation3`|
| _PreferredLabel_ | `rdfs:label` | `crm:E35_Title1`|
| _PrimaryTitleURI_ | `uri` | `crm:E35_Title1`|
| _ProductionDateURI_ | `uri` | `crm:E52_Time-Span1`|
| _ProductionURI_ | `uri` | `crm:E12_Production1`|
| _ReferenceURI_ | `uri` | `crm:E31_Document1`|
| _RemarksValid_ | `crm:P3_has_note` | `crm:E31_Document1`|
| _SitterURI_ | `uri` | `crm:E21_Person1`|
| _Suffix_ | `rdfs:label` | `crm:E41_Appellation4`|
| _SuffixURI_ | `uri` | `crm:E41_Appellation4`|
| _TextEntry_ | `crm:P3_has_note` | `crm:E22_Man-Made_Object1`|
| _TitleTranslateType_ | `rdfs:label` | `crm:E55_Type2`|
| _TitleURI_ | `uri` | `crm:E35_Title2`|
| _URL_ | `rdfs:label` | `crm:E51_Contact_Point1`|
| _urlURI_ | `uri` | `crm:E51_Contact_Point1`|


### Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E31_Document1` | `crm:P70_documents` | `crm:E22_Man-Made_Object1`|
| `crm:E31_Document1` | `crm:P106_is_composed_of` | `crm:E41_Appellation1`|
| `crm:E31_Document1` | `crm:P106_is_composed_of` | `crm:E41_Appellation2`|
| `crm:E31_Document1` | `crm:P106_is_composed_of` | `crm:E41_Appellation3`|
