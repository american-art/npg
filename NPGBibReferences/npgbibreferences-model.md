## npgbibreferences_Sheet1

### PyTransforms
#### _ReferenceURI_
From column: _ReferenceID_
>``` python
return "reference/" + getValue("ReferenceID")
```

#### _ReferenceTypeURI_
From column: _Format_
>``` python
return "reference_type/" + getValue("Format").lower().replace(' ','_')
```

#### _TitleURI_
From column: _Title_
>``` python
return "thesauri/title/" + getValue("Title").lower().replace(' ', '_')
```

#### _TitleTranslateType_
From column: _TitleURI_
>``` python
return "Not Translatable"
```

#### _TitleTranslateTypeURI_
From column: _TitleTranslateType_
>``` python
return "thesauri/title_translate_type/not_translatable"
```

#### _PrimaryTitleType_
From column: _TitleURI_
>``` python
return "Primary Title"
```

#### _PrimaryTitleTypeURI_
From column: _PrimaryTitleType_
>``` python
return "thesauri/title_type/primary_title"
```

#### _SubTitleURI_
From column: _SubTitle_
>``` python
if getValue("SubTitle"):
    return "thesauri/title/" + getValue("SubTitle").lower().replace(' ','_')
```

#### _SubTitleTranslateType_
From column: _SubTitleURI_
>``` python
if getValue("SubTitle"):
    return "Not Translatable"
else:
    return ''
```

#### _SubTitleTranslateTypeURI_
From column: _SubTitleTranslateType_
>``` python
if getValue("SubTitle"):
    return "thesauri/title_translate_type/not_translatable"
else:
    return ''
```

#### _SecondaryTitleType_
From column: _SubTitleURI_
>``` python
if getValue("SubTitle"):
    return "Secondary Title"
else:
    return ''
```

#### _SecondaryTitleTypeURI_
From column: _SecondaryTitleType_
>``` python
if getValue("SubTitle"):
    return thesauri/title_type/secondary_title
else:
    return ''
```

#### _PlacePublishedURI_
From column: _PlacePublished_
>``` python
if getValue("PlacePublished"):
    return "thesauri/place/" + getValue("PlacePublished").lower().replace(' ','_').replace(',','')
else:
    return ''
```

#### _BeginXSDDate_
From column: _YearPublished_
>``` python
if getValue("YearPublished") == 'NULL' or getValue("YearPublished") == '':
    return ''
else:
    return "01-01-{0}".format(getValue("YearPublished"))
```

#### _EndXSDDate_
From column: _BeginXSDDate_
>``` python
if getValue("YearPublished") == 'NULL' or getValue("YearPublished") == '':
    return ''
else:
    return "12-31-{0}".format(getValue("YearPublished"))
```

#### _YearPublishedURI_
From column: _YearPublished_
>``` python
if getValue("YearPublished") != 'NULL' and getValue("YearPublished") != '':
    return "thesauri/year/" + getValue("YearPublished")
else:
    return ''
```

#### _ProductionURI_
From column: _ReferenceURI_
>``` python
return getValue("ReferenceURI") + "/production"
```


### Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _Acquisition_ | `rdfs:label` | `crm:E55_Type3`|
| _AcquisitionURI_ | `uri` | `crm:E55_Type3`|
| _AltLabel_ | `rdfs:label` | `crm:E35_Title2`|
| _BeginDate_ | `crm:P82_at_some_time_within` | `crm:E52_Time-Span1`|
| _BeginXSDDate_ | `crm:P82a_begin_of_the_begin` | `crm:E52_Time-Span1`|
| _BirthURI_ | `uri` | `crm:E67_Birth1`|
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
| _EndXSDDate_ | `crm:P82b_end_of_the_end` | `crm:E52_Time-Span1`|
| _ExhTitle_ | `rdfs:label` | `crm:E41_Appellation1`|
| _ExhibitionURI_ | `uri` | `crm:E7_Activity1`|
| _ExhibitionUsageURI_ | `uri` | `crm:PC16_used_specific_object1`|
| _FirstName_ | `rdfs:label` | `crm:E82_Actor_Appellation3`|
| _FirstNameAppellationURI_ | `uri` | `crm:E82_Actor_Appellation3`|
| _FirstNameURI_ | `uri` | `crm:E41_Appellation1`|
| _Format_ | `rdfs:label` | `crm:E55_Type1`|
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
| _PageNumberURI_ | `uri` | `crm:E33_Linguistic_Object1`|
| _PageNumberValid_ | `rdfs:label` | `crm:E33_Linguistic_Object1`|
| _PlacePublished_ | `rdfs:label` | `crm:E44_Place_Appellation1`|
| _PlacePublishedURI_ | `uri` | `crm:E44_Place_Appellation1`|
| _PreferredLabel_ | `rdfs:label` | `crm:E35_Title1`|
| _PrimaryTitleType_ | `rdfs:label` | `crm:E55_Type3`|
| _PrimaryTitleTypeURI_ | `uri` | `crm:E55_Type3`|
| _PrimaryTitleURI_ | `uri` | `crm:E35_Title1`|
| _ProductionDateURI_ | `uri` | `crm:E52_Time-Span1`|
| _ProductionURI_ | `uri` | `crm:E12_Production1`|
| _ProductionURI_ | `uri` | `crm:E12_Production1`|
| _ReferenceTypeURI_ | `uri` | `crm:E55_Type1`|
| _ReferenceURI_ | `uri` | `crm:E31_Document1`|
| _ReferenceURI_ | `uri` | `crm:E31_Document1`|
| _RemarksValid_ | `crm:P3_has_note` | `crm:E31_Document1`|
| _SecondaryTitleType_ | `rdfs:label` | `crm:E55_Type4`|
| _SecondaryTitleTypeURI_ | `uri` | `crm:E55_Type4`|
| _SitterURI_ | `uri` | `crm:E21_Person1`|
| _SubTitle_ | `rdfs:label` | `crm:E35_Title2`|
| _SubTitleTranslateType_ | `rdfs:label` | `crm:E55_Type5`|
| _SubTitleTranslateTypeURI_ | `uri` | `crm:E55_Type5`|
| _SubTitleURI_ | `uri` | `crm:E35_Title2`|
| _Suffix_ | `rdfs:label` | `crm:E41_Appellation4`|
| _SuffixURI_ | `uri` | `crm:E41_Appellation4`|
| _TextEntry_ | `crm:P3_has_note` | `crm:E22_Man-Made_Object1`|
| _Title_ | `rdfs:label` | `crm:E35_Title1`|
| _TitleTranslateType_ | `rdfs:label` | `crm:E55_Type2`|
| _TitleTranslateType_ | `rdfs:label` | `crm:E55_Type2`|
| _TitleTranslateTypeURI_ | `uri` | `crm:E55_Type2`|
| _TitleURI_ | `uri` | `crm:E35_Title2`|
| _TitleURI_ | `uri` | `crm:E35_Title1`|
| _URL_ | `rdfs:label` | `crm:E51_Contact_Point1`|
| _YearPublishedURI_ | `uri` | `crm:E52_Time-Span1`|
| _urlURI_ | `uri` | `crm:E51_Contact_Point1`|


### Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E12_Production1` | `crm:P7_took_place_at` | `crm:E44_Place_Appellation1`|
| `crm:E12_Production1` | `crm:P4_has_time-span` | `crm:E52_Time-Span1`|
| `crm:E31_Document1` | `crm:P108i_was_produced_by` | `crm:E12_Production1`|
| `crm:E31_Document1` | `crm:P102_has_title` | `crm:E35_Title1`|
| `crm:E31_Document1` | `crm:P102_has_title` | `crm:E35_Title2`|
| `crm:E31_Document1` | `crm:P2_has_type` | `crm:E55_Type1`|
| `crm:E35_Title1` | `crm:P2_has_type` | `crm:E55_Type2`|
| `crm:E35_Title1` | `crm:P2_has_type` | `crm:E55_Type3`|
| `crm:E35_Title2` | `crm:P2_has_type` | `crm:E55_Type4`|
| `crm:E35_Title2` | `crm:P2_has_type` | `crm:E55_Type5`|
