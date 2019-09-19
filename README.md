# Home Specification

Everything started from this picture posted on reddit. This picture was posted on `/r/homelab` and `/r/battlestations`.
There was some many positive reply and message about it, thanks you all ! And in addition, I received some many question
about the setup, hardware list, random question, etc. I promised to write a document with the full specification.

Here we are. This document describe lot of stuff and reply to some question I see on reddit's comments, so if some
stuff here seems useless to know, if it's here, it's because someone asked for it.

# Table of Contents

1. Environment
2. Sound System
3. Monitoring
4. Computing
5. Network
6. Miscellaneous

# Environment

I live in a loft, somewhere in Liège, in Belgium. The room is actually the living room which is
sort of my office by the way. Before living here, I was in a studio nearby, the living room was
about 25 square meter. The environment you see is about 25 square meter (it's mostly my previous
room in a new room).

## Truss

The scaffolding, metal stuff around the room is called Truss.
The whole rigging is made of Global Truss F14.

Here is quick draw schema of the stuff
```
+--+--+----------+--------------------+----------+--+--+
|BC|SP|    1m    |         2m         |    1m    |SP|BC|
+--+--+----------+--------------------+----------+--+--+
|SP|                 |           |                  |SP|
+--+             +--------------------+             +--+
|  |             |         2m         |             |  |
|  |             +--------------------+             |  |
|  | < 2.5m           (dashboards)           2.5m > |  |
|  |                                                |  |
|  |                                                |  |
+--+                                                +--+
|  |                                                |  |
|  |                                                |  |
|  | < 2.5m                                  2.5m > |  |
|  |                                                |  |
|  |                                                |  |
+--+                                                +--+
|SP|                                                |SP|
+--+--+----------+--------------------+----------+--+--+
|BC|SP|    1m    |         2m         |    1m    |SP|BC|
+--+--+----------+--------------------+----------+--+--+
```

- BC: Box Corner (10 x 10 x 10 cm)
- SP: Spacer (11 cm, single pipe)

The 4 box are elevated by 2m length with 17cm single pipe and base flat.

Total length: ~28m

## Flightcases

All the wood box you see are flightcases, they are all 19 inch width and ~45-55cm depth.

Flightcase on the left are used for sound and power management, flightcase on the right are
for networking and computing.

The two flightcases supporting the desk are 16U flightcases.

## Desk

The desk itself is just a plain plank of wood of 2.5m x 80cm x 2cm depositeds on the flightcases.

## Power Management

One of the flightcase on the right side is made for power management. It's like a big
multiplug manageable with 16 outlets. The outlet are PowerCON, the main reason is because
you can put up to 12 outlet of 20A in single 1U, which is quite huge. You can't do that
with default outlet (usualy up to 12A max and much larger).

On the box, there is a Raspberry Pi with Relay Modules to power on/off each channels.
There is a web interface to remote control channels and an api.

On top of that, you have a PowerBrite Pro15 which protect and monitor stuff.

## Light

The whole room light is remotely controlable.

### LED Stripe

The full square of truss have 18m of WS2812B Stripe LED (300 leds/m). This have the huge
advantage to provide 1080 LEDs addressable one-by-one. This is controlled by a dedicated
Raspberry Pi.

### PAR-16

On top of the desk, there are 6 Showtec PAR-16 with LED Light inside.

### Home made LED Bar



### Backlight

### Understairs

# Sound System

## Sound Rack

## PA System

### Sound Rack

### Amplifier

### Processing

### FOH

## Digital

### Raspberry Pi DAC+ Pro

### PulseAudio

# Monitoring

## Electric Consumtion

## Temperature

## Aggregation

## Dashboard

# Computing

## Desktop (Laptop)

### Operating System

### Hardware

kyb


### Sceens

#### Left

#### Middle

#### Right

## Server

## Mac Mini

# Network

## ISP

## Router

## Switch

# Miscellaneous

## Temperature and Noise

## Couch

## What do I do

## Price and Evolution

## USB Rack

## Power Bill

## Ceil


