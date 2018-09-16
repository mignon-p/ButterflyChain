# Chainable Butterfly

This repository contains the [KiCad][5] and [Gerber][6] files for a
PCB shaped like a butterfly.  The butterfly contains 18 "NeoPixel"
(WS-2812) LEDs.  The butterflies can be chained together, and
controlled by just about any microcontroller.  However, I specifically
had the [BBC micro:bit][16] in mind, and designed these chainable
butterflies together with my [neo:bit][17] and [feather:bit][18]
boards.

The butterfly design is based on my [butterfly nightlight][19], but I
have removed the microcontroller so that it can be controlled
externally.

* [View schematic](doc/schematic.pdf)
* [View PCB][20]

![butterfly board](doc/butterfly.jpg)

## Bill of Materials

* D1-D18 (qty 18) - 5mm through-hole NeoPixel.  SparkFun part
  no. [COM-12986](https://www.sparkfun.com/products/12986).  Digi-Key
  part no. [1568-1213-ND](https://www.digikey.com/product-detail/en/sparkfun-electronics/COM-12986/1568-1213-ND/5673799).
* C1 (qty 1) - 47µF 1210 capacitor.  Samsung part no. CL32A476MPJNNNE.
  Digi-Key part no. [1276-3380-1-ND](https://www.digikey.com/product-detail/en/samsung-electro-mechanics/CL32A476MPJNNNE/1276-3380-1-ND/3891466).
* J1-J2 (qty 1) - 3-pin JST SM Plug + Receptacle Cable Set.  Adafruit
  part no. [1663](https://www.adafruit.com/product/1663).
* [Bare wire, 20 AWG](https://smile.amazon.com/gp/product/B01BDB8240/).

## Circuit board

This board is big enough that it would be rather expensive to order
from [OSH Park][85], so I would recommend a Chinese fab such as
[Elecrow][86] or [JLCPCB][1].  I chose blue soldermask for my first
boards, but red or yellow might work, as well.  I chose the [ENIG][2]
finish.

If you're not making any changes to the board, all you need to do is
zip up the files in the `gerber` directory, and upload the zipfile to
Elecrow or JLCPCB.

Note that in the KiCad files and Gerber files, the "front" of the
board is actually the back, and vice-versa. This is because JLCPCB
adds a customer ID number to the front of the board, but I wanted the
number to be on the actual back of the board, where it doesn't disrupt
the esthetics of the butterfly.  (It turns out it's
[possible to specify the location of the customer ID][9], but I hadn't
read that when I first came up with this trick.)

## Assembly

1. Solder the surface-mount capacitor C1 onto the back of the board.

2. Solder the JST SM plug and receptacle to the J1 and J2 locations.
Be sure to get the polarity right!

3. Solder the 18 LEDs to the front of the board.  The LED should be
positioned so that the square pad gets one of the longer legs, not one
of the shorter ones.

4. Create the butterfly's antennae by inserting a length of bare wire
into the holes on the butterfly's head.  (These two holes are
represented by J3 on the schematic.)  It's a tight fit, so friction
may be enough to hold the wire in place, but you can always solder it
to be sure.

## License

This design is licensed under the
[Creative Commons Attribution-ShareAlike 4.0 International license][12].

Some of the footprints in `myLibrary.pretty` are based on footprints
in the [KiCad library][14], which is licensed under the
[KiCad library license][15] (which is now also CC-BY-SA-4.0, with an
exception).

[1]: https://jlcpcb.com/quote
[2]: https://en.wikipedia.org/wiki/Electroless_nickel_immersion_gold
[5]: http://kicad-pcb.org/
[6]: https://en.wikipedia.org/wiki/Gerber_format
[9]: https://support.jlcpcb.com/article/28-how-to-remove-the-customer-id-on-the-pcb
[12]: https://creativecommons.org/licenses/by-sa/4.0/
[14]: https://github.com/KiCad/kicad-footprints
[15]: https://forum.kicad.info/t/kicad-library-licensing/7856
[16]: https://microbit.org/
[17]: https://github.com/ppelleti/NeoBit
[18]: https://github.com/ppelleti/FeatherBit
[19]: https://github.com/ppelleti/butterfly-hw
[20]: https://eyrie.io/board/09c10aa2968c4cc28b5949b69b98fd31
[85]: https://oshpark.com/
[86]: https://www.elecrow.com/pcb-manufacturing.html
