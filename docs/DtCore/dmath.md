---
layout: default
title: DMath
parent: DtCore
# nav_order: 1
---
# Module DawTools.DtCore.DMath

| Functions |
|:----------|
|def [DMapVal()](dmath.html#dawtoolsdtcoredmathdmapvalvalue-in_start-in_end-out_start-out_end)|
|def [DNearlyEqual()](dmath.html#dawtoolsdtcoredmathdnearlyequala-b-decimal_size)|
|def [DCloseIn()](dmath.html#dawtoolsdtcoredmathdcloseina-check_list-decimal_size)|
|def [DClosest()](dmath.html#dawtoolsdtcoredmathdclosestnum-check_list)|
|def [DRemoveExponent()](dmath.html#dawtoolsdtcoredmathdremoveexponentd)|

| Classes |
|:----------|
| [DRange](dmath.html#dawtoolsdtcoredmathdrange)|

***

## DawTools.DtCore.DMath.DMapVal(value, in_start, in_end, out_start, out_end)
Maps received value in_start,in_end to out_start,out_end
* Parameters

  * **value** - `int` or `float` or `Decimal`
  * **in_start** - `int` or `float` or `Decimal`
  * **in_end** - `int` or `float` or `Decimal`
  * **out_start** - `int` or `float` or `Decimal`
  * **out_end** - `int` or `float` or `Decimal`

* Return type

  * `int`
  * `float`
  * `decimal`

Return mapped value |

***

## DawTools.DtCore.DMath.DNearlyEqual(a, b, decimal_size)
Checks if a is nearly equal to b

decimal_size determines how many decimal units to check
* Parameters

  * **a** - `int` or `float` or `Decimal`
  * **b** - `int` or `float` or `Decimal`
  * **decimal_size** - `int` or `float` or `Decimal` -> default = 5

* Return type

  * `bool`

Return True if a is nearly equal to b |

***

## DawTools.DtCore.DMath.DCloseIn(a, check_list, decimal_size)
Checks if a is nearly equal to any in check_list

decimal_size determines how many decimal units to check
* Parameters

  * **a** - `int` or `float` or `Decimal`
  * **check_list** - `iter`
  * **decimal_size** - `int` or `float` or `Decimal` -> default = 5

* Return type

  * `bool`

Return True if a is nearly equal to any in check_list |

***

## DawTools.DtCore.DMath.DClosest(num, check_list)
* Parameters

  * **num** - `int` or `float` or `Decimal`
  * **check_list** - `iter`

* Return type

  * `int` or `float` or `Decimal`

Return closest number to num in check_list|

***

## DawTools.DtCore.DMath.DRemoveExponent(d)
Converts exponent numbers E-4 to numbers in Decimals
* Parameters

  * **d** - `Decimal`

* Return type

  * `Decimal`

Return Decimal with removed exponent|

***

## DawTools.DtCore.DMath.DRange
The [DRange](dmath.html#class-dawtoolsdtcoredmathdrangeargs) class provides a surface
to retrieve normalized and de-normalized values within a set range.
[More...](dmath.html#drange-detailed-description)

***

| Attributes|                  |
|:----------|:-----------------|
| start     | float |
| end       | float |

| Methods |
|:----------|
|def [\_\_call\_\_()](dmath.html#dawtoolsdtcoredmathdrange__call__valueinverted)|
|def [normalize()](dmath.html#dawtoolsdtcoredmathdrangenormalizevalueinverted)|
|def [deNormalize()](dmath.html#dawtoolsdtcoredmathdrangedenormalizevalueinverted)|

### DRange Detailed Description
This class provides methods to retrieve normalized and
 de-normalized values within a set range

```python
from DawTools.DtCore.DMath import DRange
DRange(0,10).start # 0
DRange(0,10).end # 10
DRange(0,10).normalize(4) # 0.4
DRange(0,10).normalize(4,inverted=True) # 0.6
DRange(0,10).deNormalize(0.4) # 4.0
DRange(0,10).deNormalize(0.4,True) # 6.0

_range = DRange(0,10)
_range(4,True) # 0.6 same as _range.normalize(4,True)
```

***

## class DawTools.DtCore.DMath.DRange(args)
DawTools.DtCore.DMath.DRange(start,end)
* Parameters

  * **start** - `float` -> default = 0
  * **end** - `float` -> default = 0
  * **start** - `int` -> default = 0
  * **end** - `int` -> default = 0

Constructs a DRange object.|

***

## DawTools.DtCore.DMath.DRange.\_\_call\_\_(value,inverted)
* Parameters

  * **value** - `int`
  * **value** - `float`
  * **inverted** - `bool` -> default = False

* Return type

  * `int`
  * `float`

Return normalized value in 0.0 to 1.0 range |

***

## DawTools.DtCore.DMath.DRange.normalize(value,inverted)
* Parameters

  * **value** - `int`
  * **value** - `float`
  * **inverted** - `bool` -> default = False

* Return type

  * `int`
  * `float`

Return normalized value in 0.0 to 1.0 range |

***

## DawTools.DtCore.DMath.DRange.deNormalize(value,inverted)
* Parameters

  * **value** - `int`
  * **value** - `float`
  * **inverted** - `bool` -> default = False

* Return type

  * `int`
  * `float`

Return de-normalized value in start to end range |
