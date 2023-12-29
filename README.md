# Pocket Protector Power Board

This is a power regulator board for my <a href="https://github.com/MouseBiteLabs/Game-Boy-Pocket-Color">Game Boy Pocket Color (MGBC)</a> project for use with LiPo batteries. But hey, have you seen my other regulator board, the <a href="https://github.com/MouseBiteLabs/Pocket-Mouse-Power-Board">Pocket Mouser Power Board</a>? It's also really cool and doesn't use a battery that can explode.

![image](https://github.com/MouseBiteLabs/Pocket-Protector-Power-Board/assets/97127539/ff710ad9-7f7b-4342-af3f-11c4f0c58c88)

## Important Things Before You Start

I highly suggest testing this board before installation in a Game Boy. Failure to do so may result in an irreversibly damaged Game Boy. See the testing sequence below.

![image](https://github.com/MouseBiteLabs/Pocket-Protector-Power-Board/assets/97127539/e5de26d0-6b67-4bbc-820b-3a5d9aa0e80e)

**This is a complicated build that requires high level soldering skills. Please do not attempt if you do not have advanced soldering experience. Do not attempt to hand-solder the QFN components on this board, you must use a hot plate.**

**I am not responsible for any damage done to you, your Game Boy, or your dwelling. Lithium ion batteries are a huge fire hazard. You accept any and all risks associated with attempting this project.**

![image](https://github.com/MouseBiteLabs/Pocket-Protector-Power-Board/assets/97127539/518b2961-8862-4ea5-a96e-8b36841dcca5)

## Mandatory Reading About Battery Safety

"Bucket Mouse, all my devices have lithium ion batteries in them, and they're not dangerous. Why are you fear mongering?"

I am but one hobbyist, making things in my room. The batteries and battery management systems you use in devices every day are created by engineering teams and produced by corporations who do rigorous testing on products they sell (or, at least, they are supposed to). Therefore, it is 100% up to *you* to safely manage these batteries, and know what you are doing, and know what to look out for with the batteries you purchase. This circuit board works for me, but as I am only one person, I have blind spots and I may have missed something (please tell me if I have). Also, I am confident in my soldering abilities - I am inherently *not* confident in yours. So, please, understand these risks and proceed at your own peril.

Read this article before continuing down this path: https://batteryuniversity.com/article/lithium-ion-safety-concerns

## Board Characteristics and Order Information

### Power Board

This is the board that sits in the U5 socket on the MGBC board.

The zipped folder contains all the gerber files for this board.
-	Layers: 4
-	Thickness: 1.6mm or thinner
-	Surface Finish: ENIG is recommended, HASL will work too

You can use the zipped folder with the gerber files at any board fabricator you like. **I am not selling this board.**

Hosted on OSH Park here: https://oshpark.com/shared_projects/ldmRhdWn

### USB-C Adapter Board

This breakout board adapts a USB-C port to the MGBC's DC jack footprint. Assemble the parts to this board (may need to trim the USB-C port legs to be flush with the board), then place on the MGBC board and flow solder into the DC jack socket holes through to the pads on the back of this board to secure it.

The zipped folder contains all the gerber files for this board.
-	Layers: 2
-	Thickness: 1.2mm is recommended
-	Surface Finish: HASL or ENIG

You can use the zipped folder with the gerber files at any board fabricator you like. **I am not selling this board.**

Hosted on OSH Park here: https://oshpark.com/shared_projects/hsA91SMe

## Features

Some features of this power board include: 

* Changing the power switch to a "soft power switch," meaning the main power of the Game Boy does not flow through the switch. A dirty power switch can severly impact performance, so using this scheme can remedy that issue.
* Bootloop protection circuitry to prevent overdischarge of the battery past 3 V (a safe limit for lithium ion batteries), and to allow the Game Boy to die gracefully instead of violently stuttering until the regulator gives up.
* Load sharing (aka "power path") for charge-and-play capability.

This board was tested exclusively with this battery; any deviation from this one is 100% up to the user to determine compatibility: https://retrogamerepairshop.com/collections/gbp-power/products/102045-900mah-lipo-battery-cell?variant=40148887437484

**This battery includes a DW01 protection IC to prevent overcharge and deep overdischarge. Any battery used in this build must include a DW01 protection IC. This circuit board does not include these protections.**

## Alternate LiPo Options

If you are at all doubting your ability to assemble this board, I recommend Nataliethenerd's Safer Charge DC, as it comes pre-assembled with everything you need: https://www.nataliethenerd.com/product-page/safer-charge-dc

<a href="https://www.nataliethenerd.com/product-page/safer-charge-dc"><img src="https://github.com/MouseBiteLabs/Pocket-Protector-Power-Board/assets/97127539/2f21e403-e07e-4f55-aace-cad3eed82622" /></a>

Another option is to **have someone more skilled than you assemble the board for you.** I am not one of those people, but they certainly exist.

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
9) Have homeowner's/renter's insurance

## Testing and Installation Steps

Testing the assembled board *is mandatory.* If you have misassembled it, a part is incorrect, if there is a hidden solder bridge, or one of many other issues - your 5 V supply might be too high when you turn it on! This is not ideal for your Game Boy! But also, importantly, you may cause damage to your battery (which can explode). So you absolutely need to make sure everything is connected properly and working as expected.

### Equipment

1) You will need a multimeter to check resistances and voltages.
2) You should have some sort of power source, like a AA battery holder with alligator clips or benchtop power supply. *You can use the lithium ion battery to test for all steps, but I would recommend something a bit safer for the initial 5V supply test if possible.*
3) I highly recommend getting test leads with clips, like this: https://mou.sr/47Yeuae. They really make testing easier without having to solder wires on.

![image](https://github.com/MouseBiteLabs/Pocket-Protector-Power-Board/assets/97127539/9f8c8415-b49b-4e88-85ed-8134179d8872)

### Step 1: Top Side Assembly and Testing for Short Circuits

Assemble the top side parts using a hot plate and solder paste. **Do not assemble the bottom side yet, as this will make reworks on the top side much more painful to perform if you find errors later.** 

![image](https://github.com/MouseBiteLabs/Pocket-Protector-Power-Board/assets/97127539/a43da905-4812-4adc-804f-7f06c126c039)

Afterwards, you'll want to check for short circuits on the charging IC (U3) with a multimeter. Finding them now will make your life much easier later. A short circuit will read as approximately 0 ohms on your multimeter. You can access (nearly) all the pertinent points via the backside of the PCB. See net definitions here:

![image](https://github.com/MouseBiteLabs/Pocket-Protector-Power-Board/assets/97127539/58f502a5-179e-43c5-8655-e216db90307c)

Check to make sure the following measurements are **not** short circuited (0 ohms):

1) BT+ and VUSB
2) BT+ and GND
3) VUSB and R7
4) VUSB and GND
5) VUSB and VPOS
6) R9 and GND
7) R9 and VPOS
8) VPOS and SW
9) VPOS and VCC
10) VPOS and 5V
11) VPOS and DC
12) VPOS and BT+

One last measurement is the resistance across the terminals of R10 (on the front of the board). It should read approximately 2.49 kΩ, +/- 1%.

Any measured short circuits indicates a solder bridge somewhere on the board, most likely on the QFN package.

### Step 2: Testing 5V Supply

The next step that will make your life easier later is to test the 5V generation handled by the *other* QFN device, U1.

1) Populate R5 on the backside of the board.
2) Connect pin 3 of the board to the negative end of a power source (like a battery holder or benchtop power supply).
3) Connect pin 2 (VCC) to the positive side of the power source.
4) Connect pin 1 (SW) to the positive side of the power source *after* pin 2 is connected. Turn the switch on (if you have a switch).
5) Measure the 5V output - positive multimeter probe on pin 7 of the board, negative probe on GND.

If your voltage measures anything but 5V (+/-1%) then you have an issue. Probably a solder bridge underneath U1. Get to troubleshooting!

![image](https://github.com/MouseBiteLabs/Pocket-Protector-Power-Board/assets/97127539/e033b20a-8fdf-457b-988b-f8e4da76f76a)

### Step 3: Populate the Back of the Board and Check Resistances

The bottom side of the board is easy to hand solder - this was done on purpose! ;)

![image](https://github.com/MouseBiteLabs/Pocket-Protector-Power-Board/assets/97127539/483614f4-ae3b-46b6-92ac-5932b3801ade)

Then check these resistances with a multimeter:

1) Check R9. It must be approximately 10 kΩ.
2) Check R10 (on the front of the board). It must (still) be approximately 2.49 kΩ.

This will also tell you if you have any new short circuits after assembling more parts. If you measure anything else, outside of a 1% margin, then something is wrong and it may be *dangerous* to use the board. Find the problem!

### Step 4: Preparing and Installing the USB-C Board

**The following steps requires the main MGBC board. The rest of this procedure assumes the MGBC is properly built.**

The USB-C breakout board sits on top of where the DC jack used to be. The board thickness should be 1.2mm for best fitment. 

1) Trim the legs of the USB-C port before soldering it in the board, so that the bottom of the board is a flush surface.
2) Solder in the port, then the 5.1kΩ resistors R1 and R2.
3) Place the board on top of the MGBC board, line up the solder pads through the holes, and flow solder through all five holes to secure it to the board.

![image](https://github.com/MouseBiteLabs/Pocket-Protector-Power-Board/assets/97127539/03cf40d1-17e9-4d65-b042-12f66c5daa1d)

### Step 5: Charge Testing

*Note: Charging will not work if F2 is blown. If you hare having issues, don't forget to check F2 for continuity.*

To set up the system for charging:

1) Connect the battery to the LIPO + and - holes on the power board using clips or wires. The DW01 should protect you if you short circuit the + and - wires together while you're soldering them in, but try to avoid it anyway.
2) Connect pins 1, 2, and 3 of the power board socket to the power board using clips or wires - don't mount it to the MGBC just yet.
3) Connect the DC hole on the power board to the DC hole on the MGBC.
4) If your MGBC board revision is v1.6 or earlier, make sure you have removed EM7 on the MGBC board. If you have v2.0 or later, **do not** remove EM7.

Measure the voltage of the battery with your multimeter. This should be measured from LIPO + pin to GND. Note what the voltage is - if it's higher than 4.1 V, then your battery is already fully charged so you may not be able to actually test the charging yet.

Now, plug in a USB-C cable to charge the battery. The red LED should come on. Once the red LED turns off by itself, the charge cycle is complete, and the voltage should measure around 4.1 V when fully charged. If the battery voltage ever rises *above* 4.2 V while charging, there may very well be a problem on your board assembly AND/OR the DW01 on your battery may be defective!

### Step 6: Testing 5V Supply With Lithium Ion Battery

*Note: The power will not turn on if F1 is blown. If you hare having issues, don't forget to check F1 for continuity.*

Disconnect the USB-C cable, and disconnect at least the positive lead of the battery. Make sure any residual charge on the 5V output is gone. Measure the voltage (positive probe on pin 7, negative probe on GND) and make sure it's 0 V (or close to it). Then, perform the following steps:

1) Connect the BT+ hole on the MGBC to the BT+ hole on the power board. **Be sure the 5V wire is still not connected (pin 7).**
2) Reconnect the battery as before.

Now, check the voltage on pin 2 of the power board (VCC): positive probe on pin 2, negative probe on GND. It should read somewhere between 3 V and 4.2 V (it will be your battery voltage). If you read 0 V, plug in your USB-C cable again and check to make sure the red LED turns on. Then measure the voltage to make sure the battery voltage appears on VCC. (If your DW01 tripped due to an overcurrent, like if you accidentally shorted the positive lead to GND, charging the battery will clear the error).

Now you should be able to turn on the 5V supply with the power switch on the MGBC. Test with the multimeter to make sure the 5V is output when the switch is on. Note that when the switch is off, the output capacitors will still hold a charge on the 5V output, so you will likely read a slowly discharging voltage when the switch is off. The important thing is to make sure the voltage output is a solid 5V (plus or minus 1% margin).

### Step 7: Final Testing and Assembly

As long as your 5 V output is the proper voltage, you can now finally connect the 5 V output to the MGBC board. **Make sure the power switch is off when you do this.** Check to make sure everything works as expected, and you can remove all the clips and test leads and permanently solder the board in (it is probably best to remove the battery while you do this, and add it in last). 

You may have to put the battery inside the back shell and *then* solder the wires into the power board. If you end up having any exposed metal, like if you spliced wires together, make sure you insulate the exposed area so you don't have any accidental short circuits.

## Bill of Materials

A prepopulated cart from Mouser can be found here: https://www.mouser.com/ProjectManager/ProjectDetail.aspx?AccessID=26118b92c3. You may want to consider ordering multiple quantities of some parts just in case you lose some during assembly.

### Regulator Board

| Reference Designators       | Qty | Value/Part Number  | Package  | Description      | Source                                           |
| --------------------------- | --- | ------------------ | -------- | ---------------- | ------------------------------------------------ |
| C1, C3, C5                  | 3   | 22uF               | 0805     | Capacitor (MLCC) | [https://mou.sr/46mVnVR](https://mou.sr/46mVnVR) |
| C2, C6                      | 2   | 10uF               | 0603     | Capacitor (MLCC) | [https://mou.sr/3mZtSkF](https://mou.sr/3mZtSkF) |
| C4                          | 1   | 0.1uF              | 0603     | Capacitor (MLCC) | [https://mou.sr/3ENc15O](https://mou.sr/3ENc15O) |
| D1                          | 1   | SMF5.0A-T13        | SOD-123  | TVS Diode        | [https://mou.sr/46lYsWi](https://mou.sr/46lYsWi) |
| D2                          | 1   | 150060RS75000      | 0603     | LED              | [https://mou.sr/3ul6dOR](https://mou.sr/3ul6dOR) |
| D3                          | 1   | VSS8D5M12HM3/H     | DO-221AD | Schottky Diode   | [https://mou.sr/3sHvulW](https://mou.sr/3sHvulW) |
| L1                          | 1   | 2.2uH              | 1212     | Inductor         | [https://mou.sr/46qW94a](https://mou.sr/46qW94a) |
| Q1                          | 1   | MMBT3906           | SOT23    | PNP BJT          | [https://mou.sr/3G7ub2I](https://mou.sr/3G7ub2I) |
| Q2, Q4                      | 2   | 2N7002             | SOT23    | N-channel MOSFET | [https://mou.sr/3rgfh6J](https://mou.sr/3rgfh6J) |
| Q3                          | 1   | MMBT3904           | SOT23    | NPN BJT          | [https://mou.sr/3Rv7yfA](https://mou.sr/3Rv7yfA) |
| R1, R4, R6, R8              | 4   | 100k               | 0603     | Resistor         | [https://mou.sr/49bgMnu](https://mou.sr/49bgMnu) |
| R2, R3, R5, R7, R9, R11     | 6   | 10k                | 0603     | Resistor         | [https://mou.sr/3riR7IH](https://mou.sr/3riR7IH) |
| R10                         | 1   | 2.49k              | 0603     | Resistor         | [https://mou.sr/3G7MS6w](https://mou.sr/3G7MS6w) |
| U1                          | 1   | TPS61202           | VSON-10  | Boost Converter  | [https://mou.sr/47hIE8c](https://mou.sr/47hIE8c) |
| U2                          | 1   | TPS3840DL30        | SOT23-5  | Supervisory IC   | [https://mou.sr/47JYTuN](https://mou.sr/47JYTuN) |
| U3                          | 1   | MCP73871-2CAI/ML   | QFN-20   |                  | [https://mou.sr/47F8yT5](https://mou.sr/47F8yT5) |
| \--                         | 1   | 10129378-904001BLF | \--      | 1x4 Header Pins  | [https://mou.sr/40SXaAX](https://mou.sr/40SXaAX) |
| \--                         | 1   | 10129378-903001BLF | \--      | 1x3 Header Pins  | [https://mou.sr/47nzLdm](https://mou.sr/47nzLdm) |

### USB-C Board

| Reference Designators | Qty | Value/Part Number | Package | Description     | Source                                           |
| --------------------- | --- | ----------------- | ------- | --------------- | ------------------------------------------------ |
| J1                    | 1   | USB4105-GF-A      | \--     | USB-C Connector | [https://mou.sr/48BChgu](https://mou.sr/48BChgu) |
| R1, R2                | 2   | 5.1k              | 0603    | Resistor        | [https://mou.sr/49J9uru](https://mou.sr/49J9uru) |

### Battery

As explained before, the battery you use **must** include a DW01 protection device. **DO NOT USE BARE CELLS**. Also note that the battery you order might be defective itself, so it is **up to you** to make sure it's safe. If your battery ever feels warm, or you measure voltages less than 2.45 V or greater than 4.2 V, the battery is defective and *should **not** be used*.

Testing was done exclusively with this battery: https://retrogamerepairshop.com/collections/gbp-power/products/102045-900mah-lipo-battery-cell?variant=40148887437484

I cannot claim that this specific battery is guaranteed to be safe and undamaged upon arrival, as I am not the vendor, so I don't know where it is sourced from. It's just the one I used. I would recommend *against* buying really cheap batteries from places like AliExpress. See the article about battery safety I linked above, especially the section titled "What Every Battery User Should Know": https://batteryuniversity.com/article/lithium-ion-safety-concerns

## Potential Issues

- I really can't stress enough that this project needs to be done correctly. Lithium ion batteries are only as safe as you make them. I am also only one person; while I have tested this board a lot, there may be an inherent flaw I missed - this is another reason why it is mandatory to have a DW01 protection device on the battery. Another thing to keep in mind is that the battery you purchase has the chance to be defective as well! Safety while using this board is *paramount*.

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
