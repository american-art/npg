## NPGDimsParsedUpdate2May_Sheet1

### PyTransforms
#### _ObjectURI_
From column: _ObjectID_
>``` python
return "object/" + getValue("ObjectID")
```

#### _ObjectTypeURI_
From column: _Element_
>``` python
return "thesauri/object_type/" + getValue("Element").lower().replace(' ','_')
```

#### _MeasurementTypeURI_
From column: _DimensionType_
>``` python
return "thesauri/measurement_type/" + getValue("DimensionType").lower().replace(' ','_')
```

#### _DimensionURI_
From column: _Dimension_
>``` python
return getValue("ObjectURI") + "/" + getValue("DimensionType").lower().replace(' ','_')
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
| _DateBeginValid_ | `crm:P82a_begin_of_the_begin` | `crm:E52_Time-Span1`|
| _DateEndValid_ | `crm:P82b_end_of_the_end` | `crm:E52_Time-Span1`|
| _Dated_ | `rdfs:label` | `crm:E52_Time-Span1`|
| _DeathDateURI_ | `uri` | `crm:E52_Time-Span2`|
| _DeathURI_ | `uri` | `crm:E69_Death1`|
| _Dimension_ | `rdfs:label` | `crm:E16_Measurement1`|
| _DimensionStringType_ | `rdfs:label` | `crm:E55_Type4`|
| _DimensionStringTypeURI_ | `uri` | `crm:E55_Type4`|
| _DimensionType_ | `rdfs:label` | `crm:E55_Type2`|
| _DimensionURI_ | `uri` | `crm:E16_Measurement1`|
| _DimensionURI_ | `uri` | `crm:E54_Dimension1`|
| _Dimensions_ | `crm:P3_has_note` | `crm:E54_Dimension1`|
| _DisplayName_ | `rdfs:label` | `crm:E41_Appellation5`|
| _DisplayNameURI_ | `uri` | `crm:E41_Appellation5`|
| _DisplayPersonInstitutionName_ | `rdfs:label` | `crm:E82_Actor_Appellation2`|
| _Element_ | `rdfs:label` | `crm:E55_Type1`|
| _EndDate_ | `crm:P82_at_some_time_within` | `crm:E52_Time-Span2`|
| _ExhTitle_ | `rdfs:label` | `crm:E41_Appellation1`|
| _ExhibitionURI_ | `uri` | `crm:E7_Activity1`|
| _ExhibitionUsageURI_ | `uri` | `crm:PC16_used_specific_object1`|
| _FirstName_ | `rdfs:label` | `crm:E82_Actor_Appellation3`|
| _FirstNameAppellationURI_ | `uri` | `crm:E82_Actor_Appellation3`|
| _FirstNameURI_ | `uri` | `crm:E41_Appellation1`|
| _LastName_ | `rdfs:label` | `crm:E82_Actor_Appellation4`|
| _LastName_ | `rdfs:label` | `crm:E41_Appellation2`|
| _LastNameAppellationURI_ | `uri` | `crm:E82_Actor_Appellation4`|
| _LastNameURI_ | `uri` | `crm:E41_Appellation2`|
| _MeasurementTypeURI_ | `uri` | `crm:E55_Type2`|
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
| _ObjectTypeURI_ | `uri` | `crm:E55_Type1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _PageNumberURI_ | `uri` | `crm:E33_Linguistic_Object1`|
| _PageNumberValid_ | `rdfs:label` | `crm:E33_Linguistic_Object1`|
| _PlacePublished_ | `rdfs:label` | `crm:E44_Place_Appellation1`|
| _PlacePublishedURI_ | `uri` | `crm:E44_Place_Appellation1`|
| _PreferredLabel_ | `rdfs:label` | `crm:E35_Title1`|
| _PrimaryTitleURI_ | `uri` | `crm:E35_Title1`|
| _ProductionDateURI_ | `uri` | `crm:E52_Time-Span1`|
| _ProductionURI_ | `uri` | `crm:E12_Production1`|
| _Provenance_ | `crm:P3_has_note` | `crm:E10_Transfer_of_Custody1`|
| _ProvenanceURI_ | `uri` | `crm:E10_Transfer_of_Custody1`|
| _ReferenceURI_ | `uri` | `crm:E31_Document1`|
| _RemarksValid_ | `crm:P3_has_note` | `crm:E31_Document1`|
| _SitterURI_ | `uri` | `crm:E21_Person1`|
| _SubTitleTranslateType_ | `rdfs:label` | `crm:E55_Type5`|
| _SubTitleTranslateTypeURI_ | `uri` | `crm:E55_Type5`|
| _Suffix_ | `rdfs:label` | `crm:E41_Appellation4`|
| _SuffixURI_ | `uri` | `crm:E41_Appellation4`|
| _TextEntry_ | `crm:P3_has_note` | `crm:E22_Man-Made_Object1`|
| _TitleTranslateType_ | `rdfs:label` | `crm:E55_Type2`|
| _TitleURI_ | `uri` | `crm:E35_Title2`|
| _URL_ | `rdfs:label` | `crm:E51_Contact_Point1`|
| _WebImageURI_ | `uri` | `crm:E38_Image1`|
| _urlURI_ | `uri` | `crm:E51_Contact_Point1`|


### Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E16_Measurement1` | `crm:P2_has_type` | `crm:E55_Type2`|
| `crm:E22_Man-Made_Object1` | `crm:P39i_was_measured_by` | `crm:E16_Measurement1`|
| `crm:E22_Man-Made_Object1` | `crm:P2_has_type` | `crm:E55_Type1`|
