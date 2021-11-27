---
layout: default
title: DQuantize
parent: DtCore
# nav_order: 1
---

# DawTools.DtCore.DQuantize

The [DQuantize](dquantize.html#class-dawtoolsdtcoredquantizeargs) class provides a surface
to work with quantization. [More...](dquantize.html#detailed-description)

| Inheritance            |
|:-----------------------|
| DawTools.DtCore.DQuantize|

***

| Attributes|                  |
|:----------|:-----------------|
| value | int() |
| style | str() |
| tuplet | tuple() |
| swing | int() |

| Methods |
|:----------|
|def [\_\_call\_\_()](dquantize.html#dawtoolsdtcoredquantize__call__args)|
|def [tupletsPerNote()](dquantize.html)|
|def [quantizePerNote()](dquantize.html)|
|def [quantizeValue()](dquantize.html)|

### Detailed Description
This class can retrieve note value (note duration) for quantize units based on the given
parameters. It is important to note that when in the style of 'swing' it outputs 2 note values
due to the nature of swing quantization.

We refer to value as quantize denominator. In most daw's we see quantize represented as 1/8 1/16 1/32 1/16 T
 in this class the value is the denominator so 1/16 is represented as 16 for example.

It is also meant to be used with [DawTools.DtCore.DMeter](https://madponyinteractive.github.io/DawTools/DtCore/dmeter.html)

```python
quantize = DQuantize()
print(quantize)
# DQuantize(value = 8, style = straight, tuplet = (3,2), swing = 60)

# Setting values
quantize(16)# value = 16
quantize.value = 4 # value = 4
quantize.style = 'tuplet' # Style: 'straight' | 'tuplet' | 'swing'
quantize.tuplet = (5,4) # Tuplet value | 3/2 == Triplet
quantize.swing = 20 # Swing percentage 0 - 100

print(quantize)
# DQuantize(value = 4, style = tuplet, tuplet = (5,4), swing = 20)

# Copy object
quantize_2 = DQuantize(quantize)
quantize_2(8)
quantize_2.swing = 90
print(quantize)
# DQuantize(value = 4, style = tuplet, tuplet = (5,4), swing = 20)
print(quantize_2)
# DQuantize(value = 8, style = tuplet, tuplet = (5,4), swing = 20)

```

***

## class DawTools.DtCore.DQuantize
DawTools.DtCore.DQuantize(DQuantize)
DawTools.DtCore.DQuantize(value=8, style='straight', tuplet=(3,2), swing=60)

* Parameters

  * **value** - `int` -> default = 8
  * **style** - `str` -> default = 'straight'
  * **tuplet** - `tuple` -> default = (3,2)
  * **swing** - `int` -> default = 60
  * **DQuantize** - `DawTools.DtCore.DQuantize`

Constructs a DQuantize object.|

***

## DawTools.DtCore.DQuantize.\_\_call\_\_(value=None)
* Return type

  * `int`

If value is passed it sets a new quantize value. |
Return quantize value |

***

## DawTools.DtCore.DQuantize.tupletsPerNote()
This method is mainly used internally, to retrieve
units in 1 whole note you should use DQuantize.quantizePerNote()

* Return type

  * `Decimal`

Return How many tuplets in 1 whole note |

***

## DawTools.DtCore.DQuantize.quantizePerNote()
* Return type

  * `Decimal`

  * `int`

Return How many quantize units in 1 whole note |

***

## DawTools.DtCore.DQuantize.quantizeValue()

* Return type

  * [`DawTools.DtCore.DNoteValue`](https://madponyinteractive.github.io/DawTools/DtCore/dnotevalue.html)

Return DNoteValue for quantize units |
Return tuple(DNoteValue(note1), DNoteValue(note2)) | If DQuantize.style is 'swing' |
