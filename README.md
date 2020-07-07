# timing

Arduino library with wrappers for seconds millis micros 

## Description

A request often made on the Arduino forum and otherwise is an option to reset
the **millis()** function to 0 or another value. 
This library provide wrapper classes around **millis()** and **micros()** 
with the extra function to do this. 
To implement this only a 4 byte offset is needed.

These classes make it easy to make a simple stopwatch.

## Interface 

The library has 3 classes that are very similar.
- microSeconds
- milliSeconds
- seconds  (wrapper around millis() too)

The interface of all three are very similar, so only one is described

- **milliSeconds()** constructor, sets the offset so it starts at 0.
- **now()** returs the time elapsed since its 'zero moment', either construction 
or by a set(0). 
- **set(value)** sets the offset of the object. As it is possible to set it 
to a non zero value it is easy to adjust the time. 

The classes are based upon **millis()** and **micros()** therefor have the same 
restrictions as these functions with respect to overflow and accuracy. 
Depending on e.g. interrupts millis and micros can drift.

| class | overflow after | 
|:----|:----|:----:|
|seconds       | 49 days, 17:02:47.297 |
| milliSeconds | 49 days, 17:02:47.297 |
| microSeconds | 00 days  01:11:34.967296 |

## Operation

See examples

## Todo
- test on ESP32

