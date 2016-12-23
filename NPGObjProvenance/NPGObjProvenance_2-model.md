# NPGObjProvenance_2_Sheet1

## Add Column

## Add Node/Literal
#### Literal Node: `http://vocab.getty.edu/aat/300026687`
Literal Type: ``
<br/>Language: ``
<br/>isUri: `true`


## PyTransforms
#### _ObjectURI_
From column: _ObjectID_
``` python
return "object/" + getValue("ObjectID")
```

#### _CreditLineURI_
From column: _Provenance_
``` python
return getValue("ObjectURI") + "/credit_line"
```


## Selections

## Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _CreditLineURI_ | `uri` | `crm:E33_Linguistic_Object1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _Provenance_ | `rdf:value` | `crm:E33_Linguistic_Object1`|


## Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E22_Man-Made_Object1` | `crm:P67i_is_referred_to_by` | `crm:E33_Linguistic_Object1`|
| `crm:E33_Linguistic_Object1` | `crm:P2_has_type` | `xsd:http://vocab.getty.edu/aat/300026687`|
