# Home Specification

Everything started from this picture posted on reddit.

![Main Room Picture](https://i.redd.it/q3xy8gi8o0m31.jpg)

This picture was posted on `/r/homelab` and `/r/battlestations`.
There was so many positive reply and message about it, thanks you all ! And in addition, I received some many question
about the setup, hardware list, random question, etc. I promised to write a document with the full specification.

Here we are. This document describe lot of stuff and reply to some question I see on reddit's comments, so if some
stuff here seems useless to know, if it's here, it's because someone asked for it.

# Table of Contents

1. [Environment](#environment)
2. [Sound System](#sound-system)
3. [Monitoring](#monitoring)
4. [Computing](#computing)
5. [Network](#network)
6. [Miscellaneous](#miscellaneous)

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

The desk itself is just a plain plank of wood of (2.5m x 80cm x 2cm) deposited on the flightcases.

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

Software to control and manage the LEDs are available here: https://github.com/maxux/rooming

To power all of this, there are 2x 40A power behind.

### PAR-16

On top of the desk, there are 6 Showtec PAR-16 with LED Light inside.

### Home made LED Bar



### Backlight

Behind the dashboard, there are 2 incandescent light bulb which gives a warm color behind the scene.

### Understairs

There are an old 3m LED Strip under the stair, plain old 5050 controlled with a remote.

# Sound System

The sound system is made to be half permanant / half mobile. Amplifier, crossover and NEXO hardware
are ready to move, the 16U rack is clearly made to be permanant.

## Sound Rack

The permanant soundrack 16U is made of the following:
```
+--------------------------------------+
| Samson PowerBrite Pro15              |
| Legacy hardware                      |
| Legacy hardware                      |
| Behringer Ultralink Pro MX882        |
| Behringer Ultralink Pro MX882        |
| Behringer Powerplay Pro-XL HA4700    |
|                                      |
| Behringer CX3400 Super X Pro         |
| Samson S-com plus                    |
| Samson S-com plus                    |
|                                      |
|                                      |
| Fame Amplifier ] 2U                  |
| Fame Amplifier ]                     |
| Behringer EP2500 Amplifier ] 2U      |
| Behringer EP2500 Amplifier ]         |
+--------------------------------------+
```

- PowerBrite power the full rack, unit by unit
- Legacy hardware are broken stuff but there, in case
- The first Ultra Link is used as mixer:
  - Two first entries are Raspberry Sound (HiFi Berry)
  - Two next are used for live mixing entries
  - Two latest are used the Mac Mini
  - The main output goes to the second Ultra Link
- The second Ultra Link is used as merger:
  - Two first output goes to the crossover
  - Two next are sent to the Powerplay
  - Two latest are used for recording
- The Powerplay is just used for multiple headphones output
- The crossover is set up to split in 2 way, top way goes to the first S-com, bass to the second one.
- The first S-com is used as compressor/limiter for the top speakers
- The second S-com used as compressor/limiter for the bass speakers
- The fame amplifier is used to send signal to the bathroom
- The EP2500 is there for legacy purpose, not used anymore

The two compressor/limiter is there, mainly to keep my neighbor happy without the need to constantly be careful to the sound level.

The advantage to compress after the crossover is to fully control level of limiting for both bass and top.

Please note that all of this stuff were present before I get NEXO stuff, so it's quite redundent at some point but was needed before.

## PA System

PA changed multiple time. Current setup will probably stiff evolve later, but for now I'm quite happy with it.

The top on the desk are two NEXO PS-8 cabinet, bass (hidden behind the couch) are home made bass speaker cabinet with lowcost 8 inch
speaker inside.

### Amplifier

The top are amplified using a Behringer EP4000. Signal comes from the NEXO DTD-T and are sent back to it.

Bass is amplified with a Behringer EP1500 Bridged, bass is summed in the crossover.

### Processing

When moving, the NEXO DTD-T does everything alone like it should be.

When I'm at home, I don't want to change settings inside the DTD but I need/want to control compressor etc. that's why the
S-com are still there. The DTD at home is mainly there for security purpose for the PS-8. Signal from the first S-com goes
to the DTD and this one do processing for the PS-8. The second S-com goes directly to the bass amplifier.

## Digital

### Raspberry Pi with HiFiBerry DAC+ Pro

Mostly everything comes from the Raspberry Pi with HiFiBerry DAC+ Pro.
This small box provide a 2 XLR output (balanced obviously) from a really nice 96 kHz soundcard.

### PulseAudio

PulseAudio is running on the Raspberry Pi and multiple source send sound to it (mainly my main laptop).

I'm not a fan of PulseAudio, but I need to admit it does the job quite well for desktop purpose.
I would prefer using JACK everywhere but application support is too bad for daily usage.

# Monitoring

## Electric Consumtion

## Temperature

## Aggregation

## Dashboard

The two dashboard screen are just chromium in kiosk mode, displaying the two dashboard webpage.
The two screens are rotated by 180° (flipped) to get the best view angle from the bottom (which is the top of the screen).

To hide the cursor, I use `unclutter -idle 0`

When X start (using xinit), dwm is used as manager, but actually does nothing except handling the tiling.

As soon as dwm is ready, chromium takes over:
```
chromium --no-sandbox --test-type --kiosk --user-data-dir=$(mktemp -d) --class=dash1 [dashboard1-url] &
chromium --no-sandbox --test-type --kiosk --user-data-dir=$(mktemp -d) --class=dash2 [dashboard2-url] &
```

Option passed are there because I do everything as root (I don't care) and avoid any message when browser is restarted.
Class is used to send browser to the right screen using dwm config.

```
static const Rule rules[] = {
    /* class      instance    title       tags mask     isfloating   monitor */
    { "dash1",    NULL,       NULL,       0,            0,            0 },
    { "dash2",    NULL,       NULL,       0,            0,            1 },
}
```

# Computing

## Desktop (Laptop)

### Operating System

I'm running `Gentoo 17.0 ~amd64`

### Hardware

The laptop is a Dell G5 5587

- `Intel(R) Core(TM) i7-8750H CPU @ 2.20GHz` (8 cores, 12 threads)
- `SK Hynix 8GB DDR4` x2 (16 GB)
- `NVIDIA GeForce GTX 1060 Mobile`
- `Intel Corporation Wireless-AC 9560`
- `Atheros Killer E2400 Gigabit Ethernet`
- `PC SN520 NVMe WDC 256GB` (M.2)
- `Samsung SSD 850 PRO 256G` (SATA)

I use external keyboard and mice:
- `Das Keyboard Ultimate Model S` (Cherry MX Brown)
- `Logitech M510`


### Sceens

Now, they are all of them: `Iiyama ProLite XUB2790HS-B1`

#### Left

#### Middle

#### Right

## Server

## Mac Mini

# Network

## ISP

My ISP is VOO, with a Cable Modem (bridged) and 125 Mbps downstream and 6.5 Mbps upstream.

## Router

## Switch

There is only one single switch for everything, a TP-Link TL-SG1024, fanless 24x Gbps Switch, non manageable.
There are no VLAN, no special configuration, nothing. It's a flat network.

# Miscellaneous

## Temperature and Noise

The average temperature of the room is ~24°C. In plain summer, room temperature at peak is nearby 30°C.
The outside temperature can be around 38°C. There are no air conditionner.

During the winter, outside temperature is between 10°C and -5°C. The heater keep an average temperature of 22-24°C
which is perfect for me.

## Couch

## What do I do

I'm a developer for a Belgian company. I also do mixing on free time.

## Price and Evolution

All of this is the result of 10+ year of evolution.
Here you can see what was the status in 2007: https://imgur.com/a/RfoGy

## USB Rack

The USB sockets in the 1U rack on the right are just charging USB ports.
It's just a nice way to provide multiple charging-only port (there is a charger behind).

## Power Bill

Average power bill is around 120€/month.
Everything is electrical (heating, hot water, ...)

## Ceil

The ceil is at ~3m height
