# NPGObjConXrefs3.csv

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
    return getValue("SitterConstituentURI") + "/preferred_id"
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
    return getValue("MakerConstituentURI") + "/preferred_id"
else:
    return ''

```

#### _MakerConstituentIDCopy_
From column: _MakerConstituentID_
``` python
return getValue("MakerConstituentID")
```

#### _ProductionURI_
From column: _ConstituentID_
``` python
if getValue("SitterConstituentURI") or getValue("MakerConstituentURI"):
    return getValue("ObjectURI")+"/production"
else:
    return ""
```


## Selections

## Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _MakerConstituentURI_ | `uri` | `crm:E39_Actor1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _ProductionURI_ | `uri` | `crm:E12_Production1`|
| _SitterConstituentURI_ | `uri` | `crm:E39_Actor2`|


## Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E12_Production1` | `crm:P14_carried_out_by` | `crm:E39_Actor1`|
| `crm:E22_Man-Made_Object1` | `crm:P108i_was_produced_by` | `crm:E12_Production1`|
| `crm:E22_Man-Made_Object1` | `crm:P62_depicts` | `crm:E39_Actor2`|
