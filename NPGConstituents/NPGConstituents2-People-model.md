## NPGConstituents2_Sheet1

### PyTransforms
#### _ConstituentURI_
From column: _ConstituentID_
>``` python
return "person-institution/"+getValue("ConstituentID")
```

#### _FirstNameURI_
From column: _FirstName_
>``` python
if getValue("FirstName") == 'NULL':
    return ""
else:
    return "thesauri/nametype/firstname"

```

#### _FirstNameAppellationURI_
From column: _FirstNameURI_
>``` python
if getValue("FirstName") != 'NULL':
    return UM.uri_from_fields("thesauri/first_name/", getValue("FirstName"))
else:
    return ''


```

#### _MiddleNameURI_
From column: _MiddleName_
>``` python
if getValue("MiddleName") == 'NULL':
    return ""
else:
    return "thesauri/nametype/middlename"

```

#### _MiddleNameAppellationURI_
From column: _MiddleNameURI_
>``` python
if getValue("MiddleName") != 'NULL':
    return UM.uri_from_fields("thesauri/middle_name/", getValue("MiddleName"))
else:
    return ''
```

#### _LastNameURI_
From column: _LastName_
>``` python
if getValue("LastName") == 'NULL':
    return ""
else:
    return "thesauri/nametype/lastname"

```

#### _LastNameAppellationURI_
From column: _LastNameURI_
>``` python
if getValue("LastName") != 'NULL':
    return "thesauri/last_name/" + getValue("LastName").lower().replace(' ', '_')
else:
    return ''
```

#### _BirthURI_
From column: _BeginDate_
>``` python
if getValue("BeginDate"):
    if int (getValue("BeginDate"))>0:
        return getValue("ConstituentURI")+"/birth"
    else:
        return ""
else:
    return ""
```

#### _BirthDateURI_
From column: _BirthURI_
>``` python
if getValue("BirthURI"):
    return getValue("BirthURI")+"/date"
else:
    return ""
```

#### _DeathURI_
From column: _EndDate_
>``` python
if getValue("EndDate"):
    if int (getValue("EndDate"))>0:
        return getValue("ConstituentURI")+"/death"
    else:
        return ""
else:
    return ""
```

#### _DeathDateURI_
From column: _DeathURI_
>``` python
if getValue("DeathURI"):
    return getValue("DeathURI")+"/date"
else:
    return ""
```

#### _DisplayPersonInstitutionName_
From column: _DisplayName_
>``` python
if getValue("DisplayName") == 'NULL':
    return getValue("Institution")
else:
    return getValue("DisplayName")
```

#### _DisplayNameURI_
From column: _DisplayName_
>``` python
if getValue("DisplayName") != 'NULL':
    return UM.uri_from_fields("thesauri/display_name/", getValue("DisplayName"))
else:
    return ''
```


### Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _BeginDate_ | `crm:P82_at_some_time_within` | `crm:E52_Time-Span1`|
| _BirthDateURI_ | `uri` | `crm:E52_Time-Span1`|
| _BirthURI_ | `uri` | `crm:E67_Birth1`|
| _ConstituentURI_ | `uri` | `crm:E39_Actor1`|
| _DeathDateURI_ | `uri` | `crm:E52_Time-Span2`|
| _DeathURI_ | `uri` | `crm:E69_Death1`|
| _DisplayNameURI_ | `uri` | `crm:E41_Appellation1`|
| _DisplayPersonInstitutionName_ | `rdfs:label` | `crm:E41_Appellation1`|
| _EndDate_ | `crm:P82_at_some_time_within` | `crm:E52_Time-Span2`|
| _FirstName_ | `rdfs:label` | `crm:E41_Appellation2`|
| _FirstNameAppellationURI_ | `uri` | `crm:E41_Appellation2`|
| _FirstNameURI_ | `uri` | `crm:E55_Type1`|
| _LastName_ | `rdfs:label` | `crm:E41_Appellation4`|
| _LastNameAppellationURI_ | `uri` | `crm:E41_Appellation4`|
| _LastNameURI_ | `uri` | `crm:E55_Type3`|
| _MiddleName_ | `rdfs:label` | `crm:E41_Appellation3`|
| _MiddleNameAppellationURI_ | `uri` | `crm:E41_Appellation3`|
| _MiddleNameURI_ | `uri` | `crm:E55_Type2`|


### Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E39_Actor1` | `crm:P131_is_identified_by` | `crm:E41_Appellation1`|
| `crm:E39_Actor1` | `crm:P98i_was_born` | `crm:E67_Birth1`|
| `crm:E39_Actor1` | `crm:P100i_died_in` | `crm:E69_Death1`|
| `crm:E41_Appellation1` | `crm:P106_is_composed_of` | `crm:E41_Appellation2`|
| `crm:E41_Appellation1` | `crm:P106_is_composed_of` | `crm:E41_Appellation3`|
| `crm:E41_Appellation1` | `crm:P106_is_composed_of` | `crm:E41_Appellation4`|
| `crm:E41_Appellation2` | `crm:P2_has_type` | `crm:E55_Type1`|
| `crm:E41_Appellation3` | `crm:P2_has_type` | `crm:E55_Type2`|
| `crm:E41_Appellation4` | `crm:P2_has_type` | `crm:E55_Type3`|
| `crm:E67_Birth1` | `crm:P4_has_time-span` | `crm:E52_Time-Span1`|
| `crm:E69_Death1` | `crm:P4_has_time-span` | `crm:E52_Time-Span2`|
