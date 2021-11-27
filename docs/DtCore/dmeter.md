---
layout: default
title: DMeter
parent: DtCore
# nav_order: 1
---

# DawTools.DtCore.DMeter

The [DMeter](dmeter.html#class-dawtoolsdtcoredmeter) class provides a surface
to work with note values and seconds. [More...](dmeter.html#detailed-description)

| Inheritance            |
|:-----------------------|
| DawTools.DtCore.DMeter|

***

| Attributes    |                  |
|:--------------|:-----------------|
| noteValue     | DNoteValue |
| bpm           | DBpm |
| timeSignature | DTimeSignature |
| quantize      | DQuantize |

| Methods |
|:----------|
|def [\_\_call\_\_()](dmeter.html#dawtoolsdtcoredmeter__call__notevalue)|
|def [beats()](dmeter.html#dawtoolsdtcoredmeterbeats)|
|def [bars()](dmeter.html#dawtoolsdtcoredmeterbars)|
|def [quantizeUnits()](dmeter.html#dawtoolsdtcoredmeterquantizeunits)|
|def [barsPerNote()](dmeter.html#dawtoolsdtcoredmeterbarspernote)|
|def [tupletsPerNote()](dmeter.html#dawtoolsdtcoredmetertupletspernote)|
|def [seconds()](dmeter.html#dawtoolsdtcoredmeterseconds)|
|def [secondsPerNote()](dmeter.htmll#dawtoolsdtcoredmetersecondspernote)|
|def [secondsPerBeat()](dmeter.html#dawtoolsdtcoredmetersecondsperbeat)|
|def [secondsPerBar()](dmeter.html#dawtoolsdtcoredmetersecondsperbar)|
|def [secondsPerQuantize()](dmeter.html#dawtoolsdtcoredmetersecondsperquantize)|

### Detailed Description
Music meter object that can retrieve note values
and seconds for beat, bar and quantization units
```python
meter = DMeter()
print(meter)# DMeter(noteValue='1/1', bpm=120, timeSignature='4/4', quantize=8)
print(meter())# note value 1/1
```
You can construct a DMeter object directly and access its
values/objects to modify them...
```python
meter = DMeter()
meter.noteValue('1/32')
meter.bpm(140)
meter.timeSignature('3/4')
meter.quantize(128)
print(meter)# DMeter(noteValue = 1/32, bpm = 140, timeSignature = 3/4, quantize = 128)
```
Or you can have separate objects and any changes made to them will reflect on DMeter
```python
# Importing necessary classes
from DawTools.DtCore import DNoteValue, DBpm, DTimeSignature, DQuantize
# Constructing separate objects
nv = DNoteValue('1/2')
bpm = DBpm(60)
ts = DTimeSignature('2/4')
qtz = DQuantize(4)
# Assigning them to DMeter
meter = DMeter(nv,bpm,ts,qtz)
print(meter)# DMeter(noteValue = 1/2, bpm = 60, timeSignature = 2/4, quantize = 4)
# Changing values on the objects themselves
nv+='1/2'
bpm*=2
ts.beatsPerBar = 6
ts.beatsPerNote = 8
qtz.value=2
print(meter)# DMeter(noteValue = 1/1, bpm = 120, timeSignature = 6/8, quantize = 2)
# Changing values on the objects themselves
nv('1/8')
bpm(180)
ts('4/4')
qtz(16)
print(meter)# DMeter(noteValue = 1/8, bpm = 180, timeSignature = 4/4, quantize = 16)
```

***

## class DawTools.DtCore.DMeter
DawTools.DtCore.DMeter(DMeter)

DawTools.DtCore.DMeter(DNoteValue, DBpm, DTimeSignature, DQuantize)

DawTools.DtCore.DMeter(noteValue='1/1', bpm=120, timeSignature='4/4', quantize=8)

* Parameters

  * **noteValue** - `str`
  * **noteValue** - `float`
  * **bpm** - `float`
  * **timeSignature** - `str`
  * **timeSignature** - `tuple`
  * **quantize** - `int`
  * **DNoteValue** - [`DawTools.DtCore.DNoteValue`](https://madponyinteractive.github.io/DawTools/DtCore/dnotevalue.html)
  * **DBpm** - [`DawTools.DtCore.DBpm`](https://madponyinteractive.github.io/DawTools/DtCore/dbpm.html)
  * **DTimeSignature** - [`DawTools.DtCore.DTimeSignature`](https://madponyinteractive.github.io/DawTools/DtCore/dtimesignature.html)
  * **DQuantize** - [`DawTools.DtCore.DQuantize`](https://madponyinteractive.github.io/DawTools/DtCore/dquantize.html)

Constructs a DMeter object.|

***

## DawTools.DtCore.DMeter.\_\_call\_\_(noteValue)
* Parameters

  * **noteValue** - [`DawTools.DtCore.DNoteValue`](https://madponyinteractive.github.io/DawTools/DtCore/dnotevalue.html) -> default = None

* Return type

  * [`DawTools.DtCore.DNoteValue`](https://madponyinteractive.github.io/DawTools/DtCore/dnotevalue.html)

If value is passed it sets a new noteValue. |
Return noteValue |

***

## DawTools.DtCore.DMeter.beats()

* Return type

  * [`DawTools.DtCore.DNoteValue`](https://madponyinteractive.github.io/DawTools/DtCore/dnotevalue.html)

Return How many beats in noteValue |

***

## DawTools.DtCore.DMeter.bars()

* Return type

  * [`DawTools.DtCore.DNoteValue`](https://madponyinteractive.github.io/DawTools/DtCore/dnotevalue.html)

Return How many bars in noteValue |

***

## DawTools.DtCore.DMeter.quantizeUnits()

* Return type

  * [`DawTools.DtCore.DNoteValue`](https://madponyinteractive.github.io/DawTools/DtCore/dnotevalue.html)

Return How many quantize units in noteValue |

***

## DawTools.DtCore.DMeter.barsPerNote()

* Return type

  * [`DawTools.DtCore.DNoteValue`](https://madponyinteractive.github.io/DawTools/DtCore/dnotevalue.html)

Return How many bars in 1 whole note |

***

## DawTools.DtCore.DMeter.tupletsPerNote()

* Return type

  * [`DawTools.DtCore.DNoteValue`](https://madponyinteractive.github.io/DawTools/DtCore/dnotevalue.html)

Return How many tuplets in 1 whole note |

***

## DawTools.DtCore.DMeter.seconds()

* Return type

  * [`DawTools.DtCore.DSeconds`](https://madponyinteractive.github.io/DawTools/DtCore/dseconds.html)

Return How many seconds in noteValue |

***

## DawTools.DtCore.DMeter.secondsPerNote()

* Return type

  * [`DawTools.DtCore.DSeconds`](https://madponyinteractive.github.io/DawTools/DtCore/dseconds.html)

Return How many seconds in 1 whole note |

***

## DawTools.DtCore.DMeter.secondsPerBeat()

* Return type

  * [`DawTools.DtCore.DSeconds`](https://madponyinteractive.github.io/DawTools/DtCore/dseconds.html)

Return How many seconds there are in 1 beat |

***

## DawTools.DtCore.DMeter.secondsPerBar()

* Return type

  * [`DawTools.DtCore.DSeconds`](https://madponyinteractive.github.io/DawTools/DtCore/dseconds.html)

Return How many seconds there are in 1 bar |

***

## DawTools.DtCore.DMeter.secondsPerQuantize()

* Return type

  * [`DawTools.DtCore.DSeconds`](https://madponyinteractive.github.io/DawTools/DtCore/dseconds.html)

Return How many seconds there are in 1 quantize unit |
