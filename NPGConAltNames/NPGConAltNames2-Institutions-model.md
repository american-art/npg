## NPGConAltNames2_Sheet1

### PyTransforms
#### _ConstituentURI_
From column: _ConstituentID_
>``` python
return "person/" + getValue("ConstituentID")
```

#### _InstitutionURI_
From column: _Institution_
>``` python
if getValue("Institution") != 'NULL':
    return "thesauri/institution_name/" + getValue("Institution").lower().replace(' ', '_')
else:
    return ''
```

#### _DisplayNameURI_
From column: _DisplayName_
>``` python
if getValue("DisplayName") != 'NULL' and getValue("Institution") != 'NULL':
    return "thesauri/display_name/" + getValue("DisplayName").lower().replace(' ', '_')
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
| _Classification_ | `rdfs:label` | `crm:E55_Type1`|
| _ClassificationURI_ | `uri` | `crm:E55_Type1`|
| _ConstituentURI_ | `uri` | `crm:E39_Actor1`|
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
| _DisplayName_ | `rdfs:label` | `crm:E41_Appellation2`|
| _DisplayName_ | `rdfs:label` | `crm:E41_Appellation5`|
| _DisplayNameURI_ | `uri` | `crm:E41_Appellation2`|
| _DisplayNameURI_ | `uri` | `crm:E41_Appellation5`|
| _DisplayPersonInstitutionName_ | `rdfs:label` | `crm:E82_Actor_Appellation2`|
| _EndDate_ | `crm:P82_at_some_time_within` | `crm:E52_Time-Span2`|
| _ExhTitle_ | `rdfs:label` | `crm:E41_Appellation1`|
| _ExhibitionURI_ | `uri` | `crm:E7_Activity1`|
| _ExhibitionUsageURI_ | `uri` | `crm:PC16_used_specific_object1`|
| _FirstName_ | `rdfs:label` | `crm:E82_Actor_Appellation3`|
| _FirstNameAppellationURI_ | `uri` | `crm:E82_Actor_Appellation3`|
| _FirstNameURI_ | `uri` | `crm:E41_Appellation1`|
| _Institution_ | `rdfs:label` | `crm:E41_Appellation1`|
| _InstitutionURI_ | `uri` | `crm:E41_Appellation1`|
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
| _PreferredLabel_ | `rdfs:label` | `crm:E35_Title1`|
| _PrimaryTitleURI_ | `uri` | `crm:E35_Title1`|
| _ProductionDateURI_ | `uri` | `crm:E52_Time-Span1`|
| _ProductionURI_ | `uri` | `crm:E12_Production1`|
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
| `crm:E39_Actor1` | `crm:P1_is_identified_by` | `crm:E41_Appellation2`|
| `crm:E41_Appellation2` | `crm:P1_is_identified_by` | `crm:E41_Appellation1`|
