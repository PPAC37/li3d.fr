https://www.lesimprimantes3d.fr/forum/topic/44815-polargraph-drawbot-scriboo-makelangelo/#comment-473115
# Polargraph (Drawbot Scriboo, Makelangelo, ...)

## BOM

Alimentation 12V et 5V ( Recyclage d'un bloc d'alimentation ATX de PC ) + (1 cable jumper pour connecter PIN PS_ON a GND pour "allumer" l'alimentation.) + cordon secteur 220V AC 
+ Embout Molex femmel x2 pour ne pas couper ?


Arduino Mega 2560 + cable USB

https://reprap.org/wiki/RAMPS_1.4 

https://reprap.org/wiki/RepRapDiscount_Full_Graphic_Smart_Controller ( enable the REPRAP_DISCOUNT_FULL_GRAPHIC_SMART_CONTROLLER in the "Configuration.h”. ) + cables de connexion + adaptateur pour RAMPS 1.4

Servo 9G + Câble 3 pines Dupont 2.54mm 70 cm  + connecteur 3p

DRIVER MOTEUR PAS À PAS DRV8825 ou 4A998

Moteur 1.8° par pas ...

Capteur de fin de course mécanique (Endstop) avec cable 2 pines Dupont 2.54 mm

Câble moteur nema ( JST PH 6p 2mm - <strike><del>HX 2.54mm</del></strike> <b>Dupont 2.54mm (cf RAMPS)</b>4p ) 1 mètre

Courrois GT2 3mm de ? 3 metres

Poulie GT3 30 dents 

fils / cable ? 10 AWG 

Kit de sertisage Dupont 2.54mm ( 1 pins) (pour alimenter en +5V le servo)

Ajout perso ( Barrette LED RGB 12V + resitances 330 Ohms ) ?

Impression 3D (porte moteur, support Arduino Mega, porte endstop, gondole ou porte plume )

Planchette de contreplaqué de 10cm * 120 cm * 1.2 cm ?

Vis

### Outils : 
Pince sertisage Dupond SN2 
Pince a dénuder 
...
Tournevis plat 2mm
...

![PIN OUT RAMPS 1.4](https://reprap.org/mediawiki/images/c/ca/Arduinomega1-4connectors.png "PIN OUT RAMPS 1.4")

## Choix du firmware

bien prendre https://github.com/MarginallyClever/Marlin-polargraph/tree/polargraph (la bonne branche) ... car lors de mes essais la branche https://github.com/MarlinFirmware/Marlin/tree/2.0.9.2 compile avec des warnings et ne fait pas fonctionner les moteurs...


## Connecter les endstops

https://reprap.org/wiki/RAMPS_1.4

<h2><span class="mw-headline" id="Endstops">Endstops</span></h2>
<div style="overflow: auto; position: relative; padding: 6px; margin-bottom: 1rem; border-left: 6px solid transparent;display: block; flex-direction: row; align-items: center; color:#721c24; background-color:#f8d7da; border-color:#f5c6cb;">
<table style="display:table-row"><tr>
<td style="padding-right: 6px;vertical-align: top;"><a href="https://reprap.org/wiki/File:Reprap_icon_stop.png" class="image"><img alt="Reprap icon stop.png" src="https://reprap.org/mediawiki/images/f/f2/Reprap_icon_stop.png" width="50" height="50" /></a></td><td style="overflow: auto; vertical-align: middle;">Pay attention when connecting the endstop to the RAMPS 1.4. Before you continue we suggest you read our wiki page on <a href="https://reprap.org/wiki/Mechanical_Endstop" title="Mechanical Endstop">mechanical endstops</a>. The RAMPS 1.4 offers no pull-up circuits, current limiting resistors or other protections. Wiring improperly an endstop that uses <b style="font-weight: normal; font-family: SFMono-Regular,Consolas,Liberation Mono,Menlo,monospace; font-size: 95%; display: inline-block; padding: 2px 4px; border-radius: 3px; border: 1px solid transparent;line-height: 1em; color:#fff; background-color:#FF5753; border-color:#7A1333;">5V</b> may damage an IO port on the ATmega 2560 or the Arduino itself, this is a particular issue with clones of the Arduino ATmega2560.</td></tr></table></div>
<p><br />
The endstops are the switches that tell the firmware when one of its axis (X, Y, Z) has reached either (or both) its minimum or maximum limit. In the board you will find six 3 pin connectors labeled (from left to right) <i>X-MIN</i>, <i>X-MAX</i>, <i>Y-MIN</i>, <i>Y-MAX</i>, <i>Z-MIN</i>, and <i>Z-MAX</i>. While you may connect both endstops for an axis the common setup is to use only one per axis. (Note firmwares implements software endstops for the opposite side using the dimensions on the build area of the printer.)
</p><p>To simplify the setup of the firmware it is easier to only use the <b>minimum</b> pins of each axis. The minimum is also know as the <i>home</i> location of your axis, on our traditional cartesian FDM printers we said that the end stop for the Z axis is in the bottom end of the frame, for the X axis is to the left of the frame and for the Y axis is somewhere near the back. (Note: all of this can be configured at will but requires more changes in the firmware. Check this excellent <a rel="nofollow" class="external text" href="https://marlinfw.org/docs/hardware/endstops.html">page</a> explaining endstops from the Marlin Firmware guys.)
</p><p><a href="https://reprap.org/wiki/File:Rampsv14_wiring_endstop_w_details.png" class="image"><img alt="Rampsv14 wiring endstop w details.png" src="https://reprap.org/mediawiki/images/thumb/3/3f/Rampsv14_wiring_endstop_w_details.png/800px-Rampsv14_wiring_endstop_w_details.png" width="800" height="530" srcset="https://reprap.org/mediawiki/images/thumb/3/3f/Rampsv14_wiring_endstop_w_details.png/1200px-Rampsv14_wiring_endstop_w_details.png 1.5x, /mediawiki/images/thumb/3/3f/Rampsv14_wiring_endstop_w_details.png/1600px-Rampsv14_wiring_endstop_w_details.png 2x" /></a>
</p><p>In the above figure we illustrate two common <a href="https://reprap.org/wiki/Mechanical_Endstop" title="Mechanical Endstop">mechanical endstops</a> that you will find. Check the wiki for <a href="https://reprap.org/wiki/Mechanical_Endstop" title="Mechanical Endstop">mechanical endstops</a> for more e info.
</p><p><a href="https://reprap.org/wiki/File:Reprap_sample_endstops_mech_circa_2020.png" class="image"><img alt="Reprap sample endstops mech circa 2020.png" src="https://reprap.org/mediawiki/images/thumb/3/3b/Reprap_sample_endstops_mech_circa_2020.png/800px-Reprap_sample_endstops_mech_circa_2020.png" width="800" height="603" srcset="https://reprap.org/mediawiki/images/thumb/3/3b/Reprap_sample_endstops_mech_circa_2020.png/1200px-Reprap_sample_endstops_mech_circa_2020.png 1.5x, /mediawiki/images/3/3b/Reprap_sample_endstops_mech_circa_2020.png 2x" /></a>
</p><p>You have endstops with 3-pin connectors. Now days when shopping online is very common to find 3-pins endstops with leds, mainly due to all the Ender 3, CR-10 and similar clones that use them.
</p><p>Is also common to find endstops with 2-pin connector or using only 2-wires (even if the connector has 3-pins). This is also the case when you wire your endstops directly, in which case only the <b style="font-weight: normal; font-family: SFMono-Regular,Consolas,Liberation Mono,Menlo,monospace; font-size: 95%; display: inline-block; color: #004085; background-color: #cce5ff; padding: 2px 4px; border-radius: 3px;border: 1px solid #b8daff;line-height: 1em;">COMMON</b> and <b style="font-weight: normal; font-family: SFMono-Regular,Consolas,Liberation Mono,Menlo,monospace; font-size: 95%; display: inline-block; color: #004085; background-color: #cce5ff; padding: 2px 4px; border-radius: 3px;border: 1px solid #b8daff;line-height: 1em;">NC</b> pins of the switch are used.
</p><p>From top-to bottom you will notice that for each axis the first pin is the <i>Signal</i> <b style="font-weight: normal; font-family: SFMono-Regular,Consolas,Liberation Mono,Menlo,monospace; font-size: 95%; display: inline-block; color: #004085; background-color: #cce5ff; padding: 2px 4px; border-radius: 3px;border: 1px solid #b8daff;line-height: 1em;">S</b>, the second is <b style="font-weight: normal; font-family: SFMono-Regular,Consolas,Liberation Mono,Menlo,monospace; font-size: 95%; display: inline-block; padding: 2px 4px; border-radius: 3px; border: 1px solid transparent;line-height: 1em; color:#fff; background-color:#3D4146; border-color:#222222;">GND</b>, and lastly the <b style="font-weight: normal; font-family: SFMono-Regular,Consolas,Liberation Mono,Menlo,monospace; font-size: 95%; display: inline-block; padding: 2px 4px; border-radius: 3px; border: 1px solid transparent;line-height: 1em; color:#fff; background-color:#FF5753; border-color:#7A1333;">5V</b> pin. In a two pin connection the <i>+</i> pin is <b>NOT</b> used.
</p><p>When wiring a 2-pin endstop the <i>NC</i> pin is connected to <i>GND</i> (<i>-</i>) on the board. The <i>COMMON</i> pin (marked as <b style="font-weight: normal; font-family: SFMono-Regular,Consolas,Liberation Mono,Menlo,monospace; font-size: 95%; display: inline-block; color: #004085; background-color: #cce5ff; padding: 2px 4px; border-radius: 3px;border: 1px solid #b8daff;line-height: 1em;">C</b> or <b style="font-weight: normal; font-family: SFMono-Regular,Consolas,Liberation Mono,Menlo,monospace; font-size: 95%; display: inline-block; color: #004085; background-color: #cce5ff; padding: 2px 4px; border-radius: 3px;border: 1px solid #b8daff;line-height: 1em;">S</b>) is connected to the <b style="font-weight: normal; font-family: SFMono-Regular,Consolas,Liberation Mono,Menlo,monospace; font-size: 95%; display: inline-block; color: #004085; background-color: #cce5ff; padding: 2px 4px; border-radius: 3px;border: 1px solid #b8daff;line-height: 1em;">S</b> on the board. Usually the endstop will have their pins identified.
</p>
<div style="overflow: auto; position: relative; padding: 6px; margin-bottom: 1rem; border-left: 6px solid transparent;display: block; flex-direction: row; align-items: center; color:#383d41; background-color:#e2e3e5; border-color:#d6d8db;">
<table style="display:table-row"><tr>
<td style="vertical-align: top;"></td><td style="overflow: auto; vertical-align: middle;">When wiring a 3-pin endstop is best not to make assumptions about the pinout on the endstop, check for markings on the PCB, read the manufacture's information or use a multimeter to identify the pins.</td></tr></table></div>
<p>Once you have figure out the type of endstops all that is left to do is to plug the corresponding connector for each axis using <i>minimum</i> pins in the board.
</p>
<div style="overflow: auto; position: relative; padding: 6px; margin-bottom: 1rem; border-left: 6px solid transparent;display: block; flex-direction: row; align-items: center; color:#004085; background-color:#cce5ff; border-color:#b8daff;">
<table style="display:table-row"><tr>
<td style="padding-right: 6px;vertical-align: top;"><a href="https://reprap.org/wiki/File:Reprap_icon_note.png" class="image"><img alt="Reprap icon note.png" src="https://reprap.org/mediawiki/images/7/7e/Reprap_icon_note.png" width="50" height="50" /></a></td><td style="overflow: auto; vertical-align: middle;">Using a switch that supports a <i>NC</i> (normally close) state is the preferred choice since it serves as a good safety feature. In case of a broken cable or broken switch or other damage, the circuit will open and the firmware can execute its expected fail-safe.</td></tr></table></div>
<div style="overflow: auto; position: relative; padding: 6px; margin-bottom: 1rem; border-left: 6px solid transparent;display: block; flex-direction: row; align-items: center; color:#383d41; background-color:#e2e3e5; border-color:#d6d8db;">
<table style="display:table-row"><tr>
<td style="padding-right: 6px;vertical-align: top;"><a href="https://reprap.org/wiki/File:Reprap_icon_printer.png" class="image"><img alt="Reprap icon printer.png" src="https://reprap.org/mediawiki/images/6/62/Reprap_icon_printer.png" width="50" height="50" /></a></td><td style="overflow: auto; vertical-align: middle;"><b>Setting up Marlin when using a Mekerbot Endstop or Pull-up-Resistors</b>:<br />1. Comment the constant <b style="font-weight: normal; font-family: SFMono-Regular,Consolas,Liberation Mono,Menlo,monospace; font-size: 95%; display: inline-block; padding: 2px 4px; border-radius: 3px; border: 1px solid transparent;line-height: 1em; color:#383d41; background-color:#e2e3e5; border-color:#d6d8db;">ENDSTOPPULLUPS</b> in <a rel="nofollow" class="external text" href="https://marlinfw.org/docs/configuration/configuration.html">configuration.h</a> to disable the built-in pull-up resistors.<br />2. Change the value of the constants <b style="font-weight: normal; font-family: SFMono-Regular,Consolas,Liberation Mono,Menlo,monospace; font-size: 95%; display: inline-block; padding: 2px 4px; border-radius: 3px; border: 1px solid transparent;line-height: 1em; color:#383d41; background-color:#e2e3e5; border-color:#d6d8db;">X_MIN_ENDSTOP_INVERTING</b>, <b style="font-weight: normal; font-family: SFMono-Regular,Consolas,Liberation Mono,Menlo,monospace; font-size: 95%; display: inline-block; padding: 2px 4px; border-radius: 3px; border: 1px solid transparent;line-height: 1em; color:#383d41; background-color:#e2e3e5; border-color:#d6d8db;">Y_MIN_ENDSTOP_INVERTING</b>, <b style="font-weight: normal; font-family: SFMono-Regular,Consolas,Liberation Mono,Menlo,monospace; font-size: 95%; display: inline-block; padding: 2px 4px; border-radius: 3px; border: 1px solid transparent;line-height: 1em; color:#383d41; background-color:#e2e3e5; border-color:#d6d8db;">Z_MIN_ENDSTOP_INVERTING</b> to true.</td></tr></table></div>
<h3><span class="mw-headline" id="See_also">See also</span></h3>
<ul><li> <a href="https://reprap.org/wiki/Mechanical_Endstop" title="Mechanical Endstop"> Mechanical Endstop</a></li>
<li> <a href="https://reprap.org/wiki/Endstop" title="Endstop"> Endstops</a></li></ul>



## Connecter le Servo 9G sur le RAMPS
Il faut ajouter une source 5V sinon lors du fonctionnement du servo, si on utilise un cavalier/Jumper pour alimenter les PINs 5V du/des servo avec le VCC de la carte RAMPS,
le servo vas drainer une bonne partie du 5V et l'ecran aura un affichage d'intensité fluctuant voir cela provoquera un reboot.


Éventuellement activer PINS_DEBUGGING donc Configuration_adv.h pour avoir la commande g-code M43 afin de voir quelle sont les attributions des pins (chez moi cela colle bien Pin 11 pour le servo0 :

```
22:07:46.845 : PIN:  11   Port: B5        SERVO0_PIN                             Output = 0    TIMER1A   PWM:  2000    WGM: 4    COM1A: 0    CS: 2    TCCR1A: 0    TCCR1B: 10    TIMSK1: 2   non-standard PWM mode   compare interrupt enabled
```

Et dans mon cas (RAMPS 1.4) si j'envoie la commande g-code "M280 P0 S180" puis "M280 P0 S90" j'ai bien mon servo 9G qui bouge... en position 180 puis 90 ...  ( [M280: Servo Position](https://marlinfw.org/docs/gcode/M280.html) )


https://www.marginallyclever.com/2021/10/friday-facts-4-how-to-marlin-polargraph/ Final thoughts :

By default Makelangelo software uses a servo position of 90 (middle of the range) for pen up and 40 for pen down. Keep that in mind when you install the servo horn (the finger thing that lifts).
?
```
M280 P0 S90 ; Pen Up
M280 P0 S40 ; Pen Down

```

Pour ajouter des commande perso ( Configuration_adv.h )
```
#define CUSTOM_MENU_MAIN
#if ENABLED(CUSTOM_MENU_MAIN)
  //#define CUSTOM_MENU_MAIN_TITLE "Custom Commands"
  #define CUSTOM_MENU_MAIN_SCRIPT_DONE "M117 User Script Done"
  #define CUSTOM_MENU_MAIN_SCRIPT_AUDIBLE_FEEDBACK
  //#define CUSTOM_MENU_MAIN_SCRIPT_RETURN   // Return to status screen after a script
  #define CUSTOM_MENU_MAIN_ONLY_IDLE         // Only show custom menu when the machine is idle

  #define MAIN_MENU_ITEM_1_DESC "Pen Up : M280 P0 S90"
  #define MAIN_MENU_ITEM_1_GCODE "M280 P0 S90"
  //#define MAIN_MENU_ITEM_1_CONFIRM          // Show a confirmation dialog before this action

  #define MAIN_MENU_ITEM_2_DESC "Pen Down : M280 P0 S40"
  #define MAIN_MENU_ITEM_2_GCODE "M280 P0 S40" 
  //#define MAIN_MENU_ITEM_2_CONFIRM
  ...
#endif
```

http://lokspace.eu/adding-9g-servo-based-autolevel-sensor-to-your-3d-printer/

### WIRING

The most important thing, is that you need a separate 5V power source for the servo. You can use the Arduino board itself, but the servo easily overloads the 5V regulator on the board, and can lead to unstable operation, spontaneous reboots, or even the regulator failing. So don't do that.

If you power your printer via ATX PSU (like I do), it's quite trivial - just connect the positive +5V output of the ATX PSU to the 5V pin shown on the picture below (no need to connect the GND wire).
If you use different kind of PSU, which has just 12V output, you can get 5V by using a cheap $0.36 
<a href="https://www.aliexpress.com/item/1pcs-Mini360-DC-DC-Buck-Converter-Step-Down-Module-4-75V-23V-to-1V-17V-17x11x3/32726435235.html" target="_blank" rel="noopener">step-down regulator</a>
. Connect it's "+" and "-" inputs to the 12V output of your PSU, and connect it's "+" output to the 5V pin from the picture (make sure the regulator is set to 5V before you connect the output!).
<a href="http://lokspace.eu/wp-content/uploads/2017/09/RAMPS1.4-Servo-Connection.jpg" rel="lightbox-0"><img loading="lazy" class="alignnone size-large wp-image-593" src="http://lokspace.eu/wp-content/uploads/2017/09/RAMPS1.4-Servo-Connection-1024x732.jpg" alt="" width="700" height="500" srcset="http://lokspace.eu/wp-content/uploads/2017/09/RAMPS1.4-Servo-Connection-1024x732.jpg 1024w, http://lokspace.eu/wp-content/uploads/2017/09/RAMPS1.4-Servo-Connection-300x215.jpg 300w, http://lokspace.eu/wp-content/uploads/2017/09/RAMPS1.4-Servo-Connection-768x549.jpg 768w, http://lokspace.eu/wp-content/uploads/2017/09/RAMPS1.4-Servo-Connection.jpg 1558w" sizes="(max-width: 700px) 100vw, 700px"></a>


Now it's time to connect the servo itself. You might need to extend the servo wires (they are usually pretty short).
Connect the servo to the first column of pins of the "SERVOS" connector - as shown on the picture. You have to check the color coding of your servo's wires. On mine, the orange wire was "Signal", and goes to D11, the red is "+" and goes to "5V", and the brown is "-" and goes to GND.
The switch that will be used is the regular endstop switch, and there is no need to connect it to different pins - leave it as is - connected to the Z_MIN endstop pins.


## Ajout d'une bar LED ... A REVOIR

Comme j'ai qui traine un morceau de bar LED de [RGB LED ADD-ON FOR K8400 - VERTEX 3D PRINTER](https://www.velleman.eu/products/view/?id=430100 "RGB LED ADD-ON FOR K8400 - VERTEX 3D PRINTER") 
![](https://www.velleman.eu/images/products/0/k8403.jpg)


Specifications  
power consumption: 470 mA  
https://www.velleman.eu/downloads/0/assembly/assemblymanual_k8403_en.pdf

Qui en principe fonctionne en 12V via l'utilisation de MOSFET avec l'ajout de resistences de 330Ohms (et de diodes pour sécuriser ? )....

Et comme sur le Polargraph je n'utilise pas les sortie de chauffes ( Tétes et Plateau chauffant) et que j'allimente en 12V.

Je me dit que je vais profiter des ses sortie 12V ...  
Mais je dois encor déterminer si le fait d'avoir un commun sur les BAR LED ne posera pas problème.  
Et je dois trouver un montage propre et qui evite les courts circuits ...

Configuration.h
```
#define RGB_LED
//#define RGBW_LED

#if EITHER(RGB_LED, RGBW_LED)

// Comme ma bar LED a besoin d'etre en 12V ... je vais tester avec les mosfet normalement pour la chauffe (tetes et bed) 
// D10, D9, D8 (enfin ... c'est a tester car le + du moins - je n'ai pas encore identifié le commun .... et il faut ajouter des Resistance de 330 Ohms et des diodes de protection ... ?)
  #define RGB_LED_R_PIN 10
  #define RGB_LED_G_PIN 9
  #define RGB_LED_B_PIN 8
  //#define RGB_LED_W_PIN -1
#endif
```

https://www.velleman.eu/downloads/0/information/resistor_colour_code.pdf
<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-coud{background-color:#009901;text-align:center;vertical-align:top}
.tg .tg-baqh{text-align:center;vertical-align:top}
.tg .tg-y9zf{background-color:#643403;border-color:inherit;color:#643403;text-align:center;vertical-align:top}
.tg .tg-s3tw{background-color:#cd9934;text-align:center;vertical-align:top}
.tg .tg-c3ow{border-color:inherit;text-align:center;vertical-align:top}
.tg .tg-iuu5{background-color:#00009b;text-align:center;vertical-align:top}
.tg .tg-lbzb{background-color:#fe0000;text-align:center;vertical-align:top}
.tg .tg-7btt{border-color:inherit;font-weight:bold;text-align:center;vertical-align:top}
.tg .tg-amwm{font-weight:bold;text-align:center;vertical-align:top}
.tg .tg-ksrh{background-color:#000000;border-color:inherit;text-align:center;vertical-align:top}
.tg .tg-0lax{text-align:left;vertical-align:top}
.tg .tg-8led{background-color:#f56b00;text-align:center;vertical-align:top}
.tg .tg-furw{background-color:#f8ff00;text-align:center;vertical-align:top}
.tg .tg-np64{background-color:#6200c9;text-align:center;vertical-align:top}
.tg .tg-4luf{background-color:#656565;text-align:center;vertical-align:top}
.tg .tg-i81m{background-color:#ffffff;text-align:center;vertical-align:top}
.tg .tg-sh07{background-color:#cbcefb;text-align:center;vertical-align:top}
</style>
<table class="tg">
<thead>
  <tr>
    <th class="tg-7btt" colspan="3" rowspan="2">Color</th>
    <th class="tg-7btt" colspan="3">DIGITS</th>
    <th class="tg-7btt">Multiplier</th>
    <th class="tg-amwm">Tolerance</th>
  </tr>
  <tr>
    <th class="tg-amwm">1st</th>
    <th class="tg-amwm">2nd</th>
    <th class="tg-amwm">3rd</th>
    <th class="tg-amwm">stripe</th>
    <th class="tg-amwm">4th stripe</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-ksrh" style="background-color:#009901;"></td>
    <td class="tg-0lax">Black</td>
    <td class="tg-baqh">Noir</td>
    <td class="tg-c3ow">0</td>
    <td class="tg-baqh">0</td>
    <td class="tg-c3ow">0</td>
    <td class="tg-c3ow">x 1</td>
    <td class="tg-baqh"></td>
  </tr>
  <tr>
    <td class="tg-y9zf" style="background-color:#643403;"></td>
    <td class="tg-0lax">Brown</td>
    <td class="tg-baqh">Brun/Marron</td>
    <td class="tg-c3ow">1</td>
    <td class="tg-baqh">1</td>
    <td class="tg-c3ow">1</td>
    <td class="tg-c3ow">x 10</td>
    <td class="tg-baqh">1%</td>
  </tr>
  <tr>
    <td class="tg-lbzb"><p style="background-color:#ff0000;">&nbsp</p></td>
    <td class="tg-0lax">Red</td>
    <td class="tg-baqh">Rouge</td>
    <td class="tg-baqh">2</td>
    <td class="tg-baqh">2</td>
    <td class="tg-baqh">2</td>
    <td class="tg-baqh">x 100</td>
    <td class="tg-baqh"></td>
  </tr>
  <tr>
    <td class="tg-8led"></td>
    <td class="tg-0lax">Orange</td>
    <td class="tg-baqh">Orange</td>
    <td class="tg-baqh">3</td>
    <td class="tg-baqh">3</td>
    <td class="tg-baqh">3</td>
    <td class="tg-baqh">x 1 000</td>
    <td class="tg-baqh"></td>
  </tr>
  <tr>
    <td class="tg-furw"></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal">Yellow</span></td>
    <td class="tg-baqh">Jaune</td>
    <td class="tg-baqh">4</td>
    <td class="tg-baqh">4</td>
    <td class="tg-baqh">4</td>
    <td class="tg-baqh">x 10 000</td>
    <td class="tg-baqh"></td>
  </tr>
  <tr>
    <td class="tg-coud"></td>
    <td class="tg-0lax">Green</td>
    <td class="tg-baqh">Vert</td>
    <td class="tg-baqh">5</td>
    <td class="tg-baqh">5</td>
    <td class="tg-baqh">5</td>
    <td class="tg-baqh">x 100 000</td>
    <td class="tg-baqh"></td>
  </tr>
  <tr>
    <td class="tg-iuu5"></td>
    <td class="tg-0lax">Blue</td>
    <td class="tg-baqh">Bleu</td>
    <td class="tg-baqh">6</td>
    <td class="tg-baqh">6</td>
    <td class="tg-baqh">6</td>
    <td class="tg-baqh">x 1 000 000</td>
    <td class="tg-baqh"></td>
  </tr>
  <tr>
    <td class="tg-np64"></td>
    <td class="tg-0lax">Purple</td>
    <td class="tg-baqh">Violet/Pourpre</td>
    <td class="tg-baqh">7</td>
    <td class="tg-baqh">7</td>
    <td class="tg-baqh">7</td>
    <td class="tg-baqh">-</td>
    <td class="tg-baqh"></td>
  </tr>
  <tr>
    <td class="tg-4luf"></td>
    <td class="tg-0lax">Grey</td>
    <td class="tg-baqh">Gris</td>
    <td class="tg-baqh">8</td>
    <td class="tg-baqh">8</td>
    <td class="tg-baqh">8</td>
    <td class="tg-baqh">-</td>
    <td class="tg-baqh"></td>
  </tr>
  <tr>
    <td class="tg-i81m"></td>
    <td class="tg-0lax">White</td>
    <td class="tg-baqh">Blanc</td>
    <td class="tg-baqh">9</td>
    <td class="tg-baqh">9</td>
    <td class="tg-baqh">9</td>
    <td class="tg-baqh">-</td>
    <td class="tg-baqh"></td>
  </tr>
  <tr>
    <td class="tg-s3tw"></td>
    <td class="tg-0lax">Gold</td>
    <td class="tg-baqh">Or</td>
    <td class="tg-baqh">-</td>
    <td class="tg-baqh">-</td>
    <td class="tg-baqh">-</td>
    <td class="tg-baqh">x 0.1</td>
    <td class="tg-baqh">5%</td>
  </tr>
  <tr>
    <td class="tg-sh07"></td>
    <td class="tg-0lax">Silver</td>
    <td class="tg-baqh">Argent</td>
    <td class="tg-baqh">-</td>
    <td class="tg-baqh">-</td>
    <td class="tg-baqh">-</td>
    <td class="tg-baqh">x 0.01</td>
    <td class="tg-baqh">10%</td>
  </tr>
</tbody>
</table>

## Ecart moteurs
Du centre d'un moteur a l'autre centre moteur  
Moi j'ai actuellement 106.4 cm car je voulais plus que le ~ 65cm du makelangelo v5  
Et donc je ne sais pas encore quelle distance de courroies il me faut ...

et forcement cela demande d'affiner le Configuration.h

```
#define POLARGRAPH_MAX_BELT_LEN 1035.0 \\ ??? a voir !
```

```
#define X_BED_SIZE 1064.0 // the width, Measured motor center to center, that’s 650 on the Makelangelo5.
#define Y_BED_SIZE 1000.0 // ?? Makelangelo 5 height = 1000, or 1m. 
```

```
#define X_MIN_POS ( - (X_BED_SIZE/2) )  
#define Y_MIN_POS ( - (Y_BED_SIZE/2) )
```
The bottom-left corner of the drawing area would then be - X_BED_SIZE/2 and -Y_BED_SIZE/2, or -325 and -500, respectively.

```
#define X_MAX_POS X_BED_SIZE/2
#define Y_MAX_POS Y_BED_SIZE/2
```
The top-right corner of the drawing area would then be X_BED_SIZE/2 and Y_BED_SIZE/2, or 325 and 500, respectively on the Makelangelo 5.

```
#define BED_CENTER_AT_0_0
```

```
#define MANUAL_X_HOME_POS 0
#define MANUAL_Y_HOME_POS ( Y_MAX_POS - ( sqrt( sq(POLARGRAPH_MAX_BELT_LEN) - sq(X_BED_SIZE/2) ) ) )
```
Remember using the triangle adjacent and the opposite to get the hypoteneuse? well here we use the opposite (machine bed size) and the hypoteneuse (the belt length) to get the adjacent, and then adjust by the Y_MAX_POS.

Note that the final value has to be inside the allowable drawing area of the machine – you can’t home to a spot that’s outside the printable area. That means the -Y_BED_SIZE/2 has to be a larger negative number than the MANUAL_Y_HOME_POS. With my settings -Y_BED_SIZE/2 is -500 and everything is fine.





