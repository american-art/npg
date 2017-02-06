# NPGConAltNames2.csv

## Add Column

## Add Node/Literal

## PyTransforms
#### _ConstituentURI_
From column: _ConstituentID_
``` python
return UM.uri_from_fields("person-institution/", getValue("ConstituentID"))
```

#### _AltNameTypeURI_
From column: _NameType_
``` python
return UM.uri_from_fields("thesauri/alt_name_type/", getValue("NameType"))
```

#### _AltNameURI_
From column: _AltNameTypeURI_
``` python
return getValue("ConstituentURI") + "/alt_name"
```


## Selections

## Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _AltNameTypeURI_ | `uri` | `crm:E55_Type1`|
| _AltNameURI_ | `uri` | `crm:E82_Actor_Appellation1`|
| _ConstituentURI_ | `uri` | `crm:E39_Actor1`|
| _DisplayName_ | `rdf:value` | `crm:E82_Actor_Appellation1`|
| _NameType_ | `skos:prefLabel` | `crm:E55_Type1`|


## Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E39_Actor1` | `crm:P131_is_identified_by` | `crm:E82_Actor_Appellation1`|
| `crm:E82_Actor_Appellation1` | `crm:P2_has_type` | `crm:E55_Type1`|
