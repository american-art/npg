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
return UM.uri_from_fields("thesauri/title/", getValue("Title"))
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
    return UM.uri_from_fields("thesauri/title/", getValue("SubTitle"))
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
| _BeginDate_ | `crm:P82_at_some_time_within` | `crm:E52_Time-Span2`|
| _BeginXSDDate_ | `crm:P82a_begin_of_the_begin` | `crm:E52_Time-Span1`|
| _BirthDateURI_ | `uri` | `crm:E52_Time-Span2`|
| _BirthURI_ | `uri` | `crm:E67_Birth1`|
| _ConstituentURI_ | `uri` | `crm:E39_Actor1`|
| _DeathDateURI_ | `uri` | `crm:E52_Time-Span1`|
| _DeathURI_ | `uri` | `crm:E69_Death1`|
| _DisplayName_ | `rdfs:label` | `crm:E41_Appellation5`|
| _DisplayNameURI_ | `uri` | `crm:E41_Appellation5`|
| _DisplayNameURI_ | `uri` | `crm:E41_Appellation4`|
| _DisplayPersonInstitutionName_ | `rdfs:label` | `crm:E41_Appellation4`|
| _EndDate_ | `crm:P82_at_some_time_within` | `crm:E52_Time-Span1`|
| _EndXSDDate_ | `crm:P82b_end_of_the_end` | `crm:E52_Time-Span1`|
| _FirstName_ | `rdfs:label` | `crm:E41_Appellation3`|
| _FirstNameAppellationURI_ | `uri` | `crm:E41_Appellation3`|
| _FirstNameURI_ | `uri` | `crm:E55_Type3`|
| _Format_ | `rdfs:label` | `crm:E55_Type1`|
| _LastName_ | `rdfs:label` | `crm:E41_Appellation1`|
| _LastNameAppellationURI_ | `uri` | `crm:E41_Appellation1`|
| _LastNameURI_ | `uri` | `crm:E55_Type1`|
| _MiddleName_ | `rdfs:label` | `crm:E41_Appellation2`|
| _MiddleNameAppellationURI_ | `uri` | `crm:E41_Appellation2`|
| _MiddleNameURI_ | `uri` | `crm:E55_Type2`|
| _NameType_ | `rdfs:label` | `crm:E55_Type3`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _PlacePublished_ | `rdfs:label` | `crm:E44_Place_Appellation1`|
| _PlacePublishedURI_ | `uri` | `crm:E44_Place_Appellation1`|
| _PrimaryTitle_ | `rdfs:label` | `crm:E35_Title2`|
| _PrimaryTitleTranslationType_ | `rdfs:label` | `crm:E55_Type2`|
| _PrimaryTitleType_ | `rdfs:label` | `crm:E55_Type3`|
| _PrimaryTitleTypeURI_ | `uri` | `crm:E55_Type3`|
| _PrimaryTitleURI_ | `uri` | `crm:E35_Title2`|
| _ProductionURI_ | `uri` | `crm:E12_Production1`|
| _ReferenceTypeURI_ | `uri` | `crm:E55_Type1`|
| _ReferenceURI_ | `uri` | `crm:E31_Document1`|
| _SecondaryTitle_ | `rdfs:label` | `crm:E35_Title1`|
| _SecondaryTitleTranslateType_ | `rdfs:label` | `crm:E55_Type4`|
| _SecondaryTitleTranslateTypeURI_ | `uri` | `crm:E55_Type4`|
| _SecondaryTitleType_ | `rdfs:label` | `crm:E55_Type4`|
| _SecondaryTitleType_ | `rdfs:label` | `crm:E55_Type1`|
| _SecondaryTitleTypeURI_ | `uri` | `crm:E55_Type4`|
| _SecondaryTitleURI_ | `uri` | `crm:E35_Title1`|
| _SubTitle_ | `rdfs:label` | `crm:E35_Title2`|
| _SubTitleTranslateType_ | `rdfs:label` | `crm:E55_Type5`|
| _SubTitleTranslateTypeURI_ | `uri` | `crm:E55_Type5`|
| _SubTitleURI_ | `uri` | `crm:E35_Title2`|
| _Title_ | `rdfs:label` | `crm:E35_Title1`|
| _TitleTranslateType_ | `rdfs:label` | `crm:E55_Type2`|
| _TitleTranslateTypeURI_ | `uri` | `crm:E55_Type2`|
| _TitleURI_ | `uri` | `crm:E35_Title1`|
| _YearPublishedURI_ | `uri` | `crm:E52_Time-Span1`|


### Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E12_Production1` | `crm:P7_took_place_at` | `crm:E44_Place_Appellation1`|
| `crm:E12_Production1` | `crm:P4_has_time-span` | `crm:E52_Time-Span1`|
| `crm:E31_Document1` | `crm:P108i_was_produced_by` | `crm:E12_Production1`|
| `crm:E31_Document1` | `crm:P1_is_identified_by` | `crm:E41_Appellation1`|
| `crm:E31_Document1` | `crm:P2_has_type` | `crm:E55_Type1`|
| `crm:E35_Title1` | `crm:P2_has_type` | `crm:E55_Type2`|
| `crm:E35_Title1` | `crm:P2_has_type` | `crm:E55_Type3`|
| `crm:E35_Title2` | `crm:P2_has_type` | `crm:E55_Type4`|
| `crm:E35_Title2` | `crm:P2_has_type` | `crm:E55_Type5`|
| `crm:E41_Appellation1` | `crm:P106_is_composed_of` | `crm:E35_Title1`|
| `crm:E41_Appellation1` | `crm:P106_is_composed_of` | `crm:E35_Title2`|
