# NPGConThesTerms2_Sheet1

## Add Column

## Add Node/Literal

## PyTransforms
#### _ConstituentURI_
From column: _ConstituentID_
``` python
return UM.uri_from_fields("person-institution/", getValue("ConstituentID"))
```

#### _Gender_
From column: _Term_
``` python
if getValue("ThesXrefType") == "Gender":
    return getValue("Term")
else:
    return ''
```

#### _PlaceOfBirth_
From column: _Term_
``` python
if getValue("ThesXrefType") == "Place of birth":
    return getValue("Term")
else:
    return ''
```

#### _PlaceOfDeath_
From column: _PlaceOfBirth_
``` python
if getValue("ThesXrefType") == "Place of death":
    return getValue("Term")
else:
    return ''
```

#### _SexRoleURI_
From column: _Gender_
``` python
if getValue("Gender"):
    return "http://vocab.getty.edu/aat/300055147"
else:
    return ''
```

#### _GenderTypeClassURI_
From column: _Gender_
``` python
if getValue("Gender"):
    return getValue("ConstituentURI") + "/gender_type_class"
else:
    return ''
```

#### _GenderClassURI_
From column: _Gender_
``` python
if getValue("Gender"):
    return getValue("ConstituentURI") + "/gender_class"
else:
    return ''
```

#### _BirthEventURI_
From column: _PlaceOfBirth_
``` python
if getValue("PlaceOfBirth"):
    return getValue("ConstituentURI") + "/birth_event"
else:
    return ''
```

#### _BirthLocationURI_
From column: _PlaceOfBirth_
``` python
if getValue("PlaceOfBirth"):
    return getValue("ConstituentURI") + "/birth_location_class"
else:
    return ''
```

#### _DeathEventURI_
From column: _PlaceOfDeath_
``` python
if getValue("PlaceOfDeath"):
    return getValue("ConstituentURI") + "/death_event"
else:
    return ''
```

#### _DeathLocationURI_
From column: _PlaceOfDeath_
``` python
if getValue("PlaceOfDeath"):
    return getValue("ConstituentURI") + "/death_location_class"
else:
    return ''
```


## Selections

## Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _BirthEventURI_ | `uri` | `crm:E63_Beginning_of_Existence1`|
| _BirthLocationURI_ | `uri` | `crm:E53_Place1`|
| _ConstituentURI_ | `uri` | `owl:Thing1`|
| _DeathEventURI_ | `uri` | `crm:E64_End_of_Existence1`|
| _DeathLocationURI_ | `uri` | `crm:E53_Place2`|
| _Gender_ | `rdfs:label` | `crm:E55_Type3`|
| _GenderClassURI_ | `uri` | `crm:E55_Type3`|
| _GenderTypeClassURI_ | `uri` | `crm:E55_Type2`|
| _PlaceOfBirth_ | `rdfs:label` | `crm:E53_Place1`|
| _PlaceOfDeath_ | `rdfs:label` | `crm:E53_Place2`|
| _SexRoleURI_ | `uri` | `crm:E55_Type1`|


## Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E55_Type2` | `skos:broadMatch` | `crm:E55_Type1`|
| `crm:E55_Type3` | `crm:P2_has_type` | `crm:E55_Type2`|
| `crm:E63_Beginning_of_Existence1` | `crm:P7_took_place_at` | `crm:E53_Place1`|
| `crm:E64_End_of_Existence1` | `crm:P7_took_place_at` | `crm:E53_Place2`|
| `owl:Thing1` | `crm:P2_has_type` | `crm:E55_Type3`|
| `owl:Thing1` | `crm:P92i_was_brought_into_existence_by` | `crm:E63_Beginning_of_Existence1`|
| `owl:Thing1` | `crm:P93i_was_taken_out_of_existence_by` | `crm:E64_End_of_Existence1`|
