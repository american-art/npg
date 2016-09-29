## NPGObjects_Sheet1

### PyTransforms
#### _ObjectURI_
From column: _ObjectID_
>``` python
return "object/"+getValue("ObjectID")
```

#### _ClassificationURI_
From column: _Classification_
>``` python
if getValue("Classification"):
    return "thesauri/classification/"+getValue("Classification").replace(" ","-")
else:
    return ""
```

#### _ProductionURI_
From column: _ClassificationURI_
>``` python
return getValue("ObjectURI")+"/production"

```

#### _DimensionURI_
From column: _Dimensions_
>``` python
return getValue("ObjectURI")+"/dimensions"
```

#### _ProductionDateURI_
From column: _DateEnd_
>``` python
return getValue("ObjectURI")+"/production/date"

```

#### _MuseumURI_
From column: _CreditLine_
>``` python
return "http://www.npg.si.edu/"
```

#### _Acquisition_
From column: _MuseumURI_
>``` python
if getValue("CreditLine"):
    return getValue("CreditLine").split(";")[1]
else:
    return ""
```

#### _AcquisitionURI_
From column: _Acquisition_
>``` python
return getValue("ObjectURI")+"/acquisition"
```

#### _DateBeginValid_
From column: _DateBegin_
>``` python
if getValue("DateBegin") == '0':
    return ""
else:
    return getValue("DateBegin")
```

#### _DateEndValid_
From column: _DateEnd_
>``` python
if getValue("DateEnd") == '0':
    return ""
else:
    return getValue("DateEnd")
```

#### _MediumURI_
From column: _Medium_
>``` python
if getValue("Medium"):
    return getValue("ObjectURI")+"/medium"
```


### Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _Classification_ | `rdfs:label` | `E55_Type1`|
| _ClassificationURI_ | `uri` | `E55_Type1`|
| _DateBeginValid_ | `http://www.cidoc-crm.org/cidoc-crm/P82a_begin_of_the_begin` | `E52_Time-Span1`|
| _DateEndValid_ | `http://www.cidoc-crm.org/cidoc-crm/P82b_end_of_the_end` | `E52_Time-Span1`|
| _Dated_ | `rdfs:label` | `E52_Time-Span1`|
| _DimensionURI_ | `uri` | `E54_Dimension1`|
| _Dimensions_ | `http://www.cidoc-crm.org/cidoc-crm/P3_has_note` | `E54_Dimension1`|
| _Medium_ | `http://www.cidoc-crm.org/cidoc-crm/P3_has_note` | `E57_Material1`|
| _MediumURI_ | `uri` | `E57_Material1`|
| _ObjectURI_ | `uri` | `E22_Man-Made_Object1`|
| _ProductionDateURI_ | `uri` | `E52_Time-Span1`|
| _ProductionURI_ | `uri` | `E12_Production1`|


### Links
| From | Property | To |
|  --- | -------- | ---|
| `E12_Production1` | `http://www.cidoc-crm.org/cidoc-crm/P4_has_time-span` | `E52_Time-Span1`|
| `E22_Man-Made_Object1` | `http://www.cidoc-crm.org/cidoc-crm/P108i_was_produced_by` | `E12_Production1`|
| `E22_Man-Made_Object1` | `http://www.cidoc-crm.org/cidoc-crm/P2_has_type` | `E55_Type1`|
| `E22_Man-Made_Object1` | `http://www.cidoc-crm.org/cidoc-crm/P43_has_dimension` | `E54_Dimension1`|
| `E22_Man-Made_Object1` | `http://www.cidoc-crm.org/cidoc-crm/P45_consists_of` | `E57_Material1`|
