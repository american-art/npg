# NPGConstituents2_Sheet1

## Add Column

## Add Node/Literal
#### Literal Node: `http://vocab.getty.edu/aat/300404670`
Literal Type: ``
<br/>Language: ``
<br/>isUri: `true`

#### Literal Node: `http://vocab.getty.edu/aat/300404672`
Literal Type: ``
<br/>Language: ``
<br/>isUri: `true`

#### Literal Node: `http://vocab.getty.edu/aat/300404845`
Literal Type: ``
<br/>Language: ``
<br/>isUri: `true`

#### Literal Node: `http://vocab.getty.edu/aat/300404651`
Literal Type: ``
<br/>Language: ``
<br/>isUri: `true`

#### Literal Node: `http://vocab.getty.edu/aat/300404654`
Literal Type: ``
<br/>Language: ``
<br/>isUri: `true`

#### Literal Node: `http://vocab.getty.edu/aat/300404652`
Literal Type: ``
<br/>Language: ``
<br/>isUri: `true`


## PyTransforms
#### _ValidBirthYear_
From column: _BeginDate_
``` python
if (getValue("BeginDate") != '0') and (getValue("ConstituentType") == 'Individual'):
    return getValue("BeginDate")
else:
    return ''
```

#### _ValidDeathYear_
From column: _EndDate_
``` python
if (getValue("EndDate") != '0') and (getValue("ConstituentType") == 'Individual'):
    return getValue("EndDate")
else:
    return ''
```

#### _ValidDisplayDate_
From column: _DisplayDate_
``` python
if (getValue("DisplayDate") != 'NULL') and (getValue("ConstituentType") == 'Individual'):
    return getValue("DisplayDate")
else:
    return ''
```

#### _EarliestBirthdate_
From column: _ValidBirthYear_
``` python
if getValue("ValidBirthYear"):
    return '01-01-' + getValue("ValidBirthYear")
else:
    return ''
```

#### _LatestBirthdate_
From column: _EarliestBirthdate_
``` python
if getValue("ValidBirthYear"):
    return '12-31-' + getValue("ValidBirthYear")
else:
    return ''
```

#### _EarliestDeathdate_
From column: _ValidDeathYear_
``` python
if getValue("ValidDeathYear"):
    return '01-01-' + getValue("ValidDeathYear")
else:
    return ''
```

#### _LatestDeathdate_
From column: _EarliestDeathdate_
``` python
if getValue("ValidDeathYear"):
    return '12-31-' + getValue("ValidDeathYear")
else:
    return ''
```

#### _ConstituentURI_
From column: _ConstituentID_
``` python
return UM.uri_from_fields("person-institution/", getValue("ConstituentID"))
```

#### _BirthTimespanURI_
From column: _BeginDate_
``` python
if getValue("ValidBirthYear"):
    return getValue("ConstituentURI") + "/birth_timespan"
else:
    return ''
```

#### _BirthURI_
From column: _BeginDate_
``` python
if getValue("ValidBirthYear"):
    return getValue("ConstituentURI") + "/birth_event"
else:
    return ''
```

#### _DeathTimespanURI_
From column: _EndDate_
``` python
if getValue("ValidDeathYear"):
    return getValue("ConstituentURI") + "/death_timespan"
else:
    return ''
```

#### _DeathURI_
From column: _EndDate_
``` python
if getValue("ValidDeathYear"):
    return getValue("ConstituentURI") + "/death_event"
else:
    return ''
```

#### _ActorAppellationURI_
From column: _DisplayName_
``` python
return getValue("ConstituentURI") + "/primary_name"
```

#### _DisplayNameCopy_
From column: _DisplayName_
``` python
return getValue("DisplayName")
```

#### _SortNameURI_
From column: _AlphaSort_
``` python
return getValue("ConstituentURI") + "/sort_name"
```

#### _NamePrefixTypeClassURI_
From column: _NameTitle_
``` python
if getValue("NameTitle") != 'NULL':
    return getValue("ConstituentURI") + "/name_prefix_type_class"
else:
    return ''
```

#### _NamePrefixClassURI_
From column: _NameTitle_
``` python
if getValue("NameTitle") != 'NULL':
    return getValue("ConstituentURI") + "/name_prefix_class"
else:
    return ''
```

#### _NamePrefixValid_
From column: _NameTitle_
``` python
if getValue("NameTitle") != 'NULL':
    return getValue("NameTitle")
else:
    return ''
```

#### _GivenNameTypeClass_
From column: _FirstName_
``` python
if getValue("FirstName") != 'NULL':
    return getValue("ConstituentURI") + "/given_name_type_class"
else:
    return ''
```

#### _GivenNameClassURI_
From column: _FirstName_
``` python
if getValue("FirstName") != 'NULL':
    return getValue("ConstituentURI") + "/given_name_class"
else:
    return ''
```

#### _FirstNameValid_
From column: _FirstName_
``` python
if getValue("FirstName") != 'NULL':
    return getValue("FirstName")
else:
    return ''
```

#### _MiddleNameTypeClassURI_
From column: _MiddleName_
``` python
if getValue("MiddleName") != 'NULL':
    return getValue("ConstituentURI") + "/middle_name_type_class"
else:
    return ''
```

#### _MiddleNameClassURI_
From column: _MiddleName_
``` python
if getValue("MiddleName") != 'NULL':
    return getValue("ConstituentURI") + "middle_name_class"
else:
    return ''
```

#### _MiddleNameValid_
From column: _MiddleName_
``` python
if getValue("MiddleName") != 'NULL':
    return getValue("MiddleName")
else:
    return ''
```

#### _FamilyNameTypeClass_
From column: _LastName_
``` python
if getValue("LastName") != 'NULL':
    return getValue("ConstituentURI") + "/family_name_type_class"
else:
    return ''
```

#### _FamilyNameClassURI_
From column: _LastName_
``` python
if getValue("LastName") != 'NULL':
    return getValue("ConstituentURI") + "/family_name_class"
else:
    return ''
```

#### _FamilyNameValid_
From column: _LastName_
``` python
if getValue("LastName") != 'NULL':
    return getValue("LastName")
else:
    return ''
```


## Selections

## Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _ActorAppellationURI_ | `uri` | `crm:E82_Actor_Appellation1`|
| _AlphaSort_ | `rdf:value` | `crm:E82_Actor_Appellation2`|
| _BirthTimespanURI_ | `uri` | `crm:E52_Time-Span1`|
| _BirthURI_ | `uri` | `crm:E63_Beginning_of_Existence1`|
| _ConstituentURI_ | `uri` | `crm:E39_Actor1`|
| _DeathTimespanURI_ | `uri` | `crm:E52_Time-Span2`|
| _DeathURI_ | `uri` | `crm:E64_End_of_Existence1`|
| _DisplayName_ | `rdfs:label` | `crm:E39_Actor1`|
| _DisplayNameCopy_ | `rdf:value` | `crm:E82_Actor_Appellation1`|
| _EarliestBirthdate_ | `crm:P82a_begin_of_the_begin` | `crm:E52_Time-Span1`|
| _EarliestDeathdate_ | `crm:P82a_begin_of_the_begin` | `crm:E52_Time-Span2`|
| _FamilyNameClassURI_ | `uri` | `crm:E82_Actor_Appellation6`|
| _FamilyNameTypeClass_ | `uri` | `crm:E55_Type4`|
| _FamilyNameValid_ | `rdf:value` | `crm:E82_Actor_Appellation6`|
| _FirstNameValid_ | `rdf:value` | `crm:E82_Actor_Appellation4`|
| _GivenNameClassURI_ | `uri` | `crm:E82_Actor_Appellation4`|
| _GivenNameTypeClass_ | `uri` | `crm:E55_Type2`|
| _LatestBirthdate_ | `crm:P82b_end_of_the_end` | `crm:E52_Time-Span1`|
| _LatestDeathdate_ | `crm:P82b_end_of_the_end` | `crm:E52_Time-Span2`|
| _MiddleNameClassURI_ | `uri` | `crm:E82_Actor_Appellation5`|
| _MiddleNameTypeClassURI_ | `uri` | `crm:E55_Type3`|
| _MiddleNameValid_ | `rdf:value` | `crm:E82_Actor_Appellation5`|
| _NamePrefixClassURI_ | `uri` | `crm:E82_Actor_Appellation3`|
| _NamePrefixTypeClassURI_ | `uri` | `crm:E55_Type1`|
| _NamePrefixValid_ | `rdf:value` | `crm:E82_Actor_Appellation3`|
| _SortNameURI_ | `uri` | `crm:E82_Actor_Appellation2`|
| _ValidBirthYear_ | `rdfs:label` | `crm:E52_Time-Span1`|
| _ValidDeathYear_ | `rdfs:label` | `crm:E52_Time-Span2`|


## Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E39_Actor1` | `crm:P92i_was_brought_into_existence_by` | `crm:E63_Beginning_of_Existence1`|
| `crm:E39_Actor1` | `crm:P93i_was_taken_out_of_existence_by` | `crm:E64_End_of_Existence1`|
| `crm:E39_Actor1` | `crm:P131_is_identified_by` | `crm:E82_Actor_Appellation1`|
| `crm:E39_Actor1` | `crm:P131_is_identified_by` | `crm:E82_Actor_Appellation2`|
| `crm:E55_Type1` | `skos:broadMatch` | `xsd:http://vocab.getty.edu/aat/300404845`|
| `crm:E55_Type2` | `skos:broadMatch` | `xsd:http://vocab.getty.edu/aat/300404651`|
| `crm:E55_Type3` | `skos:broadMatch` | `xsd:http://vocab.getty.edu/aat/300404654`|
| `crm:E55_Type4` | `skos:broadMatch` | `xsd:http://vocab.getty.edu/aat/300404652`|
| `crm:E63_Beginning_of_Existence1` | `crm:P4_has_time-span` | `crm:E52_Time-Span1`|
| `crm:E64_End_of_Existence1` | `crm:P4_has_time-span` | `crm:E52_Time-Span2`|
| `crm:E82_Actor_Appellation1` | `crm:P106_is_composed_of` | `crm:E82_Actor_Appellation3`|
| `crm:E82_Actor_Appellation1` | `crm:P106_is_composed_of` | `crm:E82_Actor_Appellation4`|
| `crm:E82_Actor_Appellation1` | `crm:P106_is_composed_of` | `crm:E82_Actor_Appellation5`|
| `crm:E82_Actor_Appellation1` | `crm:P106_is_composed_of` | `crm:E82_Actor_Appellation6`|
| `crm:E82_Actor_Appellation1` | `crm:P2_has_type` | `xsd:http://vocab.getty.edu/aat/300404670`|
| `crm:E82_Actor_Appellation2` | `crm:P2_has_type` | `xsd:http://vocab.getty.edu/aat/300404672`|
| `crm:E82_Actor_Appellation3` | `crm:P2_has_type` | `crm:E55_Type1`|
| `crm:E82_Actor_Appellation4` | `crm:P2_has_type` | `crm:E55_Type2`|
| `crm:E82_Actor_Appellation5` | `crm:P2_has_type` | `crm:E55_Type3`|
| `crm:E82_Actor_Appellation6` | `crm:P2_has_type` | `crm:E55_Type4`|
