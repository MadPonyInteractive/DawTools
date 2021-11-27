---
layout: default
title: DTimeSignature
parent: DtCore
# nav_order: 1
---

# DawTools.DtCore.DTimeSignature

The [DTimeSignature](dtimesignature.html#class-dawtoolsdtcoredtimesignatureargs) class provides a surface
to work with time signatures. [More...](dtimesignature.html#detailed-description)

| Inheritance            |
|:-----------------------|
| DawTools.DtCore.DTimeSignature|

***

| Attributes|                  |
|:----------|:-----------------|
| beatsPerBar | int() |
| beatsPerNote | int() |

| Methods |
|:----------|
|def \_\_str\_\_()|
|def \_\_iter\_\_()|
|def [\_\_call\_\_()](dtimesignature.html#dawtoolsdtcoredtimesignature__call__args)|
|def [barsPerNote()](dtimesignature.html#dawtoolsdtcoredtimesignaturebarspernote)|
|def [barValue()](dtimesignature.html#dawtoolsdtcoredtimesignaturebarvalue)|
|def [beatValue()](dtimesignature.html#dawtoolsdtcoredtimesignaturebeatvalue)|

### Detailed Description
Time signatures influence the length of bars and beats. This class can retrieve
note value (note duration) for beats and bars based on the given numerator(beats per bar) and
denominator(beats per note or note duration).

It is also meant to be used with [DawTools.DtCore.DMeter](https://madponyinteractive.github.io/DawTools/DtCore/dmeter.html)

```python
time_sig = DTimeSignature('4/4')

# Get note value for a bar
note_value = time_sig.barValue()
print(note_value)# 1/1

# Because it returns a DNoteValue object
# we can retrieve note value as float
print(float(note_value))# 1.0

# Get note value for a beat
print(time_sig.beatValue())# 4/1
print(float(time_sig.beatValue()))# 4.0

# Change time signature
time_sig(4,8)
print(time_sig)# 4/8

# Copy object
time_sig_2 = DTimeSignature(time_sig)
time_sig_2.beatsPerBar = 8
print(time_sig)# 4/8
print(time_sig_2)# 8/8
```

***

## class DawTools.DtCore.DTimeSignature(args)
DawTools.DtCore.DTimeSignature(DTimeSignature)
DawTools.DtCore.DTimeSignature(timeSignature='4/4')
DawTools.DtCore.DTimeSignature(beatsPerBar=4, beatsPerNote=4)

* Parameters

  * **beatsPerBar** - `int` -> default = 4
  * **beatsPerNote** - `int` -> default = 4
  * **timeSignature** - `str` -> default = '4/4'
  * **timeSignature** - `tuple` -> default = (4,4)
  * **DTimeSignature** - `DawTools.DtCore.DTimeSignature`

Constructs a DTimeSignature object.|

***

## DawTools.DtCore.DTimeSignature.\_\_call\_\_(args)

* Return type

  * `str`

If arguments are passed it sets Time Signature using __init__. |
Return Time Signature as string |

***

## DawTools.DtCore.DTimeSignature.barsPerNote()

* Return type

  * `float`

  * `int`

Return How many bars in 1 whole note |

***

## DawTools.DtCore.DTimeSignature.barValue()

* Return type

  * [`DawTools.DtCore.DNoteValue`](https://madponyinteractive.github.io/DawTools/DtCore/dnotevalue.html)

Return DNoteValue for bars |

## DawTools.DtCore.DTimeSignature.beatValue()

* Return type

  * [`DawTools.DtCore.DNoteValue`](https://madponyinteractive.github.io/DawTools/DtCore/dnotevalue.html)

Return DNoteValue for beats |
