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
| _LatestBirthdate_ | `crm:P82b_end_of_the_end` | `crm:E52_Time-Span1`|
| _LatestDeathdate_ | `crm:P82b_end_of_the_end` | `crm:E52_Time-Span2`|
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
| `crm:E63_Beginning_of_Existence1` | `crm:P4_has_time-span` | `crm:E52_Time-Span1`|
| `crm:E64_End_of_Existence1` | `crm:P4_has_time-span` | `crm:E52_Time-Span2`|
| `crm:E82_Actor_Appellation1` | `crm:P2_has_type` | `xsd:http://vocab.getty.edu/aat/300404670`|
| `crm:E82_Actor_Appellation2` | `crm:P2_has_type` | `xsd:http://vocab.getty.edu/aat/300404672`|
