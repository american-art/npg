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
    return UM.uri_from_fields("thesauri/title/", getValue("Title"))
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
    return UM.uri_from_fields("thesauri/title/", getValue("Title"))
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
| _BeginDate_ | `crm:P82_at_some_time_within` | `crm:E52_Time-Span2`|
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
| _FirstName_ | `rdfs:label` | `crm:E41_Appellation3`|
| _FirstNameAppellationURI_ | `uri` | `crm:E41_Appellation3`|
| _FirstNameURI_ | `uri` | `crm:E55_Type3`|
| _LastName_ | `rdfs:label` | `crm:E41_Appellation1`|
| _LastNameAppellationURI_ | `uri` | `crm:E41_Appellation1`|
| _LastNameURI_ | `uri` | `crm:E55_Type1`|
| _MiddleName_ | `rdfs:label` | `crm:E41_Appellation2`|
| _MiddleNameAppellationURI_ | `uri` | `crm:E41_Appellation2`|
| _MiddleNameURI_ | `uri` | `crm:E55_Type2`|
| _NameType_ | `rdfs:label` | `crm:E55_Type3`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _PrimaryTitle_ | `rdfs:label` | `crm:E35_Title1`|
| _PrimaryTitleTranslationType_ | `rdfs:label` | `crm:E55_Type2`|
| _PrimaryTitleTranslationTypeURI_ | `uri` | `crm:E55_Type2`|
| _PrimaryTitleType_ | `rdfs:label` | `crm:E55_Type1`|
| _PrimaryTitleTypeURI_ | `uri` | `crm:E55_Type1`|
| _PrimaryTitleURI_ | `uri` | `crm:E35_Title1`|
| _SecondaryTitle_ | `rdfs:label` | `crm:E35_Title2`|
| _SecondaryTitleTranslateType_ | `rdfs:label` | `crm:E55_Type4`|
| _SecondaryTitleTranslateTypeURI_ | `uri` | `crm:E55_Type4`|
| _SecondaryTitleType_ | `rdfs:label` | `crm:E55_Type3`|
| _SecondaryTitleTypeURI_ | `uri` | `crm:E55_Type3`|
| _SecondaryTitleURI_ | `uri` | `crm:E35_Title2`|


### Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E22_Man-Made_Object1` | `crm:P102_has_title` | `crm:E35_Title1`|
| `crm:E22_Man-Made_Object1` | `crm:P102_has_title` | `crm:E35_Title2`|
| `crm:E35_Title1` | `crm:P2_has_type` | `crm:E55_Type1`|
| `crm:E35_Title1` | `crm:P2_has_type` | `crm:E55_Type2`|
| `crm:E35_Title2` | `crm:P2_has_type` | `crm:E55_Type3`|
| `crm:E35_Title2` | `crm:P2_has_type` | `crm:E55_Type4`|
