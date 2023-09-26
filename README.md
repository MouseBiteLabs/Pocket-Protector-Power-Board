# Pocket Protector Power Board

This is a power regulator board for my <a href="https://github.com/MouseBiteLabs/Game-Boy-Pocket-Color">Game Boy Pocket Color (MGBC)</a> project for use with LiPo batteries. But hey, have you seen my other regulator board, the <a href="https://github.com/MouseBiteLabs/Pocket-Mouse-Power-Board">Pocket Mouser Power Board</a>? It's also really cool and doesn't use a battery that can explode.

[Board pictures]

## Disclaimer - MUST READ

I highly suggest testing this board before installation in a Game Boy. Failure to do so may result in an irreversibly damaged Game Boy. See the testing sequence below.

![image](https://github.com/MouseBiteLabs/Pocket-Protector-Power-Board/assets/97127539/deb4b43b-eeb8-43c7-b7f9-2ab094964ef5)

**This is a complicated build that requires high level soldering skills. Please do not attempt if you do not have advanced soldering experience. Do not attempt to hand-solder the QFN components on this board, you must use a hot plate.**

**I am not responsible for any damage done to you, your Game Boy, or your dwelling. Lithium ion batteries are a huge fire hazard. You accept any and all risks associated with attempting this project.**

![image](https://github.com/MouseBiteLabs/Pocket-Protector-Power-Board/assets/97127539/ff19da24-23ef-4fb8-ac65-065af7fdbe41)

## Successful Build Requirements

In order to effectively, properly, and *safely* build this board, you really must:

1) Read this *entire* README thoroughly and carefully
2) Use a lithium ion battery that has an internal DW01 protection IC - **NO BARE CELLS**
3) Use a hot plate and solder paste for good part placement
4) Own a multimeter for testing voltages and measuring resistance/continuity
5) Have advanced soldering skills
6) Have modded a Game Boy console before
7) Have a lot of patience (do not rush!)
8) Double check the assembled board before final installment using the testing procedure below
9) Have homeownder's/renter's insurance

## Board Characteristics and Order Information

The zipped folder contains all the gerber files for this board.
-	Layers: 4
-	Thickness: 1.6mm or thinner
-	Surface Finish: ENIG is highly recommended

You can use the zipped folder with the gerber files at any board fabricator you like. **I am not selling this board.**

## Features

Some features of this power board include: 

* Changing the power switch to a "soft power switch," meaning the main power of the Game Boy does not flow through the switch. A dirty power switch can severly impact performance, so using this scheme can remedy that issue.
* Generally improved efficiency over the OEM regulator, and increased switching frequency.
* Bootloop protection circuitry to prevent overdischarge of the battery past 3 V (a safe limit for lithium ion batteries), and to allow the Game Boy to die gracefully instead of violently stuttering until the regulator gives up.
* Load sharing (aka "power path") for charge-and-play capability.

This board was tested exclusively with this battery; any deviation from this one is 100% up to the user to determine compatibility: https://retrogamerepairshop.com/collections/gbp-power/products/102045-900mah-lipo-battery-cell?variant=40148887437484

**This battery includes a DW01 protection IC to prevent overcharge and deep overdischarge. Any battery used in this build must include a DW01 protection IC. This board does not include these protections.**

## Testing and Installation Steps

Testing the assembled board *is mandatory.* If you have misassembled it, a part is incorrect, if there is a hidden solder bridge, or one of many other issues - your 5 V supply might be too high when you turn it on! This is not ideal for your Game Boy! But also, importantly, you may cause damage to your battery (which can explode). So you absolutely need to make sure everything is connected properly and working as expected.

### Checking for Short Circuits

The following points must read as an open circuit ("OL") on a multimeter in resistance mode:

1) DC and BT+
2) DC and LIPO-
3) DC and LIPO+
4) BT+ and LIPO-
5) BT+ and LIPO+
6) LIPO+ and LIPO-
7) Pin 2 and pin 3 (middle and bottom holes on the left set of 3 holes)
8) Pin 4 and pin 7 (top and bottom holes on the right set of 4 holes)
9) Pin 2 and pin 7 (middle hole on the left and top hole on the right)

### Checking Resistances

1) Check R10. It must be approximately 2.49 kΩ.
2) Check R9. It must be approximately 10 kΩ.

## Bill of Materials

A prepopulated cart from Mouser can be found here: [link]. The quantities in the cart are enough such that there is at least one extra component in case you drop or lose one, except for U1 and U2 as they are more expensive. You may want to consider ordering multiple quantities of those parts just in case.



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
