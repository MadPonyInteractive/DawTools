---
layout: default
title: DSeconds
parent: DtCore
# nav_order: 1
---

# DawTools.DtCore.DSeconds

The [DSeconds](dseconds.html#dataclass-dawtoolsdtcoredsecondsvalue) class provides a surface
to convert seconds to other units of time. [More...](dseconds.html#detailed-description)

| Inheritance            |
|:-----------------------|
| DawTools.DtCore.DSeconds|

***

| Attributes|                  |
|:----------|:-----------------|
| value     | float(bpm value) |

| Methods |
|:----------|
|def \_\_add\_\_()|
|def \_\_sub\_\_()|
|def \_\_mul\_\_()|
|def \_\_truediv\_\_()|
|def \_\_eq\_\_()|
|def \_\_ge\_\_()|
|def \_\_gt\_\_()|
|def \_\_le\_\_()|
|def \_\_lt\_\_()|
|def [\_\_call\_\_()](dseconds.html#dawtoolsdtcoredseconds__call__)|
|def hours()|
|def minutes()|
|def ms()|
|def micro()|
|def nano()|

### Detailed Description
This @dataclass can be used for simple conversions from seconds to:
* hours
* minutes
* milliseconds
* microseconds
* nanoseconds

It is used together with other classes for ease seconds conversions.

```python
seconds = DSeconds(1)

print(seconds())       # 1
print(seconds.ms())    # 1000
print(seconds.micro()) # 1000000
print(seconds.nano())  # 1000000000

seconds += 1
print(seconds)# DSeconds(value=2)

seconds *= 0.5
print(seconds)# DSeconds(value=1.0)

seconds /= 2
print(seconds)# DSeconds(value=0.5)

seconds += DSeconds(10)
print(seconds)# DSeconds(value=10.5)
```
The object can work with different data types:
* int
* float
* decimal

You should make sure you are not combining different types or it will throw an error.

```python
# Starting with type int
seconds = DSeconds(1)

# Trying an add operation with a different type of decimal
# seconds += DSeconds(Decimal(10))
# TypeError: unsupported operand type(s) for +=: 'float' and 'decimal.Decimal'

# We need to first convert or create a new object
seconds.value = Decimal(0.5)
seconds += DSeconds(Decimal(10))
print(seconds)# DSeconds(value=Decimal('10.5'))
```
***

## @dataclass DawTools.DtCore.DSeconds(value)
* Parameters

  * **value** - `int` -> default = 0
  * **value** - `float` -> default = 0
  * **value** - `decimal` -> default = 0

Constructs a DSeconds object.|

***

## DawTools.DtCore.DBpm.\_\_call\_\_()

* Return type

  * `float`

  * `int`

  * `decimal`

Returns the current value of seconds|
Return type varies according to what was originally passed to it |
