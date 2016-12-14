# NPGObjConXrefs2_Sheet1

## Add Column

## Add Node/Literal

## PyTransforms
#### _SitterConstituentID_
From column: _ConstituentID_
``` python
if getValue("Prefix") == "Sitter:":
    return getValue("ConstituentID")
else:
    return ''

```

#### _SitterConstituentURI_
From column: _SitterConstituentID_
``` python
if getValue("SitterConstituentID"):
    return UM.uri_from_fields("person-institution/", getValue("SitterConstituentID"))
else:
    return ''

```

#### _PreferredTermsURI_
From column: _SitterConstituentID_
``` python
if getValue("SitterConstituentID"):
    return "http://vocab.getty.edu/aat/300404670"
else:
    return ''

```

#### _SitterPreferredIDURI_
From column: _SitterConstituentID_
``` python
if getValue("SitterConstituentID"):
    return UM.uri_from_fields("object/preferred_id/", getValue("SitterConstituentID"))
else:
    return ''

```

#### _SitterConstituentIDCopy_
From column: _SitterConstituentID_
``` python
return getValue("SitterConstituentID")
```

#### _ObjectURI_
From column: _ObjectID_
``` python
return UM.uri_from_fields("object/", getValue("ObjectID"))
```

#### _MakerConstituentID_
From column: _ConstituentID_
``` python
if getValue("Prefix") in ["Artist:", "Lithographer:", "Author:"]:
    return getValue("ConstituentID")
else:
    return ''
```

#### _MakerConstituentURI_
From column: _MakerConstituentID_
``` python
if getValue("MakerConstituentID"):
    return UM.uri_from_fields("person-institution/", getValue("MakerConstituentID"))
else:
    return ''
```

#### _PreferredTermsURI2_
From column: _MakerConstituentID_
``` python
if getValue("MakerConstituentID"):
    return "http://vocab.getty.edu/aat/300404670"
else:
    return ''

```

#### _MakerPreferredIDURI_
From column: _MakerConstituentID_
``` python
if getValue("MakerConstituentID"):
    return UM.uri_from_fields("object/preferred_id/", getValue("MakerConstituentID"))
else:
    return ''

```

#### _MakerConstituentIDCopy_
From column: _MakerConstituentID_
``` python
return getValue("MakerConstituentID")
```


## Selections

## Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _MakerConstituentID_ | `rdfs:label` | `crm:E42_Identifier2`|
| _MakerConstituentIDCopy_ | `rdf:value` | `crm:E42_Identifier2`|
| _MakerConstituentURI_ | `uri` | `owl:Thing2`|
| _MakerPreferredIDURI_ | `uri` | `crm:E42_Identifier2`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _PreferredTermsURI_ | `uri` | `crm:E55_Type1`|
| _PreferredTermsURI2_ | `uri` | `crm:E55_Type2`|
| _SitterConstituentID_ | `rdfs:label` | `crm:E42_Identifier1`|
| _SitterConstituentIDCopy_ | `rdf:value` | `crm:E42_Identifier1`|
| _SitterConstituentURI_ | `uri` | `owl:Thing1`|
| _SitterPreferredIDURI_ | `uri` | `crm:E42_Identifier1`|


## Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E12_Production1` | `crm:P14_carried_out_by` | `owl:Thing2`|
| `crm:E22_Man-Made_Object1` | `crm:P108i_was_produced_by` | `crm:E12_Production1`|
| `crm:E22_Man-Made_Object1` | `crm:P62_depicts` | `owl:Thing1`|
| `crm:E42_Identifier1` | `crm:P2_has_type` | `crm:E55_Type1`|
| `crm:E42_Identifier2` | `crm:P2_has_type` | `crm:E55_Type2`|
| `owl:Thing1` | `crm:P1_is_identified_by` | `crm:E42_Identifier1`|
| `owl:Thing2` | `crm:P1_is_identified_by` | `crm:E42_Identifier2`|
