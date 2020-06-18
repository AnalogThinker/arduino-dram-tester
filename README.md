# TRS-80 Arduino RAM Tester
This fork is modified to only test the 16k TRS-80 RAM (8041016A or NTE2117)

## Forked from
This is a fork from Andre Miller's excellent DRAMARDUINO DRAM Tester for 41256 and 4164 DRAM available here:
https://github.com/andremiller/arduino-dram-tester

## Basic DRAM tester, outputs results to Serial, based on:

* https://www.insentricity.com/a.cl/252
* https://github.com/FozzTexx/DRAM-Tester
* http://www.chronworks.com/DRAM

## Pinouts:

* DRAM pin       -> Arduino UNO pin
* Pin 2  (DIN)   -> A1
* Pin 14 (DOUT)  -> 8
* Pin 15 (CAS)   -> 9
* Pin 4  (RAS)   -> A3
* Pin 3  (WE)    -> A2
* Pin 5  (A0)    -> A4
* Pin 7  (A1)    -> 2
* Pin 6  (A2)    -> A5
* Pin 12 (A3)    -> 6
* Pin 11 (A4)    -> 5
* Pin 10 (A5)    -> 4
* Pin 13 (A6)    -> 7

(Also connect DRAM supply pins, unlike original project, additional voltage rails are required and should be provided using a bench power supply)
Pin 1 (Vbb) -> -5V
Pin 8 (Vdd) -> 12V
Pin 16 (Gnd) -> Gnd
Pin 9 (Vcc) -> 5V


The number of address lines is configurable by setting ADDR_BITS

## Changes to original code:

* Writes output to serial, displaying which row and col failed
* Times the tests and writes how long it took, just out of curiosity so you can calculate of refresh is happening fast enough
* Does pattern tests first (10101... and 01010...) because this identified failed ram faster for me
* Added a random bit write test
