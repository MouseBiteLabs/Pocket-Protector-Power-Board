# Pocket Protector Power Board

This is a power regulator board for my <a href="https://github.com/MouseBiteLabs/Game-Boy-Pocket-Color">Game Boy Pocket Color (MGBC)</a> project for use with LiPo batteries. But hey, have you seen my other regulator board, the <a href="https://github.com/MouseBiteLabs/Pocket-Mouse-Power-Board">Pocket Mouser Power Board</a>? It's also really cool and doesn't use a battery that can explode.

[Board pictures]

## Disclaimer - MUST READ

I highly suggest testing this board before installation in a Game Boy. Failure to do so may result in an irreversibly damaged Game Boy. See the testing sequence below.

**This is a complicated build that requires high level soldering skills. Please do not attempt if you do not have advanced soldering experience. Do not attempt to hand-solder the QFN component on this board, you must use either hot air or a hot plate. I am not responsible for any damage done to you or your Game Boy. You accept any and all risks associated with attempting this project.**

## Board Characteristics and Order Information

The zipped folder contains all the gerber files for this board.
-	Layers: 4
-	Thickness: 1.6mm or thinner
-	Surface Finish: ENIG is highly recommended

You can use the zipped folder with the gerber files at any board fabricator you like.

## Features

Some features of this power board include: 

* Changing the power switch to a "soft power switch," meaning the main power of the Game Boy does not flow through the switch. A dirty power switch can severly impact performance, so using this scheme can remedy that issue.
* Generally improved efficiency over the OEM regulator, and increased switching frequency.
* Bootloop protection circuitry to prevent overdischarge of the battery past 3 V (a safe limit for lithium polymer batteries), and to allow the Game Boy to die gracefully instead of violently stuttering until the regulator gives up.
* Load sharing (aka "power path") for charge-and-play capability.

This board was tested exclusively with this battery; any deviation from this one is 100% up to the user to determine compatibility: https://retrogamerepairshop.com/collections/gbp-power/products/102045-900mah-lipo-battery-cell?variant=40148887437484

## Testing

Testing the assembled board *is mandatory.* If you have misassembled it, a part is incorrect, if there is a hidden solder bridge, or one of many other issues - your 5 V supply might be too high when you turn it on! This is not ideal for your Game Boy! But also, importantly, you may cause damage to your battery (which can explode). So you absolutely need to make sure everything is connected properly and working as expected.

## Bill of Materials

A prepopulated cart from Mouser can be found here: [link]. The quantities in the cart are enough such that there is at least one extra component in case you drop or lose one, except for U1 and U2 as they are more expensive. You may want to consider ordering multiple quantities of those parts just in case.

If parts are out of stock or backordered, you can search for the parts on Digikey. The only parts that have no replacements are U1 and U2, every other component has suitable alternate parts you can search for.

| Ref Des        | QTY | Value       | Footprint | Type             | Notes                                        | Link                                                                                                                                                                                                                                                   |
| -------------- | --- | ----------- | --------- | ---------------- | -------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| C1, C3, C5     | 3   | 22uF        | 0805      | Capacitor (MLCC) | X5R or better, 16V or higher                 | https://www.mouser.com/ProductDetail/Murata-Electronics/GRM21BR61E226ME44K?qs=hNud%2FORuBR25jDsUehWlrQ%3D%3D                                                                                                                                           |
| C2, C4         | 2   | 0.1uF       | 0603      | Capacitor (MLCC) | C2 is removed on v1.3                        | [https://www.mouser.com/ProductDetail/KEMET/C0603C104M3RACTU?qs=7q2aiX3Gdlh4qBRaMcnohQ%3D%3D](https://www.mouser.com/ProductDetail/KEMET/C0603C104M3RACTU?qs=7q2aiX3Gdlh4qBRaMcnohQ%3D%3D)                                                             |
| D1             | 1   | BAT42       | SOD323    | Schottky Diode   | Only used on v1.3                            | https://www.mouser.com/ProductDetail/78-BAT42WS-E3-18
| L1             | 1   | 2.2uH       | 1212      | Inductor         | Saturation current higher than 1 A preferred | [https://www.mouser.com/ProductDetail/Murata-Electronics/LQH3NPN2R2MMEL?qs=sJ5gq5MLFXqbWZz8NzZoog%3D%3D](https://www.mouser.com/ProductDetail/Murata-Electronics/LQH3NPN2R2MMEL?qs=sJ5gq5MLFXqbWZz8NzZoog%3D%3D)                                       |
| Q1             | 1   | MMBT3906    | SOT23     | PNP BJT          |                                              | [https://www.mouser.com/ProductDetail/Micro-Commercial-Components-MCC/MMBT3906HE3-TP?qs=HBWAp0VN4Rh%2Ft2ZPx%252BV99A%3D%3D](https://www.mouser.com/ProductDetail/Micro-Commercial-Components-MCC/MMBT3906HE3-TP?qs=HBWAp0VN4Rh%2Ft2ZPx%252BV99A%3D%3D) |
| Q2, Q4         | 2   | 2N7002      | SOT23     | N-channel MOSFET |                                              | [https://www.mouser.com/ProductDetail/Nexperia/2N7002NXBKR?qs=%252B6g0mu59x7J2ddJstTJGkQ%3D%3D](https://www.mouser.com/ProductDetail/Nexperia/2N7002NXBKR?qs=%252B6g0mu59x7J2ddJstTJGkQ%3D%3D)                                                         |
| Q3             | 1   | MMBT3904    | SOT23     | NPN BJT          |                                              | [https://www.mouser.com/ProductDetail/Nexperia/MMBT3904VL?qs=cnAQGvEIVkKbCwIpHJoHxQ%3D%3D](https://www.mouser.com/ProductDetail/Nexperia/MMBT3904VL?qs=cnAQGvEIVkKbCwIpHJoHxQ%3D%3D)                                                                   |
| R1, R4, R6, R8 | 4   | 100k        | 0603      | Resistor         |                                              | [https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-07100KL?qs=e1ok2LiJcmaihem8Va5%2Fsw%3D%3D](https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-07100KL?qs=e1ok2LiJcmaihem8Va5%2Fsw%3D%3D)                                                         |
| R2, R3, R5     | 3   | 10k         | 0603      | Resistor         |                                              | [https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-0710KL?qs=grNVn54RoB%252B3GtjbJj3wJQ%3D%3D](https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-0710KL?qs=grNVn54RoB%252B3GtjbJj3wJQ%3D%3D)                                                       |
| U1             | 1   | TPS61202    | WSON-10   | Boost Converter  |                                              | [https://www.mouser.com/ProductDetail/Texas-Instruments/TPS61202DSCR?qs=WxL8HmPi5r6YtrNaHRAS2Q%3D%3D](https://www.mouser.com/ProductDetail/Texas-Instruments/TPS61202DSCR?qs=WxL8HmPi5r6YtrNaHRAS2Q%3D%3D)                                             |
| U2             | 1   | TPS3840DL20 | SOT23-5   | Supervisory IC   |                                              | [https://www.mouser.com/ProductDetail/Texas-Instruments/TPS3840DL20DBVR?qs=T3oQrply3y%2FZsfSrLIG7Ww%3D%3D](https://www.mouser.com/ProductDetail/Texas-Instruments/TPS3840DL20DBVR?qs=T3oQrply3y%2FZsfSrLIG7Ww%3D%3D)                                   |
| --             | 1   | 10129378-903001BLF |    | Header pin strip (3 pins) |                                     | https://www.mouser.com/ProductDetail/Amphenol-FCI/10129378-903001BLF?qs=0lQeLiL1qybuYTJnitumiA%3D%3D                                   |
| --             | 1   | 10129378-904001BLF |    | Header pin strip (4 pins) |                                     | https://www.mouser.com/ProductDetail/Amphenol-FCI/10129378-904001BLF?qs=0lQeLiL1qyYgZuNoMLioxA%3D%3D                                   |

## Potential Issues

- The battery might explode.

## Revision History

### v1.3
- Removed a via
- Changed silkscreen information

### v1.2
- Changed silkscreen information
- Modified various component values and part placements

### v1.1
- Added a series diode to drop 5 V charging input down to a lower voltage, to prevent DCM in the regulator which caused audio interference
- Modified various component values and part placements

### v1.0
- Release version

## License
<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/80x15.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>. You are able to copy and redistribute the material in any medium or format, as well as remix, transform, or build upon the material for any purpose (even commercial) - but you **must** give appropriate credit, provide a link to the license, and indicate if any changes were made.

©MouseBiteLabs 2023
