## NPGConAltNames2_Sheet1

### PyTransforms
#### _ConstituentURI_
From column: _ConstituentID_
>``` python
return "person-institution/" + getValue("ConstituentID")
```

#### _FirstNameURI_
From column: _FirstName_
>``` python
if getValue("FirstName") != 'NULL':
    return UM.uri_from_fields("thesauri/first_name/", getValue("FirstName"))
else:
    return ''
```

#### _MiddleNameURI_
From column: _MiddleName_
>``` python
if getValue("MiddleName") != 'NULL':
    return UM.uri_from_fields("thesauri/middle_name/", getValue("MiddleName"))
else:
    return ''
```

#### _LastNameURI_
From column: _LastName_
>``` python
if getValue("LastName") != 'NULL':
    return "thesauri/last_name/" + getValue("LastName").lower().replace(' ', '_')
else:
    return ''
```

#### _SuffixURI_
From column: _Suffix_
>``` python
if getValue("Suffix") != 'NULL':
    return "thesauri/suffix/" + getValue("Suffix").lower().replace(' ', '_')
else:
    return ''
```

#### _DisplayNameURI_
From column: _DisplayName_
>``` python
if getValue("DisplayName") != 'NULL':
    return UM.uri_from_fields("thesauri/display_name/", getValue("DisplayName"))
else:
    return ''
```

#### _NameTypeURI_
From column: _NameType_
>``` python
if getValue("NameType") != 'NULL':
    return "thesauri/name_type/" + getValue("NameType").lower().replace(' ', '_')
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
| _ConstituentURI_ | `uri` | `crm:E39_Actor1`|
| _DeathDateURI_ | `uri` | `crm:E52_Time-Span1`|
| _DeathURI_ | `uri` | `crm:E69_Death1`|
| _DisplayName_ | `rdfs:label` | `crm:E41_Appellation5`|
| _DisplayNameURI_ | `uri` | `crm:E41_Appellation5`|
| _DisplayNameURI_ | `uri` | `crm:E41_Appellation4`|
| _DisplayPersonInstitutionName_ | `rdfs:label` | `crm:E41_Appellation4`|
| _EndDate_ | `crm:P82_at_some_time_within` | `crm:E52_Time-Span1`|
| _FirstName_ | `rdfs:label` | `crm:E41_Appellation1`|
| _FirstName_ | `rdfs:label` | `crm:E41_Appellation3`|
| _FirstNameAppellationURI_ | `uri` | `crm:E41_Appellation3`|
| _FirstNameURI_ | `uri` | `crm:E55_Type3`|
| _FirstNameURI_ | `uri` | `crm:E41_Appellation1`|
| _LastName_ | `rdfs:label` | `crm:E41_Appellation3`|
| _LastName_ | `rdfs:label` | `crm:E41_Appellation1`|
| _LastNameAppellationURI_ | `uri` | `crm:E41_Appellation1`|
| _LastNameURI_ | `uri` | `crm:E55_Type1`|
| _LastNameURI_ | `uri` | `crm:E41_Appellation3`|
| _MiddleName_ | `rdfs:label` | `crm:E41_Appellation2`|
| _MiddleName_ | `rdfs:label` | `crm:E41_Appellation2`|
| _MiddleNameAppellationURI_ | `uri` | `crm:E41_Appellation2`|
| _MiddleNameURI_ | `uri` | `crm:E55_Type2`|
| _MiddleNameURI_ | `uri` | `crm:E41_Appellation2`|
| _NameType_ | `rdfs:label` | `crm:E55_Type1`|
| _NameTypeURI_ | `uri` | `crm:E55_Type1`|
| _Suffix_ | `rdfs:label` | `crm:E41_Appellation4`|
| _SuffixURI_ | `uri` | `crm:E41_Appellation4`|


### Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E39_Actor1` | `crm:P1_is_identified_by` | `crm:E41_Appellation5`|
| `crm:E41_Appellation5` | `crm:P1_is_identified_by` | `crm:E41_Appellation1`|
| `crm:E41_Appellation5` | `crm:P1_is_identified_by` | `crm:E41_Appellation2`|
| `crm:E41_Appellation5` | `crm:P1_is_identified_by` | `crm:E41_Appellation3`|
| `crm:E41_Appellation5` | `crm:P1_is_identified_by` | `crm:E41_Appellation4`|
| `crm:E41_Appellation5` | `crm:P2_has_type` | `crm:E55_Type1`|
