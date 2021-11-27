---
layout: default
title: DNoteValue
parent: DtCore
# nav_order: 1
---

# DawTools.DtCore.DNoteValue

The [DNoteValue](dnotevalue.html#class-dawtoolsdtcorednotevalue) class provides a surface
to work with note values as strings or floats. [More...](dnotevalue.html#detailed-description)

| Inheritance            |
|:-----------------------|
| DawTools.DtCore.DNoteValue|

***

| Attributes|                  |
|:----------|:-----------------|
| value | str() |
| value | float() |

| Methods |
|:----------|
|def \_\_add\_\_()|
|def \_\_sub\_\_()|
|def \_\_mul\_\_()|
|def \_\_truediv\_\_()|
|def \_\_eq\_\_()|
|def \_\_gt\_\_()|
|def \_\_ge\_\_()|
|def \_\_lt\_\_()|
|def \_\_le\_\_()|
|def \_\_float\_\_()|
|def \_\_str\_\_()|
|def \_\_iter\_\_()|
|def [\_\_call\_\_()](dnotevalue.html#dawtoolsdtcorednotevalue__call__value)|
|def [findNoteValue()](dnotevalue.html#dawtoolsdtcorednotevaluefindnotevalue)|

### Detailed Description
Note Value class that can convert float
to note value 0.5 = 1/2 interchangeably
Used for working with note values

#### Some Note Values
    * 1.0   = 1/1  = 1 Whole note
    * 0.5   = 1/2  = Half note
    * 0.25  = 1/4  = Quarter note
    * 0.375 = 3/8  = Three eight note
    * 10.0  = 10/1 = 10 Whole notes
    * 0.0   = 0    = 0 Whole notes

Calling this class will always retrieve a float

This class has the ability to convert floats to note values as seen
above but has some caveats. Please check help(DNoteValue.findNoteValue)

You can set the note value (value) to an int, string or float
but internal add, sub, mul and div calculations are always
done via it's float value.

It is also meant to be used with [DawTools.DtCore.DMeter](https://madponyinteractive.github.io/DawTools/DtCore/dmeter.html)

```python
from DawTools.DtCore import DNoteValue
from decimal import Decimal

# Any of this construct methods
noteVal = DNoteValue(Decimal(0.375))
noteVal = DNoteValue(0.375)
noteVal = DNoteValue('3/8')

# will produce the same results
print(type(noteVal))# <class 'DNoteValue'>
print(noteVal)# 3/8
print(str(noteVal))# 3/8
print(tuple(noteVal))# (3, 8)
print(list(noteVal))# [3, 8]
print(float(noteVal))# 0.375

# 10 whole notes
noteVal = DNoteValue(10)
print(repr(noteVal))# DNoteValue(value=10.0)

# Calling will return a float
print(noteVal())# 10.0
# Printing or using the str method
# returns a string
print(noteVal)# 10/1

# In cases where it cannot find a
# nominator/denominator value
# it returns value/1
noteVal = DNoteValue(0.5657)
print(noteVal)# 0.5657/1

# Finally, iterating will return the
# nominator/denominator values
for i in noteVal:
    print(i)
# 0.5657
# 1
```

***

## class DawTools.DtCore.DNoteValue
DawTools.DtCore.DNoteValue(value='1/1')

* Parameters

  * **value** - `str` -> default = '1/1'
  * **value** - `int`
  * **value** - `float`
  * **value** - `decimal`

Constructs a DNoteValue object.|

***

## DawTools.DtCore.DNoteValue.\_\_call\_\_(value)
* Parameters

  * **value** - `float` -> default = None

* Return type

  * `float`

If value is passed it sets a new value. |
Return note value |

***

## DawTools.DtCore.DNoteValue.findNoteValue()
Finds the first possible numerator and denominator
for a note value in float format.

You do not need to call this method, you can
simply use str(DNoteValue) or tuple(DNoteValue)

#### Note:
    `It will return the first possible combination,
        so even though 4/8 = 0.5
        when you try findNoteValue(0.5)
        it will return 1/2`

* Parameters

  * **value** - `float` -> default = None

* Return type

  * `tuple`

Return tuple(int(numerator), int(denominator)) |
Return tuple(value,1) | If not a valid note value
